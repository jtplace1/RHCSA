Configure local storage

# Configure local storage

 - 
- Create and remove physical volumes
- Assign physical volumes to volume groups
- Create and delete logical volumes
- Add new partitions and logical volumes, and swap to a system non-destructively



| **List, create, delete partitions on MBR and GPT disks**                        |                                                              |
| ---------------------------------- | ------------------------------------------------------------ |
| Df -h                              | Show info about the file system (total space and available space) |
| Df -hT                             | Show info about the file system (total space and available space) and the filesystem type |
| Du                                 | Showing disk usage by directory                              |
@@ -28,15 +27,13 @@ Configure local storage
| /etc/fstab                         | For automatic mounting drives when the system boots          |
| /etc/mtab                          | Showing all the current mounted volumes                      |
| **Mounting** |                                                              |
| ------------ | ------------------------------------------------------------ |
| Mount        | Show all the current mounts                                  |
| findmnt      | Show all the current mounts with its relations               |
| Df -Th       | Show all available disk space with the system mounts (including the filesystem) |
|              |                                                              |


|**Add new partitions and logical volumes, and swap to a system non-destructively** ||
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Swap**                                                     |                                                              |
| First create a LV disk that you want to enable for swap with Lvcreate ! |                                                              |
| Parted /dev/vg_disk/lv_disk2                                 |                                                              |
@@ -49,7 +46,6 @@ Configure local storage
| Ls -l /dev/mapper                                            | Dm-0 etc. should be the names corresponding to the output of swapon -s |

| **Volumes Show** |                       |
| ---------------- | --------------------- |
| Pvscan           | Scan physical volumes |
| Vgscan           | Scan volume groups    |
| Lvscan           | Scan ogical volumes   |
0 comments on commit 71ef59b 
