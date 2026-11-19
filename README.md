# dotfiles
My developer environment dotfiles

# 0. Set-up glazewm and yasb at first to work in peace later on
winget install glzr-io.glazewm
winget install --id AmN.yasb

# 1. Set of terminal commands to run :-
winget install glzr-io.glazewm
winget install --id AmN.yasb
winget install --id Git.Git --exact --source winget
git config --global user.name "<your github user name>"
git config --global user.email "<your github user email>"
winget install -e --id tree-sitter.tree-sitter-cli # neovim pre-requisite
winget install --id Neovim.Neovim --exact --version 0.12.0
git clone https://github.com/RonitPaul19/nvim.git "$env:LOCALAPPDATA\nvim"

# 2. Close terminal reopen it and check if git and neovim are installed properly using :-
git --version
git config --global --list
nvim --version

# 3. Set of terminal commands to run :-
Install-Module PSReadLine -Force
winget install --id Starship.Starship --exact --source winget
winget install --id junegunn.fzf --exact --source winget
winget install --id BurntSushi.ripgrep.MSVC --exact --source winget
winget install --id sharkdp.fd --exact --source winget
winget install --id ajeetdsouza.zoxide --exact --source winget
winget install --id eza-community.eza --exact --source winget
winget install --id marlocarlo.psmux --exact --source winget

# 4. Close terminal reopen it and check if all software are installed properly using :-
starship --version
fzf --version
rg --version
fd --version
zoxide --version
eza --version
winget install --id OpenJS.NodeJS.LTS --exact --source winget
node --version
npm --version

# 5. Set of commands to install developer tech stack (NodeJS, Python, C++)
winget install --id OpenJS.NodeJS.LTS --exact --source winget
winget install --id Python.Python.3.14 --exact --source winget
winget install --id MSYS2.MSYS2 --exact --source winget

# 6. add "C:\msys64\ucrt64\bin" in system variables path

# 7. Close terminal reopen if and check if c++ entire stack is installed properly using :-
gcc --version
g++ --version
gdb --version
which gcc
which g++

# 8. Install A.I. coding agent (opencode)
npm install --global opencode-ai

