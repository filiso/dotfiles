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

Set Zsh as default shell (might not work on work workstations; in this case set it in Guake):

> ```
> chsh -s /bin/zsh
> ```

### hist-subst-search and syntax highlighting

git clone the following into $HOME/opt

- https://github.com/zsh-users/zsh-history-substring-search
- https://github.com/zsh-users/zsh-syntax-highlighting
- https://github.com/zsh-users/zsh-autosuggestions
