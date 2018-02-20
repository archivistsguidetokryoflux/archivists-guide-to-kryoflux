.. _Using-the-KryoFlux:

===================
Using the KryoFlux
===================

.. _GUI-vs-CLI:

------------
GUI vs. CLI:
------------

The Kryoflux’s Disk Tool Console (DTC) is the command line application that sits 
underneath the Kryoflux’s graphical user interface (GUI). 

The KryoFlux provides two options for interacting with DTC:

1.	Use the graphical user interface (GUI)
2.	Run DTC using the command line interface (CLI)

Both provide similar functionality, and the writers of this guide do not endorse one 
approach over the other. Your decision as to which to use will likely depend in part 
on your own experience and personal preference. That said, the following summary 
provides an overview of some of the differences between the two.

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
**Ease of use for beginners**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

THE WINNER: The GUI
As might be expected, the GUI provides a more intuitive interface and a lower 
barrier of entry to use. Its color-coded interface provides immediate and 
easily-interpreted feedback, allowing users to quickly determine whether imaging is 
likely to have been successful. It might be an obvious choice for those who are 
unfamiliar with the command line. Documentation about the GUI is more widely 
available and more accessible than its CLI counterpart, which tends to assume some 
existing knowledge of the command line. 

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
**Efficiency and flexibility**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

THE WINNER: The CLI
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

^^^^^^^^^^^^^^
**Reporting**
^^^^^^^^^^^^^^

THE WINNER: The GUI
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
not able to fully diagnose them (see Gough Lui’s `Project KryoFlux 
<http://goughlui.com/2013/04/21/project-kryoflux-part-3-recovery-in-practise/>`_ 
series of Blog posts for more information).

Command line output provides similar levels of information, but its text-heavy 
delivery may not be quite as digestible as the GUI’s visualizations. That said, 
command-line options can be used to control the level of detail included in the 
DTC’s output, which may help users weed out information deemed overly technical and, 
ultimately, unnecessary (for an example of this, see :ref:`Working with 40-track 
floppy disks)<>`.

.. _Using-and-interpreting-the-GUI:

----------------------------------------------------------
Using and interpreting the graphical user interface (GUI):
----------------------------------------------------------

.. _Capturing-disk-images:

^^^^^^^^^^^^^^^^^^^^^^
CAPTURING DISK IMAGES
^^^^^^^^^^^^^^^^^^^^^^

1.	Launch the KryoFlux GUI, either by clicking the desktop icon, or by opening the 
	DTC folder where the GUI installer was located and double-clicking on the file 
	called kryoflux-ui.jar.

NOTE: Java is required in order to launch the GUI. Instructions for installing Java 
and other dependencies can be found in the :ref:`Downloading the Software section<>`.

2.	At the beginning of each imaging session calibrate the floppy drive by selecting 
	the correct drive from the Drive menu then selecting Calibrate from the same 
	menu (see figure 9). You should only need to calibrate the drive once per 
	imaging session and any time you switch between 3.5-inch and 5.25-inch disk 	
	drives.
	
NOTE: See the :ref:`troubleshooting section<>` if you experience difficulties in 
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
	
NOTE: You may wish to capture :ref:`preservation stream files<>` (listed as 
*KryoFlux stream files, preservation*) in addition to a formatted disk image as part 
of your imaging workflow, since these stream files can be used later to create 
formatted disk images using :ref:`*Deviceless Mode*<>`.

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

NOTE: The colors of the track cells mean the following: 

+-------------------------+---------------------------------------------------------+
| **Color of Track Cell** | **Meaning**                                             |
+=========================+=========================================================+
| Green                   | *Good:* The track was imaged successfully.              |
+-------------------------+---------------------------------------------------------+
| Orange                  | *Good+Modified:* The track was imaged successfully,     |
|                         | but has one or more sectors that were modified after    |
|                         | formatting or mastering.                                |
|                         | **NOTE:** The KryoFlux was designed to acquire          |
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
|                         | **NOTE:** The KryoFlux can retry reads of a given       |
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



