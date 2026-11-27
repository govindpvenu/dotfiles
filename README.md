# Dotfiles

Personal development environment configuration and setup notes.

## Setup

### 1. Back up or restore GNOME settings

Export all GNOME settings to a file:

```sh
dconf dump / > gnome.dconf
```

Restore GNOME settings from that file:

```sh
dconf load / < gnome.dconf
```

To export or restore **only GNOME keyboard bindings**, use:

```sh
# Export
dconf dump /org/gnome/settings-daemon/plugins/media-keys/ > gnome-custom-keybindings.dconf
dconf dump /org/gnome/desktop/wm/keybindings/ > gnome-wm-keybindings.dconf
dconf dump /org/gnome/shell/keybindings/ > gnome-shell-keybindings.dconf
dconf dump /org/gnome/mutter/keybindings/ > gnome-mutter-keybindings.dconf

# Restore
dconf load /org/gnome/settings-daemon/plugins/media-keys/ < gnome-custom-keybindings.dconf
dconf load /org/gnome/desktop/wm/keybindings/ < gnome-wm-keybindings.dconf
dconf load /org/gnome/shell/keybindings/ < gnome-shell-keybindings.dconf
dconf load /org/gnome/mutter/keybindings/ < gnome-mutter-keybindings.dconf
```

### 2. Install GNOME extensions

Recommended:

- Space Bar
- AppIndicator and KStatusNotifierItem Support

Optional:

- Screen Time
- System Monitor

Export GNOME extension settings:

```sh
dconf dump /org/gnome/shell/extensions/ > gnome-extensions.txt
```

Restore GNOME extension settings:

```sh
dconf load /org/gnome/shell/extensions/ < gnome-extensions.txt
```

### 3. Install Fish

```sh
sudo dnf install fish
```

Set Fish as the default shell:

```sh
chsh -s "$(which fish)"
```

Log out and back in for the change to take effect.

### 4. Install FiraCode Nerd Font

Download and install the patched font:

```sh
mkdir -p ~/.local/share/fonts/FiraCodeNerd
cd ~/.local/share/fonts/FiraCodeNerd
wget https://github.com/ryanoasis/nerd-fonts/releases/latest/download/FiraCode.zip
unzip FiraCode.zip
rm FiraCode.zip
fc-cache -fv
```

### 5. Install Starship

```sh
curl -sS https://starship.rs/install.sh | sh
```

### 6. Configure Starship in Fish

Ensure the Fish configuration directory and file exist:

```sh
mkdir -p ~/.config/fish
touch ~/.config/fish/config.fish
```

Open `~/.config/fish/config.fish` in Nano:

```sh
nano ~/.config/fish/config.fish
```

Add the following configuration:

```fish
set -U fish_greeting

if status is-interactive
    # Commands to run in interactive sessions can go here
end

starship init fish | source
```

Reload the Fish configuration, or restart your terminal:

```fish
source ~/.config/fish/config.fish
```
