# openwrt
OpenWRT patches for Black Swift board

Patches are intended to use with OpenWRT 14.07 r46155. To download it, use *svn co -r 46155 svn://svn.openwrt.org/openwrt/branches/barrier_breaker openwrt*

*patch -p0 &lt; bsb.patch* — adds Black Swift board to the list of targets. Run *touch target/linux/***/Makefile* after applying it.

*patch -p0 &lt; gpio-irq-728.patch* — GPIO IRQ support by GBert, https://github.com/GBert

*patch -p0 &lt; new_modules.patch* — kernel modules developed by Black Swift team

*patch -p0 &lt; new_files.patch* — avahi-daemon and uboot-envtools configuration files

*patch -p0 &lt; mjpg-fix.patch* — fix Cambozola package md5 sum (needed for mjpg-streamer)

*patch -p0 &lt; mjpg-enable.patch* — enable mjpg_streamer service by default

*patch -p0 &lt; mjpg-nohotplug.patch* — disable mjpg_streamer in /etc/hotplug.d/usb/ (not included in stock firmware)

*patch -p0 &lt; console.patch* — patch to allow to completely disable UART console using bootloader's environment variable. Must be re-applied after *make clean* and must be preceeded with *make kernel_menuconfig*

*patch -p0 &lt; opkg.patch* — add Black Swift's repository (http://files.black-swift.com/files/openwrt/bbreaker/1.0/packages/) to /etc/opkg.conf

*.config* — ready to use OpenWRT Buildroot configuration file

For more details, please visit http://www.black-swift.com/wiki
