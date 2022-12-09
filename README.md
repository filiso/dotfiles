## ZSH and prezto

ZSH should be installed with Ubuntu.

To install prezto follow installation steps 1-3 from https://github.com/sorin-ionescu/prezto :

Run *zsh* without creating the .zshrc file.

> ```
> zsh
> ```
> ```
> git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
> ```
> ```
> setopt EXTENDED_GLOB
> for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
> ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
> done
> ```

Set Zsh as default shell (might not work on work workstations):

> ```
> chsh -s /bin/zsh
> ```

### setup a git repo in $HOME

Based on:

https://news.ycombinator.com/item?id=11070797

https://www.atlassian.com/git/tutorials/dotfiles

Start at **Install your dotfiles onto a new system**. Directory *.cfg* replaced with *.dotfiles*

> ```
> alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
> ```

Instead of the listed command use (single >):

> ```
> echo ".dotfiles" > .gitignore
> ```

> ```
> git clone --bare https://github.com/filiso/dotfiles $HOME/.dotfiles
> ```

Remove the files created by prezto:

> ```
> rm ~/.zprezto/runcoms/zpreztorc ~/.zprezto/runcoms/zshrc
> ```

> ```
> config checkout
> ```

> ```
> config config --local status.showUntrackedFiles no
> ```

Use *config* instead of *git* in the home dir, e.g.:

> ```
> config status
> config add .xxx
> ```

### hist-subst-search and syntax highlighting

git clone the following into $HOME/programs

- https://github.com/zsh-users/zsh-history-substring-search
- https://github.com/zsh-users/zsh-syntax-highlighting



## Install

- Guake / Yakuake
  - set zsh as the default shell.
- Tmux
- Neovim
  - follow my github guide
- fzf
- Anaconda
  - either don't do the automated config at the end of installation or revert the .zshrc changes back to those from repo (dependent on $HOME, not fixed path)

## Additional config files

- Typora
  - go to .config/Typora/themes
  ```
  cp github.css github.user.css
  ```
  - in the #write section add:
  ```
  max-width: 1100 px;
  text-align: justify;
  ```
