## uvc-gadget

Forked from and following the tutorial from here: http://www.davidhunt.ie/raspberry-pi-zero-with-pi-camera-as-usb-webcam/

### Build

```bash
git clone ...
make
```

### Install

Install and enable the systemd service. The paths in the .service file might need adjustment depending on where the checkout is
```bash
sudo cp piwebcam.service /etc/systemd/system/
sudo systemctl enable piwebcam
```

### Configure Raspian

Add the following to the end of the arguments in `/boot/cmdline.txt` on the sd-card:
```
modules-load=dwc2,libcomposite
```

Add the following line to `/boot/config.txt` on the sd-card:
```
dtoverlay=dwc2
```
