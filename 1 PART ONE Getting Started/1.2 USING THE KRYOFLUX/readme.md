
# 1.2 Using the KryoFlux

* 1.2.1 [GUI vs. CLI](#121-gui-vs-cli)
	* [Ease of use for beginners](#ease-of-use-for-beginners)
	* [Efficiency and flexibility](#efficiency-and-flexibility)
	* [Reporting](#reporting)
* 1.2.2 [Using and interpreting the graphical user interface (GUI)](#122-using-and-interpreting-the-graphical-user-interface)
	* [Capturing disk images](#capturing-disk-images)
	* [Using deviceless mode](#using-deviceless-mode)
* 1.2.3	[Using and interpreting DTC via the CLI](#123-using-and-interpreting-dtc-via-the-cli)
	* [KryoFlux command line syntax](#kryoflux-command-line-syntax)
	* [Useful command line options](#useful-command-line-options)
	* [Command line examples](#command-line-examples)
	* [Adding DTC to your system variables](#adding-dtc-to-your-system-variables)

<a id="gui-vs.-cli"></a>
## 1.2.1 GUI vs. CLI:


The Kryoflux’s Disk Tool Console (DTC) is the command line application that sits 
underneath the Kryoflux’s graphical user interface (GUI). 

The KryoFlux provides two options for interacting with DTC:

1.	Use the graphical user interface (GUI)
2.	Run DTC using the command line interface (CLI)

Both provide similar functionality, and the writers of this guide do not endorse one 
approach over the other. Your decision as to which to use will likely depend in part 
on your own experience and personal preference. That said, the following summary 
provides an overview of some of the differences between the two.

### Ease of use for beginners

THE WINNER: The GUI
As might be expected, the GUI provides a more intuitive interface and a lower 
barrier of entry to use. Its color-coded interface provides immediate and 
easily-interpreted feedback, allowing users to quickly determine whether imaging is 
likely to have been successful. It might be an obvious choice for those who are 
unfamiliar with the command line. Documentation about the GUI is more widely 
available and more accessible than its CLI counterpart, which tends to assume some 
existing knowledge of the command line. 

### Efficiency and flexibility

**THE WINNER:** The CLI
In terms of efficiency and flexibility, the CLI may just pip the GUI to the 
post--especially if you are imaging a large number of disks. Whereas changing a 
setting using the GUI might involve several clicks, changing a setting using the CLI 
only requires typing the relevant option in the command. It’s a small difference, 
but may be enough to sway you towards the CLI if your aim is to get through as many 
disks as you can in the shortest possible time.

Similarly, use of the CLI also allows for the development of simple scripts that 
could run a series of commands with one keystroke--which you may or may not deem 
necessary, depending on your workflows. This does, of course, require some scripting 
expertise--but the opportunity to simplify imaging procedures may be motivation 
enough to start learning.

Finally, the number of options available using the CLI may provide more advanced 
users with added flexibility. The CLI, for example, allows greater control over what 
information is reported as part of the KryoFlux’s log files.

### Reporting

**THE WINNER:** The GUI
A particularly nice feature of the GUI are the visualizations that it provides as 
data is being imaged. Color-coded blocks provide immediate feedback on whether 
imaging has been successful. The use of red, orange, green, and grey blocks to 
represent bad, modified, good, and unrecognised data respectively is intuitive, and 
provides a quick and holistic overview for the user.

In the course of creating STREAM files, the GUI also provides visualizations of the 
flux data as a scatter plot graph and, if you’re the sort of person who knows how to 
interpret flux data as represented in a scatter plot graph, these can help diagnose 
media or hardware problems—or so I’ve been told. If you’re not the sort of person 
who knows how to interpret flux data as represented in a scatter plot graph, these 
can at least draw your attention to where problems might be lurking—even if you are 
not able to fully diagnose them (see Gough Lui’s [Project KryoFlux](http://goughlui.com/2013/04/21/project-kryoflux-part-3-recovery-in-practise/) series of Blog posts for more information).

Command line output provides similar levels of information, but its text-heavy 
delivery may not be quite as digestible as the GUI’s visualizations. That said, 
command-line options can be used to control the level of detail included in the 
DTC’s output, which may help users weed out information deemed overly technical and, 
ultimately, unnecessary (for an example of this, see [Working with 40-track floppy disks](/2%20PART%20TWO%20In-Depth/Working-With-40track-Floppy-Disks.md#25-working-with-40-track-floppy-disks)).

## 1.2.2 Using and interpreting the graphical user interface:

### CAPTURING DISK IMAGES

1.	Launch the KryoFlux graphical user interface, or GUI, either by clicking the desktop icon, or by opening the 
	DTC folder where the GUI installer was located and double-clicking on the file 
	called kryoflux-ui.jar.

**NOTE:** Java is required in order to launch the GUI. Instructions for installing 
Java and other dependencies can be found in the [Downloading the Software section](/1%20PART%20ONE%20Getting%20Started/1.1%20SET-UP%20AND%20INSTALLATION/README.md#112-downloading-the-software))

2.	At the beginning of each imaging session calibrate the floppy drive by selecting 
	the correct drive from the Drive menu then selecting Calibrate from the same 
	menu (see figure 9). You should only need to calibrate the drive once per 
	imaging session and any time you switch between 3.5-inch and 5.25-inch disk 	
	drives.
	
**NOTE:** See the [troubleshooting section](/3%20TROUBLESHOOTING/README.md) if you experience difficulties in calibrating your drive when using the GUI.

![Figure 9: Select the correct drive from the Drive menu, then select Calibrate.](figure9.png "Figure 9: Select the correct drive from the Drive menu, then select Calibrate.")

*Figure 9: Select the correct drive from the Drive menu, then select Calibrate.*

3.	Configure the KryoFlux GUI to select the output directory for your newly-created 
	disk images and log files. To do so, select *File → Settings* and click on the 
	*Output* tab. Browse to the appropriate path to storage. Ensure that the *Logs* 
	button is checked, and then click *OK* (see figure 10). 
	
![Figure 10: Enter the appropriate path to storage, check the Logs option and click 
OK.](figure10.png "Figure 10: Enter the appropriate path to storage, check the Logs option and click OK.")

*Figure 10: Enter the appropriate path to storage, check the Logs option and click 
OK.*

4.	For each disk, enter a unique identifier. Click on *Enter name…* and type in a 
	unique ID associated with the disk.  The text entered here will become the 
	filename for any disk images and log files created.  Do not include the 
	extension of the file name.
	
5.	Select the [image format(s)](/2%20PART%20TWO%20In-Depth/Disk-Image-Formats.md#22-disk-image-formats) for the disk image using the dropdown list 
	below the filename field (see figure 12). Use the table below (figure 11) to  
	select the necessary image formats. In order to choose multiple outputs, hold 
	down the *Control (Ctrl)* key while making your selections.  In most cases, 
	selecting an image format to obtain a sector image requires that you know 
	something about the media in hand.
	
**NOTE:** You may wish to capture [preservation stream files](/2%20PART%20TWO%20In-Depth/KryoFlux-Stream-Files.md#23-kryoflux-stream-files) (listed as 
*KryoFlux stream files, preservation*) in addition to a formatted disk image as part 
of your imaging workflow, since these stream files can be used later to create 
formatted disk images [using deviceless mode](#using-deviceless-mode).

|  **Physical Format** | **System Format** |     **KryoFlux Image Format**    |
|:--------------------:|:-----------------:|:--------------------------------:|
| 3.5" double density  | Macintosh         | Apple DOS 400K/800K sector image |
| 3.5" double density  | PC                | MFM sector image                 |
| 3.5" high density    | Any               | MFM sector image                 |
| 5.25" double density | Kaypro            | MFM sector image (40 track)      |
| 5.25" double density | PC                | MFM sector image (40 track)      |
| 5.25" high density   | PC                | MFM sector image                 |

*Figure 11: Some of the most commonly used disk encoding formats supported by the 
KryoFlux.  Details on how to handle 40 track images are covered in [part two.](/2%20PART%20TWO%20In-Depth/readme.md)*

![Figure 12: Select the image format(s) for the disk image using the dropdown list below the filename field.](figure12.png "Select the image format(s) for the disk image using the dropdown list below the filename field.")

*Figure 12: Select the [image format(s)](/2%20PART%20TWO%20In-Depth/Disk-Image-Formats.md#22-disk-image-formats) for the disk image using the dropdown list below the filename field.*

6.	After you have selected the appropriate image format, insert a disk and select 
	*Start*. You should see the green *Stream* indicator flash on and off, and see 
	the cells in the *Tracks* display on the left-hand side of the window fill with 
	different colors (see figure 13).
	
![Figure 13:  Once imaging has started, the green* Stream *indicator will flash on and off and the* Tracks *display on the left-hand side of the window will fill with 
blocks of color*.](figure13.png " Once imaging has started, the green* Stream *indicator will flash on and off and the* Tracks *display on the left-hand side of the window will fill with blocks of color*.")

*Figure 13: Once imaging has started, the green* Stream *indicator will flash on and 
off and the* Tracks *display on the left-hand side of the window will fill with 
blocks of color*.

**NOTE:** The colors of the track cells mean the following: 

| **Color of Track Cells** | **Meaning**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Green                    | *Good:* The track was imaged successfully.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Orange                   | *Good+Modified:* The track was imaged successfully, but has one or more sectors that were modified after formatting or mastering.  **NOTE:** The KryoFlux was designed to acquire unmodified copies of commercial software duplicated on commercial "mastering" machines. It is extremely likelythat you will encounter many "good/modified" tracks on media received from donors. While this is a measure of authenticity designed by the developers of the KryoFlux, it is largely inapplicable to archival collections that focus on receiving papers and records of private donors and organizations. |
| Red                      | *Bad:* The track was not imaged successfully.  **NOTE:** The KryoFlux can retry reads of a given track; this configuration option is available by selecting file → Settings and going to the *Advanced tab.                                                                                                                                                                                                                                                                                                                                                                                               |
| Grey                     | *Unknown:* the KryoFlux software could not determine the status of this track. This may or may not mean a successful read. It could indicate that thistrack was unformatted or that the wrong format was selected at step 5.If you are creating only preservation stream files, all sectors will be grey.                                                                                                                                                                                                                                                                                                 |


7.	Once the disk stops spinning and the green *Stream* indicator stops flashing, 
	the imaging process has completed. The disk image(s) and log file for the disk 
	you just imaged can be found in the directory you selected in step 3. 
	
8.	To image another disk, continue from step 4. If you switch drives (e.g. from 
	imaging 3.5” disks to 5.25” disks) and have not calibrated the other drive, 
	continue from step 3.
	
<a id="using-deviceless-mode"></a>
### USING DEVICELESS MODE

[Stream files](/2%20PART%20TWO%20In-Depth/KryoFlux-Stream-Files.md#23-kryoflux-stream-files) created in KryoFlux can be used to create [formatted images](/2%20PART%20TWO%20In-Depth/Disk-Image-Formats.md#22-disk-image-formats) with the KryoFlux software.  

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

The [Floppy Disk Format Identifier Tool](http://digitalcontinuity.org/post/144268258748/floppy-disk-format-identifer-tool), created by Euan Cochrane, allows the user to create multiple image types over a directory of stream files from multiple disks. See [Additional Tools and Resources](/5%20ADDITIONAL%20RESOURCES%20AND%20TOOLS/readme.md) for further information.

## 1.2.3 Using and interpreting DTC via the CLI:

### KRYOFLUX COMMAND LINE SYNTAX

If you look at the command line examples listed further down this document, you will notice that all KryoFlux commands begin with ``dtc``. This is because dtc is the name of the command that we execute whenever we run any task using the KryoFlux.

What comes after ``dtc`` depends on what task we want the KryoFlux to perform. KryoFlux’s Disk Tool Console (DTC) provides a number of options that we can use—sometimes on their own, but more often in combination with other options. These options allow us to set the parameters of the command (for example, the file names we want to use or the encoding format in which we want to create our disk image). As with other command line tools, you may want to add the folder containing dtc to your operating system environment variables. Doing so will allow calling the application from any directory without specifying the absolute path to dtc. Steps to add system variables vary from system to system. See [Adding DTC to your system variables](#adding-dtc-to-your-system-variables) for more information about how to add system variables.

Here's an example:

|        **Command**       |                                                               **Option**                                                               |                           **Parameter**                          |
|:------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------:|
|          ``dtc``         |                                                                 ``-f``                                                                 |                    ``kryofluxDiskImage_file``                    |
| Executes the DTC command | Serves as a flag to identify how the following parameter should be interpreted (in this case, it should be interpreted as a file name) | Provides our chosen file name (and, if necessary, its file path) |

### USEFUL COMMAND LINE OPTIONS	

**NOTE:** In the following table, the KryoFlux user should replace the angle brackets ( < > ) and any text stored inside the angle brackets with the required 
information.	

*For example*:	

``-f<name>`` might become ``-f filename.img``

``-i<type>`` might become ``-i0``

| Option        | Function                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``-f<name> `` | Used to set filename (and, if necessary, file path).                                                                                                                                                                                                                                                                                                                                                                           |
| ``-i<type> `` | Used to determine image type. This relates to how data has been encoded on the floppy disk, which may or may not be known in advance of imaging. When used in a command, option -i is paired with a number representing a certain encoding format, e.g., STREAM = 0, MFM = 4, Apple DOS 400k/800k = 9. (See the official KryoFlux manual (https://www.kryoflux.com/?page=download) for a full list of supported image types.)  |
|   ``-m<id>``  | Set device mode. This option is used to generate additional disk images using existing STREAM files, rather than the original floppy disk.                                                                                                                                                                                                                                                                                     |
|   ``-d<id>``  | Select drive, used if multiple drives are connected to KryoFlux (e.g., both a 3.5" and a 5.25" drive).                                                                                                                                                                                                                                                                                                                         |
|  ``-l<mask>`` | Used to select the level of output generated during imaging. Using -l8 will restrict output to formatting information only, which can be used to verify data against a specified image type.                                                                                                                                                                                                                                   |
|  ``-t<try>``  | Used to specify the number of retries per track in the event that the KryoFlux encounters errors. The default number of retries is 5; increasing this number might help recover data from worn disks.                                                                                                                                                                                                                          |
|     ``-p``    | Used to force creation of directories listed in file path.                                                                                                                                                                                                                                                                                                                                                                     |
|  ``-dd<val>`` | Used to set drive density line (i.e., high density (HD) or double density ( DD)). This is particularly useful when working with 5.25-inch drives. The disk may appear unformatted if the wrong density is used. This flag is less useful for 3.5-inch drives, which typically include a sensor to automatically detect the correct density.                                                                                    |

### COMMAND LINE EXAMPLES

**Create stream files only:**

	dtc -fpath/to/new/streamFile -i0
	
**Simultaneously create stream files plus formatted image files:**

	dtc –fpath/to/new/streamFile -i0 –fpath/to/new/formattedFile -i4
	
**Create stream files and, in the process, validate against selected image types in 
order to determine disk formatting:**

This command is helpful if you are not sure of the floppy disk’s encoding format. 
Using option –i with the parameter 0 (``-i0``), creates stream files from your floppy 
disk. When we use option –i again, this time with parameters 4 (MFM) and 9 (Apple DOS 
400k/800k) for example, the KryoFlux will validate the data on the disk against those 
encoding formats in order to determine which one (if either) is correct.

	dtc –fpath/to/new/streamFile -i0 -i4 –i9

**Limit output to formatting information only:**

By default, output generated by the KryoFlux during imaging will include detailed 
technical information, not all of which will necessarily be relevant to you. This 
option, used with parameter 8 (``-l8``), can be added to the end of any command to 
limit output generated by the KryoFlux to encoding format information.
							  
For example, the output generated by this command would only report whether the 
encoding format for data on the disk is MFM or Apple DOS 400k/800k:

	dtc –fpath/to/new/streamFile -i0 -i4 –i9 –l8
	
**Create formatted image files in deviceless mode (i.e., using stream files):**

If you have already created stream files and now wish to create a disk image using 
one of KryoFlux’s supported encoding formats (e.g., MFM), use the –m option to 
generate the new image file from data stored in the stream files, rather than on the 
original floppy disk. This is especially helpful if you don’t initially know the 
floppy disk’s encoding format—you can validate and reimage using the stream files, 
rather than repeatedly running commands on a disk that is aging and potentially 
fragile.

	dtc –fpath/to/existing/streamFile -i0 –fpath/to/new/formattedFile -i4 –m1
	
**NOTE:** For people who are less familiar with the command line, here is an example 
of how the above command would look in practice, and a breakdown of its component 
parts - also see how quotes are used for paths which contain spaces:

	dtc -f"c:\Users\username\Desktop\Stream Files\Track00.0.raw" -i0
	-fc:\Users\username\Desktop\Disk_1.img -i4 -m1
	
| Command component                                          | Function                                                                                                                                                                                                   |
|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``dtc``                                                    | Command required to call Disk Tool Console, the KryoFlux software.                                                                                                                                         |
| ``-fc:\Users\username\Desktop\Stream_Files\Track00.0.raw`` | File path (indicated by -f) to the first track in a folder of STREAM files (*Track00.0.raw*)                                                                                                               |
| ``-i0``                                                    | The 0 in ``-i0`` indicates that you are working from STREAM files.                                                                                                                                         |
| ``-fc:\Users\username\Desktop\Disk_1.img``                 | File path to the new image file. This command creates a new disk image, so you must specify its name and location here. Once you run the command, the KryoFlux software will create the file *Disk_1.img*. |
| ``-i4``                                                    | Indicates the encoding format for the new disk image. The 4 in ``-i4`` indicates that you are creating an MFM-encoded disk image.                                                                          |
| ``-m1``                                                    | Denotes that you are using [deviceless mode](#using-deviceless-mode).                                                                                                                            

**Force creation of directories in file path:**

Use the ``–p`` option if some of the directories in your file path don’t yet exist. 
This prevents you from having to manually create directories prior to running the 
command.

For example, the following command would create the directories named *UnitedStates* 
and *Georgia* in the process of generating the stream file named Atlanta:

	dtc –p –fUnitedStates\Georgia\Atlanta -i0
	
**Sending DTC output to log file:**

If you want to keep a copy of output generated during imaging for your records, this 
command will create a log file. However, note that this command sends output to the 
log file *instead* of the terminal window.

	dtc –fpath\to\streamFile -i0 –fpath\to\formattedFile -i4 > path\to\output.log
	
**Using tee or Wintee to send DTC output to both DTC terminal and log file:**

If you want to send output to both the terminal window *and* a log file, you will 
need to run an additional command alongside dtc.

On a Mac or Linux machine, use the command tee (tee is a native utility and does not 
need to be installed):

	dtc –fpath\to\streamFile -i0 –fpath\to\formattedFile -i4 2>&1 | tee 
	path\to\output.log
	
Windows has no native utility for this purpose, but Wintee is a free utility that can 
be used for this purpose. Download Wintee prior to running this command:

	dtc –fpath\to\streamFile -i0 –fpath\to\formattedFile -i4 2>&1 | wtee 
	path\to\output.log
	
### Adding DTC to your System Variables:

**Windows:**

1.	Launch Control Panel --> System and Security --> System.
2.	Select *Advance system settings* on the left-hand panel.
3.	In the System Properties dialog, select *Environment Variables…*
4.	In the Environment Variables dialog, select the Path line in the System Variables 
	list and select *Edit…*
5.	In the *Edit* environment variable dialog, select *New* and type the path to your 
	DTC folder.
	
**Mac:**

**NOTE:** The method for setting these variables changes dramatically from OS version 
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

**NOTE:** Depending on your version of Linux, you might need to replace .bash_profile 
with .profile or .bashrc.

1.	Launch terminal and ensure your working directory is your home directory.
2.	Type ``nano .bash_profile`` to create (or edit an existing) .bash_profile file.
3.	Add a line to the .bash_profile file that reads ``export 
	PATH=$PATH:/path/to/dtc-dir``
4.	Save and close the .bash_profile file.
5.	Type ``source ~/.bash_profile``
