# New-Machine

An elegant, automated onboarding and bootstrapping system for setting up fresh macOS machines for development using the `denver` configuration repository.

This public repository contains the **`init`** script, which safely resolves the classic chicken-and-egg bootstrapping issue by installing Homebrew, downloading 1Password CLI (`op`) and GitHub CLI (`gh`), authenticating with 1Password to retrieve your personal access tokens, and securely cloning your private `devenv` repository to run the main installer.

## 🚀 Bootstrap Command

To set up a brand new macOS machine, open the default macOS **Terminal.app** (not Kitty) and run the following command:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/danshumaker/New-Machine/main/init)"
```

## 📦 What the Bootstrapper Does:

1. **Installs Homebrew:** Downloads and configures the latest Homebrew package manager non-interactively.
2. **Installs Bootstrap Utilities:** Installs `1password-cli` and `gh` via Homebrew.
3. **Connects to 1Password:** Configures your 1Password CLI client for securely accessing your GitHub Access Token (`GH_TOKEN`).
4. **Authenticates GitHub CLI:** Uses your secure `GH_TOKEN` from 1Password to log into GitHub CLI seamlessly.
5. **Clones Denver Repository:** Clones your private `danshumaker/devenv` repository.
6. **Hands-Off Setup:** Launches the main interactive `./install` script to complete your environment installation!

## TODO

- Switch from https to ssh gh protocol. https has git push issues.
