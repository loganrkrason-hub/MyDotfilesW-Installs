# MyDotfilesW-Installs

Here are the commands to install the required packages depending on your Linux distribution.

### 📦 Ubuntu / Debian / Mint (apt)
Run the following command to update your system and install the tools:
```bash
sudo apt update && sudo apt install -y git curl neovim tmux htop
```

### 🏔️ Arch Linux (pacman)
Run this command to sync repositories and install the base tools:
```bash
sudo pacman -Syu firefox Thunar wezterm hyprland hyprpaper quickshell 
```

### ⚡ Arch AUR Packages (yay)
If you are on Arch and use the AUR, use this command for external packages:
```bash
yay -S codium elephant-desktopapplications-bin elephant-providerlist-bin elephant-calc-bin elephant-files-bin elephant-windows-bin
```

### 🎩 Fedora (dnf)
Run this command to update and install the packages:
```bash
sudo dnf upgrade --refresh -y && sudo dnf install -y git curl neovim tmux htop
```
