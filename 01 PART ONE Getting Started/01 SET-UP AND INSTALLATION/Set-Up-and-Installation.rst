.. _Set-Up-and-Installation:

===================
Set-Up and Installation
===================

.. _What's in the Box?

------------
What's in the Box?
------------

The KryoFlux setup consists of several pieces of hardware connected by cables (see figure 1). Because the KryoFlux board is so small and light, the setup can be a little precarious once connected. It also takes up more space than it does when boxed, so be sure that you have enough desk space to accommodate the various components. When moving hardware, handle it with caution, and have someone else help move the components as needed. As always when working with sensitive electronic components, take steps to protect against static electricity by using an anti-static mat or anti-static wristband; always place the KryoFlux board on a non-conductive surface while it is in use. 

///////////////////INSERT FIGURE 1 [ON P. 6] HERE /////////////////////////////////

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

///////////////////INSERT FIGURE 2 [ON P. 8] HERE /////////////////////////////////

*Figure 2: If using MacOSX, double-click KryoFlux.mpkg to install DTC.*

**NOTE:** You will need administrator rights to the computer to install the package.

**NOTE:** If you receive an unidentified developer warning (see figure 3) when trying to install the 
package, right click on the package and choose "Open" from the menu and then choose "Open" from the pop-up window.

///////////////////INSERT FIGURE 3 [ON P. 8] HERE /////////////////////////////////

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

See also the Troubleshooting section for more information related to this issue.

////////////////////////////LINK TO TROUBLESHOOTING SECTION//////////////////////////////////






