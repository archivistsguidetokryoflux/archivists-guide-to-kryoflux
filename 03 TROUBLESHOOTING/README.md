### Troubleshooting

## Why isn’t my computer finding the KryoFlux?

If your KryoFlux isn’t showing up as an unknown device or if your Windows instance
seems to have forgotten the drivers in between KryoFlux sessions, it may be that it’s being mistakenly recognized as Bossa Program Port. From the Device Manager window, search under Ports (COM & LPT). If you see Bossa Program Port listed, use the following steps to correct the problem (see also [Princeton's Tale of KryoFlux Woe](/02%20PART%20TWO%20In-Depth/Lessons-Learned.md) for an alternative solution, if this one fails):

**NOTE:** Administrative rights are required to add drivers to the computer. If you don’t have
admin access, contact your IT administrator for help.

1.  Right-click on *Bossa Program Port.*
2.  Select *Update driver software.*
3.  Select *Browse my computer for driver software.*
4.  Select *Let me pick from a list of device drivers on my computer.*

**NOTE:** If this is the first time you have done this, you may need to complete step
5. However, if you’ve done this once before, you may see the KryoFlux
Disk System listed and can simply select it and proceed to step 6.

5.  Browse to the KryoFlux drivers stored in the folder downloaded here.
6.  Hit *Next*. You should see the following confirmation message: *Windows has successfully updated your driver software*.
7.  Hit *Close*.

If you are still having trouble, try again from the beginning with the following steps:

The following instructions have been verified and written for Windows 10 Enterprise build 1703 x64. They are modified from those found on: https://forum.kryoflux.com/viewtopic.php?t=1038 

1.  Connect the KryoFlux board.Verify the *Bossa device* is under *Unspecified in the Control Panel\\All Control Panel Items\\Devices and Printers*
2.  Right click the Bossa device
3.  Click on *properties*
4.  Select the *hardware* tab
5.  Click on *properties* at the bottom of the *hardware* tab
6.  Click *change settings* at the bottom of the *General* tab
7.  Select the *Driver* tab in the new dialog window
8.  Click *Update Driver* in the Driver tab
9.  Click *Browse my computer* for driver software
10. Check the box *Include subfolders* and then click *Browse*
11. Click the folder where the extracted KryoFlux files are
12. Click *OK*
13. Click *Next*
14. Install the drivers
15. Reboot (may not be necessary)
16. Open *Control Panel\\All Control Panel Items\\Devices and Printers*
17. Verify the device in *Unspecified* is listed as *KryoFlux DiskSystem*

If the drivers do not load, or it says you already have the latest driver:

1.  Open *Control Panel\\All Control Panel Items\\Devices and Printers*
2.  Right click the Bossa device
3.  Click *Properties*
4.  Select the *Hardware* tab
5.  Click *Properties* at the bottom of the *Hardware* tab
6.  Click *Change Settings* at the bottom of the *General* tab
7.  Select the *Driver* tab in the new dialog window
8.  Click *Roll Back Driver*, and accept all prompts to roll back the driver
9.  Click *Update Driver* after the drivers have been rolled back and the *Roll Back Driver* option is not available
10. Check the box to *Always trust software*
11. Click *install* and close the dialog box
12. Verify the device in *Unspecified* has changed to *KryoFlux DiskSystem*

If the device reverts to *Bossa Program Port* after switching user accounts, even though it was not disconnected, follow these steps in **exactly the same order as they are listed**:

1.  Delete the device
2.  Unplug the power cord, unplug the usb cable
3.  Plug the usb cable in the computer, plug the power cord back in.

If this doesn’t work, it may be that your computer has stopped recognizing USB devices
Altogether. Other workarounds not listed here may be necessary.  See [Princeton's Tale of KryoFlux Woe](/02%20PART%20TWO%20In-Depth/Lessons-Learned.md) for one possible solution.


**Why am I getting bcadmin permission errors when trying to run the KryoFlux using Linux BitCurator?**

If this is your first time installing the KryoFlux, you will also need to create a udev rule.
The udev rule will prevent bcadmin permissions errors as well as erasing the need for the user to root. If this file is missing it is highly likely that the KryoFlux will not work properly.

If this is your first time installing the Kryoflux, you may need to also create a udev (Userspace Device) rule. This is often necessary to configure a Debian Linux (of which Ubuntu and BitCurator are flavors) environment, allowing access to the Kryoflux device for users in the *floppy* group. It is possible that BitCurator users will not need to to create a udev rule, as the default user (bcadmin) should already be part of the *floppy* group, however, some users report needing this udev rule on BitCurator systems as well as other Debian flavors of Linux.

See [here](/02%20PART%20One%20Getting-Started/01-SET-UP-AND-INSTALLATION/readme.md#udev-rule) for instructions to create a udev rule.

**Why won’t the drive calibrate when using the GUI?**

When using the GUI, the drive will not calibrate if you have selected the incorrect drive
(for example, drive 1 instead of drive 0). Select the other drive and retry. For more information, see [Understanding Drive 1/0](/02%20PART%20TWO%20In-Depth/Understanding-Drives-1-and-0.md) and [Princeton's Tale of KryoFlux Woe](/02%20PART%20TWO%20In-Depth/Lessons-Learned.md).

**Why is the Settings window blank when I use the KryoFlux GUI?**

At Princeton, even though Java was installed on the Ubuntu Linux workstation, archivists observed that the KryoFlux GUI did not call Java correctly when launching the GUI by clicking on “kryoflux-ui.jar.” The GUI would appear to open correctly, but important functionality would be missing (such as a completely blank Settings window). For more information on how to address this, see [Princeton's Tale of KryoFlux Woe](/02%20PART%20TWO%20In-Depth/Lessons-Learned.md).

**DTC is reporting that it successfully created a sector image. Why can’t I mount or export files from the image file?**

There is no single answer to this question, but here a few reasons why you might be unable to successfully mount or otherwise export logical files from a disk image.

* Many sectors were good or okay, but the sectors with important file system data were not due to bit rot and related media degradation.

* The file system is intact, but incompatible with the software you are to analyze the disk image. Since many forensic applications are designed to work with mainstream, contemporary systems, those that were obscure or mainstream but older often have compatibility issues.

* The disk image type selected was incorrect or some of the configuration options were incorrect. Certain disk image formats are similar enough to each other that selecting the wrong one will still result in a complete disk image. For example, a double-density 5.25” floppy when the options were configured for a single-density disk.
