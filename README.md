# Prezto — Instantly Awesome Zsh
Prezto is the configuration framework for [Zsh][1]; it enriches the command line
interface environment with sane defaults, aliases, functions, auto completion,
and prompt themes.

This is my custom fork.

# New system setup
1. [Ubuntu based distro](#ubuntu-based-distro)
2. [OSX](#osx)

## Ubuntu based distro
> [!CAUTION]
> Only do the following if machine is yours

```bash
sudo groupadd gigachad
sudo usermod -aG gigachad $USER

sudo visudo
# Add following before @includedir, uncomment last line
# Allow gigachads to sudo passwdless
# %gigachad ALL=(ALL) NOPASSWD: ALL
```

```bash
sudo apt install zsh vim ranger w3m ncdu redshift neofetch tig htop btop ncal
sudo apt install openjdk-18-jre xclip konsole

# GNOME only
sudo apt install gnome-shell-extension-manager gir1.2-gtop-2.0 lm-sensors
```

### Update git
```
sudo add-apt-repository ppa:git-core/ppa -y
sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com A1715D88E1DF1F24 40976EAF437D05B5 3B4FE6ACC0B21F32 A6616109451BBBF2
sudo apt-get update
sudo apt-get install git -y
git --version
```

### Refind
> [!NOTE]
> Only needed if going run multiple operating systems on the same machine

[Docs](https://www.rodsbooks.com/refind/installing.html)

```
sudo apt-add-repository ppa:rodsmith/refind
sudo apt-get update
sudo apt-get install refind
```

### NVIDIA drivers
> [!CAUTION]
> Only if distro doesn't have them baked in OR GPU is too old

https://unix.stackexchange.com/questions/352828/how-to-switch-nvidia-driver-from-nouveau-to-nvidia-proprietary

---

## OSX
### Install
1. [brew](https://brew.sh/)

```bash
brew update
brew install ranger tig ncdu bash neofetch openssl@3 shellcheck htop w3m
brew install openssh libffi cmake yq ykman libu2f-udev pyenv vim btop

# better 'alt' tab for OSX
brew install --cask alt-tab
```

Installation
------------
Prezto will work with any recent release of Zsh, but the minimum required
version is 4.3.11.

```bash
zsh

git clone --recursive git@github.com:one-m1nd/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"

setopt EXTENDED_GLOB
for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
  ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
done


chsh -s /bin/zsh
```

In a new terminal window/tab

```bash
cd $ZPREZTODIR
git clone --recurse-submodules https://github.com/belak/prezto-contrib contrib
```

---

# Additional Installation
## Common
1. [rvm](https://rvm.io/)
   * `curl -sSL https://get.rvm.io | bash -s master`
   * `gem update --system`
2. [nvm](https://github.com/nvm-sh/nvm)
3. [pyenv](https://github.com/pyenv/pyenv)
4. [vundle](https://github.com/VundleVim/Vundle.vim)
5. [FiraCode Patched Font](https://www.nerdfonts.com/font-downloads)

## OSX
1. [iterm2](https://iterm2.com/index.html)

## Linux
Binaries/executables ... place in ~/bin

`mkdir "$HOME/bin"`

1. [rubymine](https://www.jetbrains.com/ruby/)
   * Fallback version `2023.2.8`
2. [obsidian](https://obsidian.md/)

Resources
---------
[Original docs](https://github.com/sorin-ionescu/prezto)

The [Zsh Reference Card][7] and the [zsh-lovers][8] man page are indispensable.

License
-------

This project is licensed under the MIT License.

[1]: http://www.zsh.org
[2]: http://i.imgur.com/nrGV6pg.png "sorin theme"
[3]: http://git-scm.com
[4]: https://github.com
[5]: http://gitimmersion.com
[6]: https://git.github.io/git-reference/
[7]: http://www.bash2zsh.com/zsh_refcard/refcard.pdf
[8]: http://grml.org/zsh/zsh-lovers.html
