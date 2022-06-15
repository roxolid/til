#

[Mounting a raw partition file made with dd or dd_rescue in Linux](https://major.io/2010/12/14/mounting-a-raw-partition-file-made-with-dd-or-dd_rescue-in-linux/)

```
# fdisk -l harddrive.img
                    Device Boot      Start         End      Blocks   Id  System
harddrive.img                *          63    33640109    16820023+  83  Linux

# mount -o ro,loop,offset=32256 harddrive.img /mnt/loop
# mount | grep harddrive.img
/root/harddrive.img on /mnt/loop type ext3 (ro,loop=/dev/loop1,offset=32256)
```

Start * size_of_sector (usually 512)

```
# fdisk -l /run/media/rox/BAKPLUZ/LIBRARY/orcl/work/equipment/notebook/t490/m2_nvme_256gb.img
Disk /run/media/rox/BAKPLUZ/LIBRARY/orcl/work/equipment/notebook/t490/m2_nvme_256gb.img: 238.47 GiB, 256060514304 bytes, 500118192 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: gpt
Disk identifier: E9042240-166E-469A-9D4A-C90213AAA038

Device                                                                                 Start       End   Sectors   Size Type
/run/media/rox/BAKPLUZ/LIBRARY/orcl/work/equipment/notebook/t490/m2_nvme_256gb.img1     2048  14682111  14680064     7G Windows recovery environment
/run/media/rox/BAKPLUZ/LIBRARY/orcl/work/equipment/notebook/t490/m2_nvme_256gb.img2 14682112  15214591    532480   260M EFI System
/run/media/rox/BAKPLUZ/LIBRARY/orcl/work/equipment/notebook/t490/m2_nvme_256gb.img3 15214592  15476735    262144   128M Microsoft reserved
/run/media/rox/BAKPLUZ/LIBRARY/orcl/work/equipment/notebook/t490/m2_nvme_256gb.img4 15476736 500118157 484641422 231.1G Microsoft basic data
[root@balvan ~]# umount /mnt/loop
[root@balvan ~]# mount -o ro,loop,offset=7924088832 /run/media/rox/BAKPLUZ/LIBRARY/orcl/work/equipment/notebook/t490/m2_nvme_256gb.img /mnt/loop
[root@balvan ~]# ll /mnt/loop
total 449K
drwxrwxrwx 1 root root    0 Oct 22  2019 '$Recycle.Bin'/
-rwxrwxrwx 1 root root    1 Mar 19  2019  BOOTNXT*
drwxrwxrwx 1 root root 8.0K Oct 23  2019  Boot/
lrwxrwxrwx 2 root root   15 Oct 22  2019 'Documents and Settings' -> /mnt/loop/Users/
drwxrwxrwx 1 root root    0 Oct 22  2019  OBIins/
drwxrwxrwx 1 root root    0 Mar 19  2019  PerfLogs/
drwxrwxrwx 1 root root 4.0K Oct 22  2019 'Program Files'/
drwxrwxrwx 1 root root 4.0K Oct 22  2019 'Program Files (x86)'/
drwxrwxrwx 1 root root 8.0K Oct 22  2019  ProgramData/
drwxrwxrwx 1 root root    0 Oct 22  2019  Quarantine/
drwxrwxrwx 1 root root    0 Oct 22  2019  Recovery/
drwxrwxrwx 1 root root    0 Apr 28 03:37 'System Volume Information'/
drwxrwxrwx 1 root root 4.0K Oct 22  2019  Users/
drwxrwxrwx 1 root root  16K Oct 22  2019  Windows/
-rwxrwxrwx 1 root root 401K Apr  2  2019  bootmgr*
```
