# Instalacion de bspwm y sxhkd

sudo apt install build-essential git vim xcb libxcb-util0-dev libxcb-ewmh-dev libxcb-randr0-dev libxcb-icccm4-dev libxcb-keysyms1-dev libxcb-xinerama0-dev libasound2-dev libxcb-xtest0-dev libxcb-shape0-dev
sudo apt install bspwm sxhkd

mkdir ~/.config/bspwm
mkdir ~/.config/sxhkd

cp -r bspwm/ ~/.config/bspwm
cp -r sxhkd/ ~/.config/sxhkd

sudo apt install polybar
sudo apt install libconfig-dev libdbus-1-dev cmake libegl-dev libev-dev libgl-dev libepoxy-dev libpcre2-dev libpixman-1-dev libx11-xcb-dev libxcb1-dev libxcb-composite0-dev libxcb-damage0-dev libxcb-glx0-dev libxcb-image0-dev libxcb-present-dev libxcb-randr0-dev libxcb-render0-dev libxcb-render-util0-dev libxcb-shape0-dev libxcb-util-dev libxcb-xfixes0-dev meson ninja-build uthash-dev

git clone https://github.com/yshui/picom ../picom
cd ../picom
meson setup --buildtype=release build
ninja -C build
sudo ninja -C build install
sudo apt install rofi kitty feh
cd /usr/share/local/fonts
sudo wget https://github.com/ryanoasis/nerd-fonts/releases/download/v3.3.0/Hack.zip
7z x Hack.zip
rm Hack.zip README.md LICENSE.md
sudo apt install zsh
cd /opt
sudo apt remove kitty
sudo wget https://github.com/kovidgoyal/kitty/releases/download/v0.37.0/kitty-0.37.0-x86_64.txz
sudo 7z x kitty-0.37.0-x86_64.txz
sudo rm kitty-0.37.0-x86_64.txz
sudo mkdir kitty
mv kitty-0.37.0-x86_64.tar kitty
cd kitty
sudo tar -xf kitty-0.37.0-x86_64.tar
cd / 
sudo chown -R $USER:$USER opt/
