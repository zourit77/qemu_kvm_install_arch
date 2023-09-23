# qemu_kvm_install_arch
# commandes pour installer quemu kvm sur archlinux
sudo pacman -Syyy
sudo pacman -S qemu virt-manager virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat ebtables iptables libguestfs
sudo systemctl enable --now libvirtd.service
sudo usermod -a -G libvirt $(whoami)
sudo systemctl restart libvirtd.service

#démarrage du réseau virtuel
sudo virsh net-list --all
sudo virsh net-start default
sudo virsh net-autostart default
