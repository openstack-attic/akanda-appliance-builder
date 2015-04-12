The files in this directory help to make test nocloud disk image:

genisoimage  -output seed.iso -volid cidata -joliet -rock user-data meta-data

You can test the image in kvm without OpenStack by invoking kvm like this:

kvm -m 1024 -curses -net nic,model=virtio,macaddr=52:54:00:12:34:56 \
 -net tap,ifname=tap0 \
-drive file=image.qcow2,if=virtio \
-drive file=seed.iso,if=virtio


