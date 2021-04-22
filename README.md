# KVM_GVTg_VM
Windows VM running on Qemu/KVM with cpu pinning, GVTg passthrought and hypervisor hydden grom the guest.

# Host setup
Assuming the host has never been set up for running a VM.

1) Kernel modules
    Add:
        kvmgt
        vfio-iommu-type1
        vfio-mdev
    to /etc/modules
    Rebuild initramfs: sudo update-initramfs -u

2) Boot parameters
    Copy boot parameters grom "grub" file to /etc/default/grub
    update the bootloader: sudo update-grub

3) Libvirtd permissions
    add kvm and libvirtd-q to the root group 

4) Gvtg hook
    copy the content of "qemu" in /etc/libvirtd/hooks/qemu
    make the hook executable: sudo chmod +x /etc/libvirtd/hooks/qemu

# Guest setup

1) First Boot, Windows install


