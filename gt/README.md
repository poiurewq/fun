# about

## purpose
**gt** defines, maintains, and **g**oes **t**o shortcuts to resources, whether they be files on your computer or links to websites. 

## "release" notes
currently, **gt** does not support opening links using your own browser. you can ask me to set it up for you in 5 minutes or you can wait for a generalized update that sets it up for you.

also, **gt** only currently supports zsh, which is the default shell on MacOS. to adapt it to other shells, you'll mostly just need to change the array syntax wherever it's used. with zsh, you'll also get autocomplete; with other shells, your autocomplete won't work. by convention in this document we'll name the directory containing our scripts 'bin'. you can name it whatever you want. if you want the folder to be hidden, add a dot '.' before the name.

# instructions for setting up gt

## step 1
type the following commands in your terminal

```
cd
mkdir -p bin
cd bin
curl https://raw.githubusercontent.com/poiurewq/fun/refs/heads/main/gt/gt > gt
curl https://raw.githubusercontent.com/poiurewq/fun/refs/heads/main/gt/_gt_helper > _gt_helper
curl https://raw.githubusercontent.com/poiurewq/fun/refs/heads/main/gt/_gt > _gt
curl https://raw.githubusercontent.com/poiurewq/fun/refs/heads/main/gt/gt_setup > gt_setup
chmod u+x _gt_helper
source gt_setup
```

## step 2
then add the following lines to a file named `.zshrc` in your home directory, so its path would be: `~/.zshrc`

to open the file, you can type these lines to open the file using the command-line file editor Vi:
```
vi ~/.zshrc
```

## step 3
then type `Gi` (you will not see the letters show up, these letters simply let you insert at the end of the file). then copy & paste these lines into the file:
```
typeset -TU FPATH=$HOME/bin:$FPATH fpath
autoload gt
typeset -TU PATH=$HOME/bin:$PATH path
autoload -U compinit; compinit
```

then press the `Esc` key and type `:wq`, which saves the file and quits the editor.

## step 4
reload the shell by restarting terminal or typing `exec $SHELL`

## step 5
type `gt` to start using the script!
