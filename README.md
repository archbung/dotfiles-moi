dotfiles-moi
---

A simple dotfiles managed using [chezmoi](https://www.chezmoi.io/).
To start hacking, simply run:
```
chezmoi init https://github.com/archbung/dotfiles-moi.git
```

# dracut and pacman

If using dracut on Arch Linux, you may want to create pacman [hooks](https://wiki.archlinux.org/index.php/Dracut#Generate_a_new_initramfs_on_kernel_upgrade) to regenerate initcpios and copy new kernels to its appropriate location automatically.
Note that in this repo, the scripts are in `$HOME/.local/bin` by default, instead of `/usr/local/bin`.
