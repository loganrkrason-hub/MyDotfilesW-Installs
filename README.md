# MyDotfilesW-Installs

Here are the commands to install the required packages depending on your Linux distribution.

### 📦 Ubuntu / Debian / Mint (apt)

1. **Install Core & Desktop Packages:**
   ```bash
   sudo apt update && sudo apt upgrade -y && sudo apt install -y firefox thunar git curl neovim fastfetch fonts-noto-color-emoji
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
4.  **Hyprland and the hyprecosystem is not intended for Ubuntu, Debian, or Mint**
   ```bash
   sudo add-apt-repository universe && sudo apt update && sudo apt install -y hyprland hyprpaper
   ```
5.  **Install Quickshell**
   ```bash
   sudo add-apt-repository ppa:avengemedia/danklinux -y
   sudo apt update && sudo apt install -y quickshell
   ```
### 🏔️ Arch Linux (pacman)
Run this command to sync repositories and install the base tools:
```bash
sudo pacman --needed -Syu firefox thunar wezterm hyprland hyprpaper quickshell git curl neovim fastfetch noto-fonts-emoji
```

### ⚡ Arch AUR Packages (yay)
If you are on Arch and use the AUR, use this command for external packages:
```bash
yay -S codium elephant-desktopapplications-bin elephant-providerlist-bin elephant-calc-bin elephant-files-bin elephant-windows-bin walker
```
if you use paru use this:
```bash
paru -S codium elephant-desktopapplications-bin elephant-providerlist-bin elephant-calc-bin elephant-files-bin elephant-windows-bin
```
if you dont have yay or paru, you get yay. To do that run:
```bash
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```
## 🎩 Fedora (dnf) Installation

Fedora provides modern, bleeding-edge packages natively. To install the core tools along with the Wayland ecosystem components, run these setup steps:

### 1. Enable Third-Party Repositories (Copr & VSCodium)
Because VSCodium and Quickshell are not in the default Fedora repositories, you need to enable their external package registries first:

```bash
# Add the VSCodium Repository
sudo rpm --import https://gitlab.com
sudo sh -c 'echo -e "[vscodium]\nname=vscodium\nbaseurl=https://vscodium.com\nenabled=1\ngpgcheck=1\ngpgkey=https://gitlab.com" > /etc/yum.repos.d/vscodium.repo
copr enable errornointernet/walker'

# Enable the Copr repository for Quickshell
sudo dnf copr enable -y alternateved/quickshell
```

### 2. Install All Core Applications & Wayland Desktop Components
Run this single terminal string to fully upgrade the package tracker and install everything natively via `dnf`:

```bash
sudo dnf upgrade --refresh -y && \
sudo dnf install -y firefox thunar wezterm hyprland hyprpaper quickshell git curl codium neovim fastfetch walker elephant google-noto-emoji-fonts
```

### 3. Note for Elephant Plugins (`elephant-...`)
* The `elephant-*-bin` applications are wrapped explicitly for Arch Linux's packaging ecosystem. 
* To run the Elephant plugin backend (for launchers like `walker`) on Fedora, you will need to install the Go development kit (`sudo dnf install golang`) and compile the source code directly from the [Elephant Upstream Git](https://github.com) repository.
