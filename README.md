# raspa2dptry
raspa2dptry

sudo nano /etc/apt/sources.list
uncomment #deb-src -> deb-src

sudo nano /etc/apt/sources.list.d/raspi.list
uncomment #deb-src -> deb-src

sudo apt-get update
sudo apt-get upgrade

sudo apt-get build-dep bluealsa

sudo apt-get install dh-autoreconf
sudo apt-get build-dep bluealsa

sudo apt-get install libasound2-dev
sudo git clone https://github.com/raspberrypi-ui/bluealsa
cd bluealsa
sudo autoreconf --install
sudo mkdir build && cd build
sudo ../configure --enable-aac --enable-debug

