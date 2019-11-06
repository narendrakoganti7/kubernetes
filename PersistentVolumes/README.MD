### Persistent Volumes and Persistent volumes claim



### nfs method

first attach disk in to vm in my case gcp.

* edit vm settings and add persistence disk
* format diks using blow command 

   `mkfs.ext4 -m 0 -F -E lazy_itable_init=0,lazy_journal_init=0,discard /dev/` 
 * create new directory using `mkdir`  and `chmod a+w /folder/directory`
 * Disk add into mount point 
 `mount -o discard,defaults /dev/sdb /folder/directory`
 
 * List uuid for disk `blkid /dev/DEVICE_ID`
 
      /dev/sdb: UUID="bcb96eef-e934-43fd-b9bb-eab306cda86b" TYPE="ext4"
  * add to /etc/fstab uuid and directory name and mount point type

  