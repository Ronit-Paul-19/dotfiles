# Dotfiles

My developer environment dotfiles and setup guide.

---

# AT FIRST INSTALL POWERSHELL 7 FROM MS STORE


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

### MSYS2

```powershell
winget install --id MSYS2.MSYS2 --exact --source winget
```

---

## 6. Set up the MSYS2 C++ toolchain

Open the **MSYS2 UCRT64 terminal** and update the package database and system packages.

### First update

```bash
pacman -Syu
```

If MSYS2 asks you to close the terminal, close it and reopen the **MSYS2 UCRT64** terminal.

### Run the update again

```bash
pacman -Syu
```

Then install the required development tools and UCRT64 GCC toolchain:

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

---

## 7. Add MSYS2 UCRT64 to PATH

Add the following directory to the system `PATH`:

```text
C:\msys64\ucrt64\bin
```

Close the terminal and reopen it after modifying `PATH`.

---

## 8. Verify the C++ toolchain

Run the following commands in PowerShell:

```powershell
gcc --version
g++ --version
gdb --version
where.exe gcc
where.exe g++
```

---

## 9. Install the AI coding agent

Install OpenCode globally using npm:

```powershell
npm install -g @opencode/cli
```
