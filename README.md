# raspa2dptry
raspa2dptry

Raspbian 2018 03 13 Fresh install

sudo nano /etc/apt/sources.list
uncomment #deb-src -> deb-src

sudo nano /etc/apt/sources.list.d/raspi.list
uncomment #deb-src -> deb-src

sudo apt-get update
sudo apt-get upgrade

sudo reboot

sudo apt-get update
sudo apt-get build-dep bluealsa

sudo git clone https://github.com/raspberrypi-ui/bluealsa

cd bluealsa
sudo autoreconf --install
sudo mkdir build && cd build
sudo ../configure --enable-debug

sudo make && make install


sudo killall bluealsa
sudo bluealsa
