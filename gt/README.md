# instructions for setting up gt

gt code only currently supports zsh, which is the default shell on MacOS. to adapt it to other shells, you'll mostly just need to change the array syntax wherever it's used. with zsh, you'll also get autocomplete; with other shells, your autocomplete won't work. by convention in this document we'll name the directory containing our scripts 'bin'. you can name it whatever you want. if you want the folder to be hidden, add a dot '.' before the name.

type the following commands in your terminal

```
cd
mkdir -p bin
cd bin
curl https://raw.githubusercontent.com/poiurewq/fun/refs/heads/main/gt/gt > gt
curl https://raw.githubusercontent.com/poiurewq/fun/refs/heads/main/gt/_gt_helper > _gt_helper
curl https://raw.githubusercontent.com/poiurewq/fun/refs/heads/main/gt/_gt > _gt
chmod u+x _gt_helper
```

then add the following lines to a file named `.zshrc` in your home directory, so its path would be: `~/.zshrc`

to open the file, you can type these lines:
```
vi ~/.zshrc
```

then type `GG` then `i` and copy & paste these lines into the file:
```
typeset -TU FPATH=$HOME/bin:$FPATH fpath
autoload gt
typeset -TU PATH=$HOME/bin:$PATH path
autoload -U compinit; compinit
```

then press the `Esc` button and type `:wq`

reload the shell by restarting terminal or typing `exec $SHELL`
