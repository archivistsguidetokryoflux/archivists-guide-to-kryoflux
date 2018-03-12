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

blah blah
