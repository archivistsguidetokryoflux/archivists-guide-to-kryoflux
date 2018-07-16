
# Disk Image Formats

There are over 20 distinct types of disk images available using the DTC application, and trying to visually parse the list either in the GUI or from the CLI reference list in the official KryoFlux manual is daunting. This section will briefly cover the two broad categories of disk image types and the full range of options available to the user, before providing a longer discussion of the two more common formats one will likely encounter including how to configure the CLI and GUI to create them. The section will close with a discussion of KryoFlux preservation stream files, specifically addressing the format’s positives and negatives.

## Frequency modulation and group code recording:

Floppy disks can be divided into two categories based on the scheme computer systems use to encode data on the magnetic surface. The two families are Modified Frequency Modulation (MFM) (based on its predecessor Frequency Modulation (FM)), and Group Code Recording (GCR). The general user of the KryoFlux board does not need to know a huge amount of information about either particular encoding method, but it is useful to keep in mind that MFM is a uniform method of encoding--meaning that MFM is generally better documented and closer to a standard--while GCR really refers to a number of related encoding methods primarily developed by Apple and Commodore Business Machines independently of one another. As implied by its name, MFM and FM encodes binary data through reversals in polarity and because of the translation from flux reversals and the data signified by those reversals, disks encoded using this method tend to be more uniform. GCR encoding methods rely on tables to translate flux reversals and those tables vary depending on the hardware, low-level driver software, and operating system.

As a rule of thumb, if you know what system a disk was used with and the approximate era, you can make an educated guess about whether it’s MFM or GCR encoded. It is important to note, however, that a user may have purchased a disk meant for another system and reformatted it for use in their own machine--so it is important not to assume that a manufacturer’s label claiming compatibility with one system means it is definitely formatted for use with that system.

## Most commonly encountered options:


### MFM/FM Generic Sector Images

Generic MFM and FM encoded floppy disks are perhaps most common, particularly with disks used in the 1990s.[1_] This is largely because IBM personal computers and IBM clones throughout the 1980s and 1990s encoded data using these methods, leading to wide use by users of MS-DOS and CP/M systems at work and in the home. Rising levels of interoperability between peripherals across these systems over time helped lead to increased market share.

If a set of disks was used with an MS-DOS machine from the mid-1980s through the early-2000s, it is almost certainly a MFM or FM-encoded disk. Disks using the generic FM and MFM profiles include single-sided/double-density floppies, double-sided/double-density floppies, and double-sided, high-density floppies in both 5.25” and 3.5” sizes. 

### Apple DOS 400K/800K Sector Images

Apple computers in the 1980s and early 1990s used variable speed floppy drives in order to increase the capacity over their PC counterparts. This allowed for disks to beat early PC disks in terms of raw storage, but made reading those disks on later Apple computers to be much more difficult. KryoFlux’s use of the phrase Apple DOS 400K/800K is a bit of a misnomer in that this type of sector image may include Apple computers not running Apple DOS[2_] (e.g., early Macintosh computers). As a general rule, 400K refers to single sided/single-density floppy disks. These disks were most commonly created on Apple computers running System 0.7-System 7.1. 800K refers to the double-sided or double-density floppy disks created by machines running System 7.5 and later.[3_] By the time Apple introduced the update to its HFS filesystem (HFS+), native support for the variable speed floppies had been deprecated. All of this is a long way of saying, if the user knows that a particular disk was written using an Apple computer made between 1985 and 1995 (generally), the image type to attempt would be the 400K/800K sector image.


## Other disk image types available:

### Disk Image Types Using MFM and FM Encoding

Additional disk image types available when using KryoFlux include the following:

* MFM/FM XFD - used for disks from the Atari 8-bit line of computers. The FM XFD is compatible with the earlier models from that line, while the MFM XFD is compatible with the later models.
* AmigaDOS sector image - used for disks from the Amiga family of personal computers. Interestingly, the floppy disk controller in Amiga machines was capable of reading and writing both MFM and GCR encoded floppies. Given that MFM encoding was handled by the Amiga’s CPU, it was even possible for users to implement custom encoding schemes.
* DEC RX01 and RX02 sector image - used for 8-inch disks specifically using the DEC-manufactured drives. While 8-inch drives made by other manufacturers were similar to later 3.5- and 5.25-inch successors, the DEC models worked specifically with PDP machines and were more idiosyncratic in nature.
* EMU sector image - used for disks that worked with the E-mu line of synthesizers. The synthesizers stored samples on floppy disks

### Disk Image Types Using GCR Encoding

Additional disk image types available when using KryoFlux include the following:

* Apple DOS 3.x sector image, DSK DOS 3.3 Interleave - used for 5.25” floppy disks written to by Apple II family of computers in the early 1980s.
* CBM sector image, various subtypes - used for floppy disks used by the Commodore Business Machines family of computers in the 1980s. As indicated by the KryoFlux user guide, there are a number of subtypes of CBM disk; it appears that different manufacturers created variations of the format.

.. [1] Pages 1-6 of this document have additional details on FM and MFM encoding. http://info-coach.fr/atari/hardware/_fd-hard/AN-505.pdf accessed 05/03/2017
.. [2] https://groups.google.com/forum/#!topic/vintage-macs/CbD58EqcnUM accessed 12/5/2016
.. [3] http://siber-sonic.com/mac/newmillfloppy.html accessed 12/5/2016
