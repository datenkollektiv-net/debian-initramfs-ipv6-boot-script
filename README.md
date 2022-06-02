# debian-initramfs-ipv6-boot-script
Scripts to support IPv6 networking in Debian pre-boot (initramfs) environment 

_It is initial forked from https://gist.github.com/zajdee/65aad61f35d3a63c56c7d1cc76c22e14 (thanks @zadjee)_

## Usage

* Copy `debian-initramfs-ipv6-premount-script` to `/etc/initramfs-tools/scripts/init-premount/`
* Edit GRUB kernel boot parameter
```txt
# /etc/default/grub
# ...

GRUB_CMDLINE_LINUX="ipv6=addr=<address>/<netmask>,gw=<gateway>,iface=<interface>,forwarding=<0/1>,accept_ra=<0/1/2>"

# ...
```
* Update initramfs and grub
```sh
update-initramfs -u 
update-grub
```
