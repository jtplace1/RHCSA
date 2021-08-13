Operate running systems

# Operate running systems

- Boot, reboot, and shut down a system normally
- Boot systems into different targets manually
-  Interrupt the boot process in order to gain access to a system
-  Identify CPU/memory intensive processes and kill processes
-  Adjust process scheduling
- Manage tuning profiles
- Locate and interpret system log files and journals
- Preserve system journals
- Start, stop, and check the status of network services
- Securely transfer files between systems

**Grub**

| **Grub**                               |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| Boot legacy                            | Location: /boot/grub/menu.lst                                |
| Grub2                                  | Location: /boot/grub2/grub.cfg (BIOS) Location: /boot/efi/EFI/distro-name/grub.cfg (UEFI) |
|                                        |                                                              |
| /etc/default/grub                      | Changing settings for grub                                   |
| Grub2-mkconfig -o /boot/grub2/grub.cfg | Making a config for grub2                                    |



**Booting**

Post -> Bootloader -> Kernel (in memory, mounts root partition and runs initialisation program) -> initialization process starts the necessary background programs required for the system to operate 

Bootloader is installed on the MBR (Master boot record) 

Install GRUB on MBR:

- grub-install 

Show kernel ring buffer content:

\- dmesg 



Memory:

Show active partition where the swapfile is stored:

- Swapon -s

Get information about the usage of virtual memory:

\- vmstat

Root 

Grant user as sudo user -> visudo 

]


| **Root password reset:**                                     |                                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Press “e” on boot menu                                       |                                                              |
| Add rd.break to the linux line   <br />![image-20210123121910707](images/RHCSA8_notes/image-20210123121910707.png) | The rd.break parameter interrupts the boot process before the control is passed over to the kernel. |
| Cntrl x<br />![image-20210123122022764](images/RHCSA8_notes/image-20210123122022764.png) |                                                              |
|                                                              |                                                              |
|                                                              |                                                              |
| **Grub Changing default target**                             |                                                              |
| Press “e” on boot menu                                       |                                                              |
| ![image-20210123122051387](images/RHCSA8_notes/image-20210123122051387.png) <br />To <br />![image-20210123122129423](images/RHCSA8_notes/image-20210123122129423.png) |                                                              |
| Cntrl x                                                      |                                                              |
|                                                              |                                                              |
|                                                              |                                                              |

| **Grub changing config**                                     |                                                  |
| ------------------------------------------------------------ | ------------------------------------------------ |
| Vi /etc/default/grub                                         | Changing some settings within the grub config    |
| grub2-mkconfig -o /boot/grub2/grub.cfg                       | Writing the config file to the boot config file. |
| ![image-20210123122234185](images/RHCSA8_notes/image-20210123122234185.png) |                                                  |
|                                                              |                                                  |


|                      |                                                              |
| -------------------- | ------------------------------------------------------------ |
| **UEFI**             |                                                              |
| Efi System Partition | Partition where UEFI stores the boot loader                  |
| /boot/efi            |                                                              |
| bcfg                 | Interactive shell within UEFI for changing the boot configuration |


