grep -E --color '(vmx|svm)' /proc/cpuinfo

lsmod | grep -i kvm

sudo dnf install -y qemu-kvm libvirt virt-install bridge-utils

sudo dnf install -y virt-manager

sudo dnf install -y libvirt-devel virt-top libguestfs-tools guestfs-tools

sudo systemctl start libvirtd

sudo systemctl enable libvirtd

nmcli connection show

sudo nmcli connection add type bridge autoconnect yes con-name br0 ifname br0

sudo nmcli connection modify br0 ipv4.addresses 192.168.1.189/24 gw4 192.168.1.1 ipv4.method manual

sudo nmcli connection modify br0 ipv4.dns 192.168.1.1

sudo nmcli connection del static-fedora

sudo nmcli connection add type bridge-slave autoconnect yes con-name enp0s3 ifname enp0s3 master br0

sudo nmcli connection up br0

nmcli connection show br0

ip add show br0

Related link :
[KVM nstallation on Fedora](https://www.linuxtechi.com/how-to-install-kvm-on-fedora-step-by-step/)
[what is libvirt](https://linuxconfig.org/how-to-use-bridged-networking-with-libvirt-and-kvm)
