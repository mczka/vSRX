# iPXE VM for netboot
Alpinelinux/IPv4/IPv6/PXE/HTTP/TFTP/DHCP

run the VM ISO https://dl-cdn.alpinelinux.org/alpine/v3.15/releases/x86_64/alpine-virt-3.15.4-x86_64.iso

setup-alpine sys mode

reboot

apk update

test -d /sys/firmware/efi && echo UEFI || echo BIOS

adduser -h /home/alpine -s /bin/ash alpine

apk add sudo 
echo '%wheel ALL=(ALL) ALL' > /etc/sudoers.d/wheel

or

apk add doas htop

cat <<EOF >> /etc/doas.d/doas.conf
permit nopass :wheel as root
EOF

adduser alpine wheel

echo 'alpine ALL=(ALL:ALL) NOPASSWD: ALL' > /etc/sudoers.d/alpine

wget https://github.com/mczka.keys >> ~/.ssh/authorized_keys

lock and disable root

$ sudo passwd -l root
$ sudo passwd -d root

Nano is a text editor that's useful
apk add nano
## enable repo community
nano /etc/apk/repositories

install and config nginx/http, tftp and build iPXE

cd /opt

wget script

chmod +x script

./script
