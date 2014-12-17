# uio_pruss

Enable the PRU on BeagleBone Black with Kernel 3.18+

***IMPORTANT***: You have to enable the PRU in the device-tree before this module will do anything.

Getting the PRU running on newer kernels is a pain; `rproc` support hasn't landed yet, and the existing PRU module doesn't come with any of Robert's builds. Maybe one day the patch will make it upstream, but until then there's this module.

We include updated versions of existing patches to get this all working.

```sh
git clone https://github.com/izaakschroeder/uio_pruss.git uio_pruss
sudo dkms add uio_pruss
sudo dkms install uio_pruss/3.18.0
sudo modprobe uio_pruss
```

To check if it's working:

```sh
ls /sys/class/uio
```

Remember to autoload this module.

