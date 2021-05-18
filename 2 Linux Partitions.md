1.INTRODUCTION
	
There are two type of chips for the motherboard, i.e

1.BIOS
	
2.UFI
	
There are diffrent partion methods for these two diffrent chips.Basically the storage is divided into two parts known as Primary Partition & Extended Partition.Primary partition basically contains the booting files and the extended partion contains storage files for the other data to store.
	
=>For BIOS,Master Boot Record (MBR) method is used which have MSDOS as labels.In this,primary partitions are followed by the extended partitions & after the extended partition the primary partition cannot be placed.
	
=>For UFI,GUID Partition Table (GPT) method is used.

2.STEPS TO CREATE PARTIOTIONS
	
To create the partion for the storage we have to follow certain set of steps.
		
STEP 1.List out the partitions present on the current system.
			
To list the partiotions will use the ``command parted -l``.After executing the command successfully there will be output as following -

	Model: Virtio Block Device (virtblk)
	Disk /dev/vda: 106GB
	Sector size (logical/physical): 512B/512B
	Partition Table: msdos
			
Disk Flags: 

	Number  Start   End    Size   Type     File system  Flags
 	1      1049kB  105GB  105GB  primary  ext4         boot

STEP 2.In the second step we have to label the partition.
			
For this we have to first enter ``/dev/vdb`` to enable the GNU interface,then we have to fire the command ``mklabel msdos``.When we enter this command the partion will be labeled as following :
	 
	        Disk /dev/vdb: 21.5GB
		Sector size (logical/physical): 512B/512B	
		Partition Table: msdos
		
STEP 3.Now we have to make the partition.
			
To make partition we will use first ``/dev/vdb`` to enable GNU and the further steps are as following :
			        
				[root@7f972e2e8c88 ~]# parted /dev/vdb
				GNU Parted 3.1
				Using /dev/vdb
				Welcome to GNU Parted! Type 'help' to view a list of commands.
				(parted) mkpart                                                           
				Partition type?  primary/extended? extended                               
				Start? 2048s                                                              
				End? 30%                                                                  
				(parted) quit 
					
After we Enter GNU will type the command ``mkpart`` to make partition then it will ask for partition type .after entering the partition type we have to select starting point of the partition then have to select the endpoint or we can simply enter percentage of disk we want to parted.Then enter `quit` command to exit.
		
STEP 4.Now let the partion be settled/created.
			
We have to let the partition to be created/settled for some time as it requires some time.If other actions are performed during the settlement of the partiton the storage may get corrupted.
        Use command `udevadm settle` for this.
		
		
STEP 5.In the step 5 we have to attach file system to the partition & format file system with XFS file system.
			
Use command ``mkfs.xfs /dev/vdb1`` this will show the metadata.
		
STEP 6.Create a mount point directory for the partition.
			
Use command `mkdir /archieve`
		
STEP 7.We have to add entry in fstab because if mount is created & the system is rebooted then it may earase so create entry in fstab.
			
=>To get UUID use command `Lsblk --fs /dev/vdb`
			
=>To make entry in fstab use ``vi /etc/fstab`` and then enter the UUID & other deatails.
		
STEP 8.In step 8 we have to restart the daemon service using command ``systemctl daemon-reload``
		
STEP 9.Now we have to mount the partition on the directory.
			Use command ``df -h`` to check whether directory is mounted or not.
		

