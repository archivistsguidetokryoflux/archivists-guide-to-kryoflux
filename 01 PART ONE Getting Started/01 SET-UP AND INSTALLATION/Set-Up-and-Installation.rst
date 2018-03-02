.. _Set-Up-and-Installation:

===================
Set-Up and Installation
===================

.. _What's in the Box?:

------------
What's in the Box?:
------------

The KryoFlux setup consists of several pieces of hardware connected by cables (see figure 1). Because the KryoFlux board is so small and light, the setup can be a little precarious once connected. It also takes up more space than it does when boxed, so be sure that you have enough desk space to accommodate the various components. When moving hardware, handle it with caution, and have someone else help move the components as needed. As always when working with sensitive electronic components, take steps to protect against static electricity by using an anti-static mat or anti-static wristband; always place the KryoFlux board on a non-conductive surface while it is in use. 

///////////////////INSERT FIGURE 1 [ON P. 6] HERE /////////////////////////////////

*Figure 1: The various components included in the KryoFlux package. Depending on the package purchased by your institution, your box may also include a second backup KryoFlux board or a 5.25” floppy disk drive.*


.. _Downloading the Software:

------------
Downloading the Software:
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













^^^^^^^^^^^^^^^^^^^^^^
CAPTURING DISK IMAGES
^^^^^^^^^^^^^^^^^^^^^^

1.	Launch the KryoFlux GUI, either by clicking the desktop icon, or by opening the 
	DTC folder where the GUI installer was located and double-clicking on the file 
	called kryoflux-ui.jar.

**NOTE:** Java is required in order to launch the GUI. Instructions for installing 
Java and other dependencies can be found in the :ref:`Downloading the Software section<>`.

2.	At the beginning of each imaging session calibrate the floppy drive by selecting 
	the correct drive from the Drive menu then selecting Calibrate from the same 
	menu (see figure 9). You should only need to calibrate the drive once per 
	imaging session and any time you switch between 3.5-inch and 5.25-inch disk 	
	drives.
	
**NOTE:** See the :ref:`troubleshooting section<>` if you experience difficulties in 
calibrating your drive when using the GUI.

.. image:: figure9.png

*Figure 9: Select the correct drive from the Drive menu, then select Calibrate.*

3.	Configure the KryoFlux GUI to select the output directory for your newly-created 
	disk images and log files. To do so, select *File → Settings* and click on the 
	*Output* tab. Browse to the appropriate path to storage. Ensure that the *Logs* 
	button is checked, and then click *OK* (see figure 10). 
	
.. image:: figure10.png

*Figure 10: Enter the appropriate path to storage, check the Logs option and click 
OK.*

4.	For each disk, enter a unique identifier. Click on *Enter name…* and type in a 
	unique ID associated with the disk.  The text entered here will become the 
	filename for any disk images and log files created.  Do not include the 
	extension of the file name.
	
5.	Select the :ref:`image format(s)<>` for the disk image using the dropdown list 
	below the filename field (see figure 12). Use the table below (figure 11) to  
	select the necessary image formats. In order to choose multiple outputs, hold 
	down the *Control (Ctrl)* key while making your selections.  In most cases, 
	selecting an image format to obtain a sector image requires that you know 
	something about the media in hand.
	
**NOTE:** You may wish to capture :ref:`preservation stream files<>` (listed as 
*KryoFlux stream files, preservation*) in addition to a formatted disk image as part 
of your imaging workflow, since these stream files can be used later to create 
<<<<<<< Local Changes
formatted disk images `using deviceless mode`_.

+----------------------+-------------------+-----------------------------------+
| **Physical Format**  | **System Format** | **KryoFlux Image Format**         |
+======================+===================+===================================+
| 3.5” double density  | Macintosh         | Apple DOS 400K/800K sector image  |
+----------------------+-------------------+-----------------------------------+
| 3.5” double density  | PC                | MFM sector image                  |
+----------------------+-------------------+-----------------------------------+
| 3.5” high density    | Any               | MFM sector image                  |
+----------------------+-------------------+-----------------------------------+
| 5.25” double density | Kaypro            | MFM sector image (40 track)_      |
+----------------------+-------------------+-----------------------------------+
| 5.25” double density | PC                | MFM sector image (40 track)       |
+----------------------+-------------------+-----------------------------------+
| 5.25” high density   | PC                | MFM sector image                  |
+----------------------+-------------------+-----------------------------------+

*Figure 11: Some of the most commonly used disk encoding formats supported by the 
KryoFlux.  Details on how to handle 40 track images are covered in :ref:`PART 
TWO<>`.*

.. image:: figure11.png

*Figure 12: Select the :ref:`image format(s)<>` for the disk image using the dropdown list below the filename field.*

6.	After you have selected the appropriate image format, insert a disk and select 
	*Start*. You should see the green *Stream* indicator flash on and off, and see 
	the cells in the *Tracks* display on the left-hand side of the window fill with 
	different colors (see figure 13).
	
.. image:: figure13.png

*Figure 13: Once imaging has started, the green* Stream *indicator will flash on and 
off and the* Tracks *display on the left-hand side of the window will fill with 
blocks of color*.

**NOTE:** The colors of the track cells mean the following: 

+-------------------------+---------------------------------------------------------+
| **Color of Track Cell** | **Meaning**                                             |
+=========================+=========================================================+
| Green                   | *Good:* The track was imaged successfully.              |
+-------------------------+---------------------------------------------------------+
| Orange                  | *Good+Modified:* The track was imaged successfully,     |
|                         | but has one or more sectors that were modified after    |
|                         | formatting or mastering.                                |
|                         | ****NOTE:**** The KryoFlux was designed to acquire          |
|                         | unmodified copies of commercial software duplicated on  |
|                         | commercial “mastering” machines. It is extremely likely |
|                         | that you will encounter many “good/modified” tracks on  |
|                         | media received from donors. While this is a measure of  |
|                         | authenticity designed by the developers of the          |
|                         | KryoFlux, it is largely inapplicable to archival        |
|                         | collections that focus on receiving papers and          |
|                         | records of private donors or organizations.             |
+-------------------------+---------------------------------------------------------+
| Red                     | *Bad:* the track was not imaged successfully.           |
|                         | ****NOTE:**** The KryoFlux can retry reads of a given       |
|                         | track; this configuration option is available           |
|                         | by selecting File → Settings and going to the Advanced  |
|                         | tab.                                                    |
+-------------------------+---------------------------------------------------------+
| Grey                    | *Unknown:* the KryoFlux software could not determine    |
|                         | the status of this track. This may or may not mean a    |
|                         | successful read. It could indicate that this track was  |
|                         | unformatted or that the wrong format was selected at    |
|                         | step 5.  If you are creating only preservation stream   |
|                         | files, all sectors will be grey.                        |
+-------------------------+---------------------------------------------------------+

7.	Once the disk stops spinning and the green *Stream* indicator stops flashing, 
	the imaging process has completed. The disk image(s) and log file for the disk 
	you just imaged can be found in the directory you selected in step 3. 
	
8.	To image another disk, continue from step 4. If you switch drives (e.g. from 
	imaging 3.5” disks to 5.25” disks) and have not calibrated the other drive, 
	continue from step 3.

^^^^^^^^^^^^^^^^^^^^^^
USING DEVICELESS MODE
^^^^^^^^^^^^^^^^^^^^^^

:ref:`Stream files <>` created in KryoFlux can be used to create :ref:`formatted 
images <>` with the KryoFlux software.  

If you have previously created stream files you can use this workflow to create 
images using the KryoFlux software without needing the hardware or disk itself.

1.	At the beginning of each imaging session calibrate the drive by selecting 
	*Stream* Files from the *Drive* menu. Unlike working with a physical drive, the 
	stream file option does not require calibration.
	
2.	Configure the KryoFlux GUI to select the output directory for your newly-created 
	disk images and log files. To do so, select *File → Settings* and click on the 
	*Output* tab. Browse to the appropriate path to the *Staging storage*. Ensure 
	that the *Logs* button is checked, and then click *OK*. 
	
3.	For each disk, enter a unique identifier by clicking on *Enter name…* Type in the 
	unique ID number.  Do not include the extension of the file name.
	
4.	Select the image format(s) for the disk image using the dropdown list below the 
	filename field, select the necessary image formats from the table below. In order 
	to choose multiple outputs, hold down the *Control (Ctrl)* key while making your 
	selections. 
	
5.	Click *Start* and browse to the folder containing stream files.

The `Floppy Disk Format Identifier Tool <http://digitalcontinuity.org/post/144268258748/floppy-disk-format-identifer-tool>`_, created by Euan Cochrane, allows the user to create multiple image types over a directory of stream files from multiple disks. See :ref:`Additional Tools and Resources <>` for further information.

.. _Using-and-interpreting-DTC-via-the-CLI:

---------------------------------------
Using and interpreting DTC via the CLI:
---------------------------------------

.. _KryoFlux-Command-Line-Syntax:

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
KRYOFLUX COMMAND LINE SYNTAX
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you look at the command line examples listed further down this document, you will notice that all KryoFlux commands begin with ``dtc``. This is because dtc is the name of the command that we execute whenever we run any task using the KryoFlux.

What comes after ``dtc`` depends on what task we want the KryoFlux to perform. KryoFlux’s Disk Tool Console (DTC) provides a number of options that we can use—sometimes on their own, but more often in combination with other options. These options allow us to set the parameters of the command (for example, the file names we want to use or the encoding format in which we want to create our disk image). As with other command line tools, you may want to add the folder containing dtc to your operating system environment variables. Doing so will allow calling the application from any directory without specifying the absolute path to dtc. Steps to add system variables vary from system to system. See `Adding-DTC-to-your-system-variables`_ for more information about how to add system variables.

Here's an example:

+-------------+-------------------------------+--------------------------------------+
| **Command** | **Option**                    | **Parameter**                        |
+=============+===============================+======================================+
| ``dtc``     | ``-f``                        | ``kryofluxDiskImage_file``           |
+-------------+-------------------------------+--------------------------------------+
| Executes the| Serves as a flag to identify  | Provides our chosen filename (and    |
| DTC command | how the following parameter   | if necessary, its file path)         |
|             | should be interpreted (in     |                                      |
|             | this case, it should be       |                                      |
|             | interpreted as a filename)    |                                      |
+-------------+-------------------------------+--------------------------------------+		  
.. _Useful-command-line-options:

^^^^^^^^^^^^^^^^^^^^^^^^^^^^
USEFUL COMMAND LINE OPTIONS	
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

****NOTE:**** In the following table, the KryoFlux user should replace the angle brackets 
( < > ) and any text stored inside the angle brackets with the required 
information.	

*For example*:	

``-f<name>`` might become ``-f filename.img``

``-i<type>`` might become ``-i0``
				
+--------------+---------------------------------------------------------------------+
| ``-f <name>``| Used to set filename (and, if necessary, file path).                |
+--------------+---------------------------------------------------------------------+
| ``-i <type>``| Used to determine image type. This relates to how data has been     |
|              | encoded on the floppy disk—which may or may not be known in         |
|              | advance of imaging. When used in a command, option –i is paired     |
|              | with a number representing a certain encoding format, e.g.,         |
|              | STREAM = 0, MFM = 4, Apple DOS 400k/800k = 9. (See the              |
|              | `KryoFlux manual <https://www.kryoflux.com/?page=download>`_        |
|              | for a full list of supported image types).                          |
+--------------+---------------------------------------------------------------------+
| ``-m<id>``   | Set device mode. This option is used to generate additional disk    |
|              | images using existing STREAM files, rather than the original floppy |
|              | disk.                                                               |
+--------------+---------------------------------------------------------------------+
| ``-d<id>``   | Select drive, used if multiple drives are connected to KryoFlux     |
|              | (e.g., both a 3.5” and a 5.25” drive).                              |
+--------------+---------------------------------------------------------------------+
|``l<mask>``   | Used to select the level of output generated during imaging. Using  |
|              | –l8 will restrict output to formatting information only, which can  |
|              | be used to verify data against a specified image type.              |
+--------------+---------------------------------------------------------------------+
| ``-t<try>``  | Used to specify the number of retries per track in the event that   |
|              | the KryoFlux encounters errors. The default number of retries is    |
|              | 5; increasing this number can sometimes help recover data from      |
|              | worn disks.                                                         |
+--------------+---------------------------------------------------------------------+
| ``-p``       | Used to force creation of directories listed in file path.          |
+--------------+---------------------------------------------------------------------+
| ``-dd <val>``| Used to set drive density line (i.e., high density (HD) or double   |
|              | density ( DD)). This is particularly useful when working with       |
|              | 5.25-inch drives. The disk may appear unformatted if the wrong      |
|              | density is used. This flag is less useful for 3.5-inch drives, which|
|              | typically include a sensor to automatically detect the correct      |
|              | density.                                                            |
+--------------+---------------------------------------------------------------------+
				              
.. _Command-line-examples:

^^^^^^^^^^^^^^^^^^^^^^
COMMAND LINE EXAMPLES
^^^^^^^^^^^^^^^^^^^^^^

**Create stream files only:**

::

	dtc -fpath/to/new/streamFile -i0
	
**Simultaneously create stream files plus formatted image files:**

::

	dtc –fpath/to/new/streamFile -i0 –fpath/to/new/formattedFile -i4
	
**Create stream files and, in the process, validate against selected image types in 
order to determine disk formatting:**

This command is helpful if you are not sure of the floppy disk’s encoding format. 
Using option –i with the parameter 0 (``-i0``), creates stream files from your floppy 
disk. When we use option –i again, this time with parameters 4 (MFM) and 9 (Apple DOS 
400k/800k) for example, the KryoFlux will validate the data on the disk against those 
encoding formats in order to determine which one (if either) is correct.

::

	dtc –fpath/to/new/streamFile -i0 -i4 –i9

**Limit output to formatting information only:**

By default, output generated by the KryoFlux during imaging will include detailed 
technical information, not all of which will necessarily be relevant to you. This 
option, used with parameter 8 (``-l8``), can be added to the end of any command to 
limit output generated by the KryoFlux to encoding format information.
							  
For example, the output generated by this command would only report whether the 
encoding format for data on the disk is MFM or Apple DOS 400k/800k:

::

	dtc –fpath/to/new/streamFile -i0 -i4 –i9 –l8
	
**Create formatted image files in deviceless mode (i.e., using stream files):**

If you have already created stream files and now wish to create a disk image using 
one of KryoFlux’s supported encoding formats (e.g., MFM), use the –m option to 
generate the new image file from data stored in the stream files, rather than on the 
original floppy disk. This is especially helpful if you don’t initially know the 
floppy disk’s encoding format—you can validate and reimage using the stream files, 
rather than repeatedly running commands on a disk that is aging and potentially 
fragile.

::

	dtc –fpath/to/existing/streamFile -i0 –fpath/to/new/formattedFile -i4 –m1
	
****NOTE:**** For people who are less familiar with the command line, here is an example 
of how the above command would look in practice, and a breakdown of its component 
parts:

::

	dtc -fc:\Users\username\Desktop\Stream_Files\Track00.0.raw 
	-fc:\Users\username\Desktop\Disk_1.img -i4 -m1
	
+-----------------------------------------------------------+-----------------------+
| ``dtc``                                                   | Command required to   | 
|                                                           | call Disk Tool        |
|                                                           | the KryoFlux software |
+-----------------------------------------------------------+-----------------------+
| ``-fc:\Users\username\Desktop\Stream_Files\Track00.0.raw``| File path (indicated  |
|                                                           | by -f) to the first   | 
|                                                           | track in a folder of  | 
|                                                           | stream files          | 
|                                                           | (“Track00.0.raw”)     |
+-----------------------------------------------------------+-----------------------+
| ``-i0``                                                   | The 0 in ``-i0``      | 
|                                                           | indicates that you are| 
|                                                           | working with stream   |
|                                                           | files                 |
+-----------------------------------------------------------+-----------------------+
| ``-fc:\Users\username\Desktop\Disk_1.img``                | File path to the new  | 
|                                                           | image file. You are   | 
|                                                           | creating a new disk   | 
|                                                           | image, so you must    | 
|                                                           | specify its name and  | 
|                                                           | location in the       |
|                                                           | command line. Once you| 
|                                                           | run the command, the  | 
|                                                           | KryoFlux software will| 
|                                                           | create the file       | 
|                                                           | *Disk_1.img*. Be sure | 
|                                                           | to include the        | 
|                                                           | extension .img or .E01|
+-----------------------------------------------------------+-----------------------+
| ``-i4``                                                   | Indicates the encoding| 
|                                                           | format for the new    | 
|                                                           | disk image            |
+-----------------------------------------------------------+-----------------------+
| ``-m1``                                                   | Denotes that you are  | 
|                                                           | `using deviceless     | 
|                                                           | mode`_.               |
+-----------------------------------------------------------+-----------------------+

**Force creation of directories in file path:**

Use the ``–p`` option if some of the directories in your file path don’t yet exist. 
This prevents you from having to manually create directories prior to running the 
command.

For example, the following command would create the directories named *UnitedStates* 
and *Georgia* in the process of generating the stream file named Atlanta:

::

	dtc –p –fUnitedStates\Georgia\Atlanta -i0
	
**Sending DTC output to log file:**

If you want to keep a copy of output generated during imaging for your records, this 
command will create a log file. However, note that this command sends output to the 
log file *instead* of the terminal window.

::

	dtc –fpath\to\streamFile -i0 –fpath\to\formattedFile -i4 > path\to\output.log
	
**Using tee or Wintee to send DTC output to both DTC terminal and log file:**

If you want to send output to both the terminal window *and* a log file, you will 
need to run an additional command alongside dtc.

On a Mac or Linux machine, use the command tee (tee is a native utility and does not 
need to be installed):

::

	dtc –fpath\to\streamFile -i0 –fpath\to\formattedFile -i4 2>&1 | tee 
	path\to\output.log
	
Windows has no native utility for this purpose, but Wintee is a free utility that can 
be used for this purpose. Download Wintee prior to running this command:

::

	dtc –fpath\to\streamFile -i0 –fpath\to\formattedFile -i4 2>&1 | wtee 
	path\to\output.log
	
.. _Adding-DTC-to-your-System-Variables:

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Adding DTC to your System Variables:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Windows:**

1.	Launch Control Panel --> System and Security --> System.
2.	Select *Advance system settings* on the left-hand panel.
3.	In the System Properties dialog, select *Environment Variables…*
4.	In the Environment Variables dialog, select the Path line in the System Variables 
	list and select *Edit…*
5.	In the *Edit* environment variable dialog, select *New* and type the path to your 
	DTC folder.
	
**Mac:**

****NOTE:**** The method for setting these variables changes dramatically from OS version 
to OS version. The following instructions should work in MacOS 10.13, but be aware 
that your mileage may vary:

1.	Launch terminal and ensure that your working directory is your home 
	directory.
2.	Type ``nano .bash_profile`` to create (or edit an existing) .bash_profile file.
3.	Add a line to the .bash_profile file that reads ``export PATH=”/path/to/ 
	DTC:$PATH”``
4.	Save and close the .bash_profile file.
5.	Quit and relaunch Terminal.
6.	Type ``echo $PATH`` to confirm that DTC has been added as a variable.

**Ubuntu Linux:**

****NOTE:**** Depending on your version of Linux, you might need to replace .bash_profile 
with .profile or .bashrc.

1.	Launch terminal and ensure your working directory is your home directory.
2.	Type ``nano .bash_profile`` to create (or edit an existing) .bash_profile file.
3.	Add a line to the .bash_profile file that reads ``export 
	PATH=$PATH:/path/to/dtc-dir``
4.	Save and close the .bash_profile file.
5.	Type ``source ~/.bash_profile``
 	




	






