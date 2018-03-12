.. Working with 40-Track Floppy Disks:

==================================
Working with 40-Track Floppy Disks
==================================

------------------------
What are 40-track disks?
------------------------

The magnetic medium inside a blank floppy disk is coated with magnetic oxide, with particles in no magnetic order. Formatting the disk aligns these particles into a pattern of tracks, which are concentric rings divided into sectors that represent locations where data is stored, with empty space between the rings. This also represents the structure that the stored data follows. Until the mid-1980s, floppy disks typically had 40 tracks each. These tracks were widely-spaced enough that drives would not accidentally overwrite data or write data to the wrong track by mistake. After the mid-1980s, changes in technology halved the physical distance needed between tracks, so more tracks (and data) could fit onto a disk. Floppy disks usually had 80 tracks after this point. 

The KryoFlux’s software images 80-track disks by default, and will not automatically image 40-track disks correctly. If you have a 40-track disk, you’ll need to change the GUI’s settings or image the disk using the command line interface in order to image it correctly.

Reading a 40-track disk with an 80-track drive can be difficult, since 80-track drives were generally not designed for this, but there are workarounds once you know you have a 40-track disk. 

It can be difficult to identify a 40-track disk. One clue can be found by checking the disk’s label, since some 40-track disks are labeled “48 tpi,” or 48 tracks per inch. This refers to the density of the tracks on the floppy. If the label says “48 tpi,” you can confirm that it is a 40-track disk via the command line and/or the GUI (see next section).

---------------------------
How to tell if you have one
---------------------------

40-track disks can often be identified in the GUI by the distinctive sector pattern they exhibit during imaging, wherein every other track is bad or unintelligible, as shown below. **If you notice this pattern while imaging is underway, it’s important not to stop the process until it is finished, since stopping during imaging can damage the drive.**

.. image:: images/40-track-figure01.png
*Figure 1: DTC GUI. Note that every other track on side 0 is bad; this is a sign that the floppy disk is likely a 40-track disk.*

In the above image, the pattern occurs because the drive detects “crosstalk”, or magnetic noise between tracks. The drive expects to see a new track, but does not find one because the disk has 40 wider tracks instead of 80 narrower tracks. The drive/KryoFlux may try to read tracks that shouldn’t have readable data on a 40-track disk (the odd-numbered tracks), resulting in every other track appearing to be bad.

In order to confirm that this pattern indicates a 40-track disk, you will need to use the command line. 

In the command line, navigate to the folder containing the DTC executable file, and enter:
::
  dtc -m1 -fpath\to\STREAM\file/* -i -fpath\to\MFMimageFile/new_image_filename.img -i4 -l8

This will create an MFM image of the disk from stream files. (We chose to create an MFM image because we thought this was the most likely format for the disk we were imaging, and the output confirmed that we were right. If another format is more likely, the command you enter to image the disk will be slightly different. See Using and interpreting DTC via the CLI for more information.) 

Then look at the output:

.. image:: images/40-track-figure02.PNG
*Figure 1: STDOUT to console.*

After the first few lines, each line should look something like this:
::
  02.0      :  MFM OK*, trk: 002[001], sec: 9, *HT      +5

Here, *02.0* is the track number, and *MFM OK** means that the disk is MFM-formatted, so the MFM image will work. *Trk:  002* means that the software expects to find track 2, and [001] means that it found track 001 instead. 

The number after *trk:* and the number in the bracket will depend on the track. If there is a number in brackets, then the disk is a 40-track disk. This is because the brackets won’t appear if the track number matches the number after trk. If they do not match, then the track number the program found will be listed in the brackets, and you’ll know you have a 40-track disk.

In the output, *H* stands for header gap. If there’s a header gap, that means that the track has been modified (in other words, the user wrote something to it) so it has data that we want. *T* represents the track warning, which is when the track number the software finds doesn’t match the track number it should find. Each line of output also includes a number that represents the number of modified sectors on that track. In this case, there are 9 modified sectors.

An additional sign that you have a 40-track disk instead of an 80-track disk is that, after the first few tracks, every other track returns three lines: one that looks like the line shown above, but with MFM <error> instead of MFM OK*, one that says “Bad sector found,” and one that says “Read operation failed.” This is because there’s no track for the software to read.

The following breaks down the sample line of output described above, and explains what each part means:
 * **02.0  :**: Track number
 * **MFM**: Check for MFM Formatting
 * **OK***: Disk is MFM-formatted
 * **trk: 002**: Expecting to find track 2
 * **[001],**: Finds track 1 instead (difference signifies 40-track disk)
 * **sec: 9,**: 9 modified sectors
 * ***HT**: Header gap (track has been modified), Track warning
 * **+5**:
