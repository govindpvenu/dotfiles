## Setup FiraCode Nerd Font

###### Download Patched Font:

    mkdir -p ~/.local/share/fonts/FiraCodeNerd
    cd ~/.local/share/fonts/FiraCodeNerd
    wget https://github.com/ryanoasis/nerd-fonts/releases/latest/download/FiraCode.zip
    unzip FiraCode.zip
    rm FiraCode.zip

###### Refresh font cache:

    fc-cache -fv

###### Verify Nerd Font is installed:

    fc-list | grep -i "FiraCode"
