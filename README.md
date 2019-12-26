dotfiles-moi
---

A simple dotfiles managed using [chezmoi](https://www.chezmoi.io/).
To start hacking, simply run:
```
chezmoi init https://github.com/archbung/dotfiles-moi.git
```

# dracut and pacman

If using dracut on Arch Linux, you may need to create a pacman hook to regenerate initramfs and copy the new kernel to its appropriate location [[1]](https://wiki.archlinux.org/index.php/User:Krathalan).
Simply create a [pacman](https://wiki.archlinux.org/index.php/Pacman) hook e.g. `/etc/pacman.d/hooks/90-dracut-linux-zen.hook` as follows:
```
[Trigger]
Type = File
Operation = Install
Operation = Upgrade
Target = usr/lib/modules/*/pkgbase

[Action]
Description = Updating linux-zen initramfs...
When = PostTransaction
Exec = /home/username/.local/bin/90-dracut-linux-zen.script
NeedsTargets
```

Don't forget to replace `username` with your user name.
