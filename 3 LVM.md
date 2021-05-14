1.LVM stands for Logical Volume Management.

2.It is a storage device management technology that gives users the power to pool and abstract the physical layout of component storage devices for easier and flexible administration.

3.The storage structure for the LVM can be given as following :

a) Linux Partitions

b) Physical Volumes - Physical block devices or other disk-like devices (for example, other devices created by device mapper, like RAID arrays) are used by LVM as the raw building material for higher levels of abstraction. Physical volumes are regular storage devices. LVM writes a header to the device to allocate it for management.

c) Volume Groups - LVM combines physical volumes into storage pools known as volume groups. Volume groups abstract the characteristics of the underlying devices and function as a unified logical device with combined storage capacity of the component physical volumes.
	
d) Logical Volumes - A volume group can be sliced up into any number of logical volumes. Logical volumes are functionally equivalent to partitions on a physical disk, but with much more flexibility. Logical volumes are the primary component that users and applications will interact with.

4.Commands for the LVM are as following:

1.pvcreate => to create a physical volume 

2.pvdisplay => to display the physical volume

3.vgcreate vgname[pv] => to create a volume group
	
4.vgdisplay => to display the volume group
	
5.lvcreate -n name -L[size] name =>to create a logical volume 
	
6.lvdisplay => to display the logical volume
