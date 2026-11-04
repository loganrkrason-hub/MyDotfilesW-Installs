# MyDotfilesW-Installs

Here are the commands to install the required packages depending on your Linux distribution.

### 📦 Ubuntu / Debian / Mint (apt)

1. **Install Core & Desktop Packages:**
   ```bash
   sudo apt update && sudo apt upgrade -y && sudo apt install -y firefox thunar git curl
   ```

2. **Install WezTerm:**
   ```bash
   curl -fsSL https://fury.io | sudo gpg --yes --dearmor -o /usr/share/keyrings/wezterm-fury.gpg
   echo "deb [signed-by=/usr/share/keyrings/wezterm-fury.gpg] https://fury.io * *" | sudo tee /etc/apt/sources.list.d/wezterm.list
   sudo apt update && sudo apt install wezterm
   ```

3. **Install VSCodium:**
   ```bash
   wget -qO - https://gitlab.com | gpg --dearmor | sudo tee /usr/share/keyrings/vscodium.gpg > /dev/null
   echo 'deb [ signed-by=/usr/share/keyrings/vscodium.gpg ] https://vscodium.com vscodium main' | sudo tee /etc/apt/sources.list.d/vscodium.list
   sudo apt update && sudo apt install codium
   ```

### 🏔️ Arch Linux (pacman)
Run this command to sync repositories and install the base tools:
```bash
sudo pacman --needed -Syu firefox Thunar wezterm hyprland hyprpaper quickshell git curl
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
