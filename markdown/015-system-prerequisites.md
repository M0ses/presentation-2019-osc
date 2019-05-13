<!-- .slide: data-state="normal" id="system-prerequisites" data-menu-title="System prerequisites" data-timing="20s"-->
# System prerequisites

* Laptop (ideally with installed opensuse)
  * approx.  20GB free disk space / ideally 70GB
  * at least 4G RAM
  * at least 2 free VCPUs
* (optional if laptop with opensuse) 1 VM for Developer Setup
* (optional) required for Server Setup


<!-- .slide: data-state="normal" id="nested-kvm" data-menu-title="Nested Virtualization" data-timing="20s"-->
## Nested Virtualization for Installation in VM

### Intel

```
cat /sys/module/kvm_intel/parameters/nested

# In /etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT=".... kvm-intel.nested=1"
```

### AMD

```
cat /sys/module/kvm_amd/parameters/nested
# In /etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT=".... kvm-amd.nested=1"
```
