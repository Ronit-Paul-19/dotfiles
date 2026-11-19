# Dotfiles

My developer environment dotfiles and setup guide.

---

## 0. Set up GlazeWM and YASB first

Set these up first so the desktop environment is ready before continuing.

```powershell
winget install glzr-io.glazewm
winget install --id AmN.yasb
```

---

## 1. Install Git, Tree-sitter, Neovim and clone the configuration

Run the following commands:

```powershell
winget install --id Git.Git --exact --source winget

git config --global user.name "<your GitHub username>"
git config --global user.email "<your GitHub email>"

winget install -e --id tree-sitter.tree-sitter-cli

winget install --id Neovim.Neovim --exact --version 0.12.0

git clone https://github.com/RonitPaul19/nvim.git "$env:LOCALAPPDATA\nvim"
```

---

## 2. Restart the terminal and verify the installation

Close the terminal, reopen it, and run:

```powershell
git --version
git config --global --list
nvim --version
```

---

## 3. Install terminal utilities

Run:

```powershell
Install-Module PSReadLine -Force

winget install --id Starship.Starship --exact --source winget
winget install --id junegunn.fzf --exact --source winget
winget install --id BurntSushi.ripgrep.MSVC --exact --source winget
winget install --id sharkdp.fd --exact --source winget
winget install --id ajeetdsouza.zoxide --exact --source winget
winget install --id eza-community.eza --exact --source winget
winget install --id marlocarlo.psmux --exact --source winget
```

---

## 4. Restart the terminal and verify the utilities

Close the terminal, reopen it, and run:

```powershell
starship --version
fzf --version
rg --version
fd --version
zoxide --version
eza --version
```

---

## 5. Install the developer tech stack

### Node.js

```powershell
winget install --id OpenJS.NodeJS.LTS --exact --source winget
```

### Python

```powershell
winget install --id Python.Python.3.14 --exact --source winget
```

### C++ / MSYS2

```powershell
winget install --id MSYS2.MSYS2 --exact --source winget
```

---

## 6. Add MSYS2 UCRT64 to PATH

Add the following directory to the system `PATH`:

```text
C:\msys64\ucrt64\bin
```

---

## 7. Verify the C++ toolchain

Close the terminal, reopen it, and run:

```powershell
gcc --version
g++ --version
gdb --version
which gcc
which g++
```

---

## 8. Install the AI coding agent

Install OpenCode globally using npm:

```powershell
npm install --global opencode-ai
```
