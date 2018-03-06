.. _Set-Up-and-Installation:

===================
Set-Up and Installation
===================

.. _What's in the Box?

------------
What's in the Box?
------------

The KryoFlux setup consists of several pieces of hardware connected by cables (see figure 1). Because the KryoFlux board is so small and light, the setup can be a little precarious once connected. It also takes up more space than it does when boxed, so be sure that you have enough desk space to accommodate the various components. When moving hardware, handle it with caution, and have someone else help move the components as needed. As always when working with sensitive electronic components, take steps to protect against static electricity by using an anti-static mat or anti-static wristband; always place the KryoFlux board on a non-conductive surface while it is in use. 

.. image:: figure1.png

*Figure 1: The various components included in the KryoFlux package. Depending on the package purchased by your institution, your box may also include a second backup KryoFlux board or a 5.25” floppy disk drive.*


.. _Downloading the Software:

------------
Downloading the Software
------------

^^^^^^^^^^^^^^^^^^^^^^
USING WINDOWS...
^^^^^^^^^^^^^^^^^^^^^^
1.	Download the directory containing KryoFlux driver and DTC files from the KryoFlux website: http://kryoflux.com/?page=download.

2.	Save the directory to your chosen location. Make a note of this location. For example: C:\Users\Public\Desktop\kryoflux_2.51_windows


^^^^^^^^^^^^^^^^^^^^^^
USING MAC...
^^^^^^^^^^^^^^^^^^^^^^

1. Download the JDK Java Runtime Platform files from the Oracle website: http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html.

2. Run the JDK dmg file (it will have a name similar to this: jdk-8ku121-macosx-x64.dmg).

3. Download the KryoFlux software from the KryoFlux website: http://kryoflux.com/?page=download.

4. Save the downloaded KryoFlux file to your chosen location. Make a note of this location (MacOSX will place the download in the following path by default, ~/Downloads/kryoflux_2.62_macosx).

5. Unzip the downloaded file and navigate to the dtc folder.

6. Install DTC 

- Double-click KryoFlux.mpkg (see figure 2);
- Follow prompts to install the software.

.. image:: figure2.png

*Figure 2: If using MacOSX, double-click KryoFlux.mpkg to install DTC.*

**NOTE:** You will need administrator rights to the computer to install the package.

**NOTE:** If you receive an unidentified developer warning (see figure 3) when trying to install the 
package, right click on the package and choose "Open" from the menu and then choose "Open" from the pop-up window.

.. image:: figure3.png

*Figure 3: The unidentified developer MacOSX warning.*


^^^^^^^^^^^^^^^^^^^^^^
USING LINUX...
^^^^^^^^^^^^^^^^^^^^^^

1. Download the Linux .tar file containing KryoFlux driver and DTC files from the KryoFlux website: http://kryoflux.com/?page=download

2. Save the .tar file and then use Archive Manager to extract the directory to your chosen location. Make a note of this location (for example, ~/Downloads/kryoflux_2.6_linux).

3. Launch a terminal window.

4. In the terminal window, type the following three commands (each followed by the Enter key) to install libusb and the JDK Java Runtime Platform:

	``sudo apt-get install libusb-1.0-0-dev``

	``sudo apt-get install libusb-dev``

	``sudo apt-get install openjdk-7-jre``

If they are already installed, the system will tell you that your version is up to date.

""""""""""""""""""""""""""
**USING LINUX: PREREQUISITES AND DEPENDENCIES**
""""""""""""""""""""""""""
*UDEV RULE*
If this is your first time installing the KryoFlux software, you will also need to create a udev rule. The udev rule will prevent permissions errors as well as erasing the need for the user to root. (If this file is missing it is highly likely that the KryoFlux will not work properly.)

* To create this rule, navigate to the following directory: **/etc/udev/rules.d**
* While still in the above directory, create a file with the following title (use nano or a similar text editor): **80-kryoflux.rules**
* Type the following text into the file: **ACTION=="add", SUBSYSTEM=="usb", ATTR{idVendor}=="03eb", ATTR{idProduct}=="6124", GROUP="floppy", MODE="0660"**

*JAVA DEPENDENCY*
The KryoFlux software relies on Java to launch the GUI. In some cases, even though Java was installed on the Ubuntu Linux workstation, archivists observed that the KryoFlux GUI did not call Java correctly when launching the GUI by clicking on “kryoflux-ui.jar.” As a workaround, archivists at Princeton have developed a short `bash script <https://github.com/kellybolding/scripts/blob/master/run-kryoflux-gui.sh>`_that invokes Java each time they launch the GUI. This script lives on the workstation’s desktop and users click on it in order to start up the GUI in place of a desktop icon.

See also the :ref:`troubleshooting section<>` section for more information related to this issue.


------------
Setting Up the KryoFlux
------------
While it does not require an especially high level of technical skill, setting up the KryoFlux does demand some careful attention to detail.  

	- **Make sure to read this entire section before attempting to connect and power your board!**

	- **The floppy drive is an unstable source of power that can permanently damage the board, so it is imperative to follow the correct order when connecting/disconnecting KryoFlux.**

	- **If you suspect that you have a malfunctioning board or have damaged a board in the process of installing, and you have a backup board, do not use the backup board until you have successfully troubleshooted the original board. If you do not know why the original board is not working, you may inadvertently replicate the problem if you connect a backup board.**

1. Always place the KryoFlux board on a non-conductive surface while it is in use. You may choose to use an anti-static mat or wristband, but typically this won’t be necessary and there’s debate about whether or not these types of anti-static devices will be helpful in a scenario like this one. NOTE: do not place the board on top of the anti-static bag in which the KryoFlux is shipped. The anti-static bags are conductive, and although the resistance is fairly high, it might cause data errors nonetheless.

2. Make sure the floppy disk drive is placed so that the spinning mechanism on its bottom side is not obstructed (i.e. on a raised surface that doesn’t cover the bottom of the drive, such as bridging the drive across the space between two DVD cases).

3. Enable write-blocking functionality by removing the jumper for the write gate (see figure 4).

4. Connect the drive to the board via the data cable. Ensure that the data cable’s first pin (the colored band) is oriented correctly. For more information about this, please see the :ref:`Understanding Drive 1/0<>` section.

	* For 3.5” drives, pin 1 must face left when the front of the drive is facing away from you. For some drives, this means that pin 1 will fact the outside of the drive when plugged in correctly, but this is not always the case. The rule of facing the drive away from you before plugging it in, and making sure that pin 1 faces left, should still be applicable to all 3.5” drives.  

	* For 5.25” drives, the same rule should apply. When the drive is facing away from you the first pin should be on the left.

	* On the KryoFlux side, the cable’s first pin should be on the right if viewing the board with the cable connector closest to you (as in figure 5).	
	
.. image:: figure4.png

*Figure 4: Enable writeblocking functionality by removing the jumper for the write gate. This photograph shows the write gate once the jumper has been removed and writeblocking functionality enabled.*	

**NOTE:** If you are not familiar with the connectors on the data cable, the smaller ones connect to the board and to 3.5” drives, while the larger ones with gold lining connect to 5.25” drives.

5. Connect the KryoFlux board to the computer using the USB cable (see figure 5).
	
.. image:: figure5.png

*Figure 5: Once the drive is connected to the KryoFlux board via the data cable, connect the board to the computer using the USB cable.*	
**NOTE:** If using Windows, proceed to step 6. If using Mac or Linux, skip step 6 and proceed directly to step 7.

6. WINDOWS USERS ONLY

**FIRST TIME WINDOWS USERS** (If using the KryoFlux on a Windows machine for the first time, you will need to complete the *Install the KryoFlux Drivers* instructions below. If, however, drivers are already installed, skip to *Launch the Command Prompt* step below):

* Install the KryoFlux drivers:

	* Launch the *Start* menu; 

	* Right-click on *Computer*;

	* Click *Properties*; 

	* Click *Device Manager*; 

	* Right-click on *Unknown Device* in the Device Manager menu (see figure 6). 

	* Select *Browse my computer for driver software*. Depending on your institution’s policies, you may need admin credentials starting with this step.

	* Click *Browse* and navigate to the folder where the KryoFlux directory was saved in step 2. 

	* Select the KryoFlux directory and click *Next*. 

	* Click *OK* on all of the prompts to install the drivers.

.. image:: figure6.png

*Figure 6: Device Manager. One of the devices in this menu will be labeled “Unknown Device.” This is the KryoFlux. During installation, you may have to search through this list to find the “Unknown Device.” Once the KryoFlux has been recognized, however, it should be listed under Universal Serial Bus controllers. The steps are largely the same in Windows 10, although the presentation is slightly different.* 

**NOTE:** See the :ref:`troubleshooting section<>` if you have trouble with this step, or if your Windows 
instance seems to have forgotten the drivers in between KryoFlux sessions.

* Launch the command prompt:

	* Go to the *Start* menu and type ``command prompt`` command prompt or ``cmd`` into the search box and hit *Enter*.
	* Using the command prompt, navigate to the dtc folder (located inside the KryoFlux directory downloaded at step 1) (see figure 7). 
	* Type  ``dtc -c2`` into the command prompt, and press *Enter*. If DTC gives an error message, this means it is working (it tried to install the driver, but the driver was already there, so DTC returned an error). 
	
**NOTE:** the above steps may require admin credentials depending on your institution’s setup.


