
```shell
pacman install git
alias picard='/usr/bin/git --git-dir="$HOME/.picard/" --work-tree="/"'
picard clone --bare git@github.com:bofakin/picard-overlay.git .picard
picard config status.showUntrackedFiles no
picard checkout -f
```
