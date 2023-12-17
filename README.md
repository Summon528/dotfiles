# dotfiles
```
echo "[interop]
  appendWindowsPath = false" | sudo tee -a /etc/wsl.conf
```

```
sudo zypper -n ref
sudo zypper -n in gh
gh auth login

sudo zypper -n in neovim zsh nodejs bat cargo python3-pip eza npm gcc make gcc-c++ tmux gdb gh fzf
sudo npm i -g corepack

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" "" --unattended
yes | LV_BRANCH='release-1.3/neovim-0.9' bash <(curl -s https://raw.githubusercontent.com/LunarVim/LunarVim/release-1.3/neovim-0.9/utils/installer/install.sh)
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

git init --bare ~/.dotfiles
git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME remote add origin https://github.com/Summon528/dotfiles.git
git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME fetch origin dot
git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME checkout -f dot
git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME config status.showUntrackedFiles no
git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME submodule init
git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME submodule update
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
chsh -s /usr/bin/zsh

exec zsh
```

