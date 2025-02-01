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
zshrc_file="$HOME/.zshrc"
if [ -z $(grep 'GT-PATH-SETUP' $HOME/.zshrc) ]; then
echo '# GT-PATH-SETUP' >> $zshrc_file
echo 'typeset -TU FPATH=$HOME/bin:$FPATH fpath' >> $zshrc_file
echo 'autoload gt' >> $zshrc_file
echo 'typeset -TU PATH=$HOME/bin:$PATH path' >> $zshrc_file
echo 'autoload -U compinit; compinit' >> $zshrc_file
fi
unset zshrc_file
exec $SHELL
```

## step 2
type `gt` to start using the script!

To start, you'll want to set up a few shortcuts to resources using the `gt -n` flag.

If you want to get the path to a file from Finder, toggle on the path view with the keyboard shortcut `Option-Command-P`, then right-click on the file name in the path that shows up at the bottom of the Finder window and choose `Copy <file> as Pathname`.

