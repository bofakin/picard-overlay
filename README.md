
# Copy Overlay
```shell
pacman install git
alias picard='/usr/bin/git --git-dir="$HOME/.picard/" --work-tree="/"'
picard clone --bare git@github.com:bofakin/picard-overlay.git .picard
picard config status.showUntrackedFiles no
picard checkout -f
```

# Activate services
```shell
systemctl enable picard-tc358743@0.service
systemctl enable picard-tc358743@1.service
```

# Push from kvmd workspace
```shell
DOCKER='sudo docker' make regen
rsync -rP kvmd/ root@192.168.178.105:/usr/lib/python3.13/site-packages/kvmd/
rsync -rP --exclude="*.pug" web/ root@192.168.178.105:/usr/share/kvmd/web/
```
