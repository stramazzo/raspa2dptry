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
sudo nano ~/.asoundrc
defaults.bluealsa.interface "hci0"
defaults.bluealsa.device "00:21:98:00:05:B4"
defaults.bluealsa.profile "a2dp"
defaults.bluealsa.delay 10000

sudo bluealsa

altro terminale
bluetoothctl
ping 00:21:98:00:05:B4
trust 00:21:98:00:05:B4
connect 00:21:98:00:05:B4

altro terminale

cd ~
aplay /usr/share/sounds/alsa/Noise.wav
aplay -D bluealsa:HCI=hci0,DEV=00:21:98:00:05:B4,PROFILE=a2dp /usr/share/sounds/alsa/Noise.wav
