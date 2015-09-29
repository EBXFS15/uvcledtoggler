# MODIFIED UVCVIDEO DRIVER

In orer to have an insight into the details of the UVCVIDEO driver a measurement procedure has been defined (see EyeTrackerQT project). This project includes all soruces needed to get a modified UVCVIDEO driver that could be used in combination with th e EyeTrackerQT project.

Preconditions is:
* Hardware: EBX-BBB-KIT with Chipsee board
* Lab1 (LAB 1-1 Embedded Linux Configuration - Ubuntu 14.04 LTS) done.


# Option 1
* Copy the uvcvideo.ko to the folder of your choice on the target
* Copy the ebx_Monitor.ko from (https://github.com/EBXFS15/ebx_monitor) to the same folder
* Load first the ebx_monitor.ko and then the uvcvideo.ko.
* The green and blue light shall be turned on after the insmod procedrue has finished.

# Option 2
* copy the files to the following folder:
/opt/embedded/bbb/kernel/linux-dev-am33x-v3.18/drivers/media/usb/uvc
* then run make at the following location:
/opt/embedded/bbb/kernel/linux-dev-am33x-v3.18/make
* to save time and build only the specific driver use the following command:
make SUBDIRS=drivers/media/usb/uvc modules
* Now take the uvcvideo.ko from /opt/embedded/bbb/kernel/linux-dev-am33x-v3.18/drivers/media/usb/uvc and follow the option 1 from above.

# Option 3
* Instead of taking the uvcvideo.ko from /opt/embedded/bbb/kernel/linux-dev-am33x-v3.18/drivers/media/usb/uvc repeat the steps from section 2.17 of the lab 1-1
* Now the driver is the default driver on your board.
* The green light shall be turned on after the reboot of the board and if the uvcvideo is loaded (if webcam is plugged in).
* As soon you load the ebx_monoitor.ko and you start to capture from the webcam the blue ligth will be turned on.


