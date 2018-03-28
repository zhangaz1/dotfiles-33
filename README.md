<p align="center" >
	<img src="header.png" alt="dotfiles" title="dotfiles" width="600">
</p>

This repository contains files for configuring my Terminal environment and other various macOS settings.

## Maintaining macOS setup

Symlinks are managed with GNU Stow (installed with Homebrew). Files you wish to be symlinked to the home directory need to be placed in a folder within `~/dotfiles`. Using the `stow` command from the `~/dotfiles` directory will symlink the contents of the folder you choose (`/bash`, `/vim`, etc) to the grandparent directory, which is wherever the `/dotfiles` folder is contained.

Assuming you clone the dotfiles repository in your home directory, executing the commands:

```bash
$ cd ~/dotfiles
$ stow bash
```
will symlink the contents of `dotfiles/bash` to the home directory, which is currently `.bash_profile` and `.bashrc`

You can use the `stow` command anytime you add a new file to a folder you wish to symlink directly to the home directory. You do not need to delete existing files or symlinks; GNU Stow will overwrite them automatically. This can all be done without Stow using the `ln -s` command, but I find Stow with folder management to be cleaner and easier to maintain.


## How it Works

`.bash_profile` automatically sources configurations defined in the files contained in the main /dotfiles folder. Any file beginning with `.` will automatically be sourced.
