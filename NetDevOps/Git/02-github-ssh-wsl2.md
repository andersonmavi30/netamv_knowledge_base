---
tags: [git, github, ssh, wsl2, netdevops]
validation: reference
---

# GitHub SSH authentication from WSL2 — step by step

[🇬🇧 English](02-github-ssh-wsl2.md) · [🇨🇴 Español](02-github-ssh-wsl2.es.md) · [↩ Git](README.md)

**Platform:** Ubuntu or another Linux distribution in WSL2, Bash, OpenSSH and Git. These steps configure the Linux environment, not Windows OpenSSH. Work from your normal WSL user, not root. Use a passphrase for the private key.

## 1. Verify the tools and existing keys

```bash
git --version
ssh -V
ls -la ~/.ssh
```

- **Purpose:** Confirm Git/OpenSSH are available and check whether you already have SSH keys.
- **Arguments:** `--version`: Git version; `-V`: SSH version (uppercase V); `ls -la`: long listing including hidden files; `~/.ssh`: Linux user's SSH directory.
- **Use case:** Avoid overwriting a key that already works. If `~/.ssh` does not exist, that is normal for a first-time setup.

## 2. Generate a dedicated Ed25519 key (only if needed)

```bash
mkdir -p ~/.ssh
chmod 700 ~/.ssh
ssh-keygen -t ed25519 -C "your-email@example.com" -f ~/.ssh/id_ed25519_github
```

- **Purpose:** Create a distinct GitHub SSH key pair in WSL2.
- **Arguments:** `mkdir -p`: create directory if missing; `chmod 700`: owner-only directory access; `-t ed25519`: key algorithm; `-C`: identifying comment (replace the sample email); `-f`: key-pair filename.
- **Use case:** Use a dedicated WSL2 identity for GitHub pushes. Choose a strong passphrase when prompted. **If the key file already exists, do not overwrite it; reuse it or choose another filename.**
- **Security:** `id_ed25519_github` is the **private** key; `id_ed25519_github.pub` is the **public** key. Never upload, paste or commit the private key.

## 3. Load the private key in the WSL2 SSH agent

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519_github
ssh-add -l
```

- **Purpose:** Start a session-local agent, load the key, and list loaded identities.
- **Arguments:** `ssh-agent -s`: output shell setup for the agent; `eval`: apply it to the current shell; `ssh-add`: load the private key; `-l`: list loaded-key fingerprints.
- **Use case:** Authenticate Git operations without typing the key's passphrase for every operation. A new WSL session may need its agent/key loaded again.

## 4. Copy only the public key to your GitHub account

```bash
cat ~/.ssh/id_ed25519_github.pub
```

- **Purpose:** Print the public key (usually begins with `ssh-ed25519`).
- **Arguments:** `cat`: print file content; `.pub`: denotes the public key, **not** the private key.
- **Use case:** Copy the **entire single-line public key** to **GitHub → Settings → SSH and GPG keys → New SSH key**; choose **Authentication Key**, give it a recognizable title (for example, `WSL2-Ubuntu`), then save.
- **Official reference:** https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

## 5. Choose the key for github.com (recommended for a dedicated key)

Create or edit `~/.ssh/config` (for example with `vim ~/.ssh/config`) and add:

```sshconfig
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_github
    IdentitiesOnly yes
```

Then secure the file:

```bash
chmod 600 ~/.ssh/config
chmod 600 ~/.ssh/id_ed25519_github
```

- **Purpose:** Use the selected private key whenever this WSL2 environment connects to GitHub.
- **Arguments:** `IdentityFile`: private-key path; `IdentitiesOnly yes`: restrict offered keys; `chmod 600`: owner read/write on config and key.
- **Caution:** If an existing `Host github.com` section is present, edit it instead of creating conflicting duplicates. A dedicated key is optional if an existing GitHub key already works.

## 6. Test the SSH connection

```bash
ssh -T git@github.com
```

- **Purpose:** Verify that GitHub recognizes the SSH key.
- **Arguments:** `-T`: disable pseudo-terminal allocation; `git@github.com`: GitHub SSH account/host.
- **Use case:** The expected success message recognizes your GitHub account and explains that shell access is unavailable; exit code **1** can still be normal for this test.
- **Security:** On first connection, **verify GitHub's published SSH host-key fingerprint** before accepting the host key; never accept an unexpected fingerprint blindly.
- **Official references:** https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection and https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints

## 7. Connect a local repository via SSH and verify the remote

Run these inside the local **RHCSA simulator repository**:

```bash
git remote -v
git remote set-url rhcsa_simulator git@github.com:andersonmavi30/rhcsa_simulator.git
git remote -v
git ls-remote rhcsa_simulator HEAD
```

- **Purpose:** Inspect remotes, change the existing `rhcsa_simulator` remote to SSH, and confirm read access.
- **Arguments:** `remote -v`: list fetch/push URLs; `remote set-url`: replace an existing remote URL; `rhcsa_simulator`: local remote name; `ls-remote … HEAD`: read the remote's advertised HEAD without cloning or modifying it.
- **Use case:** Confirm that the RHCSA simulator repository can be accessed via the configured WSL2 SSH key.
- **Important:** If `git remote -v` shows only `origin`, substitute `origin` for `rhcsa_simulator` in both commands; do not assume the remote name. If no remote exists, use `git remote add origin git@github.com:andersonmavi30/rhcsa_simulator.git` instead.
- **Official reference:** https://git-scm.com/docs/git-remote

## Quick troubleshooting

- **Permission denied (publickey):** Check `ssh-add -l`, the uploaded **.pub** key and `~/.ssh/config`; use `ssh -vT git@github.com` to see which key is offered (`-v`: verbose diagnostics).
- **No such remote:** Run `git remote -v` to confirm its actual local name.
- **Host key verification failed:** Check the published GitHub fingerprint and `~/.ssh/known_hosts`; do not bypass host verification.
- **Works on Windows but not in WSL2:** WSL2 has a separate Linux `~/.ssh` and SSH agent unless you explicitly configured sharing.

> Reference procedure; not executed against the user's WSL2 environment. Never put private keys, access tokens or personal secrets in Git repositories.
