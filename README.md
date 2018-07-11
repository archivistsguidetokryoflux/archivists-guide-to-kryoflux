Introduction
=============

Contributors
------------

Jennifer Allen, Elvia Arroyo-Ramirez, Kelly Bolding, Faith Charlton, Patricia 
Ciccone, Yvonne Eadon, Matthew Farrell, Allison Hughes, Victoria Maches, Shira 
Peltzman, Alice Prael, Scott Reed, Dorothy Waugh.

About this Guide
----------------

For archivists working with aging floppy disks, the KryoFlux can be an incredibly 
powerful tool. It is not, however, an incredibly user-friendly one. Scant 
documentation and a somewhat advanced user forum have caused frustration for many 
archivists and, in some cases, hampered use. Having heard such complaints at 
conferences and meetings across the country, our group of digital archivists and 
graduate students from Duke, Emory, UCLA, the University of Texas, and Yale decided 
to develop this user guide, which has been written specifically with the needs of 
archivists in mind.

We’ve assumed that readers are already familiar with the principles underlying 
digital forensics and its application in an archival context, but do not assume 
readers to have any previous experience with the KryoFlux. A key feature of this 
guide is that we do not intend or expect that it be read in any particular order. 
Instead, we hope that users will move between sections as they are most relevant and 
useful.

The user guide is divided into two parts:

*	[Part One] [./01 PART ONE Getting Started/README.rst] provides step-by-step instructions designed to get you set up 
	and started. You may wish to start here if you already have a KryoFlux in hand 
	and are ready to jump in. We’ve included links to relevant sections in [part two] [./02 PART TWO In-Depth/README.rst] 
	so you can dip in and out as needed.
*	[Part Two] [./02 PART TWO In-Depth/README.rst] provides a more in-depth introduction to the KryoFlux and 
	floppy disks as a medium for data storage. You may wish to start here if you are 
	interested in learning more about the ins and outs of how the KryoFlux works 
	before diving in, or if you’re weighing the benefits of purchasing a KryoFlux 
	for your institution.
	
	
This is an unofficial guide and has not been written in affiliation with the 
Software Preservation Society (SPS). The official KryoFlux manual is available at 
http://www.kryoflux.com/download/kryoflux_manual.pdf. 

----------------------------
Introduction to the KryoFlux
----------------------------

The KryoFlux is a floppy disk controller card developed by the `Software 
Preservation Society <https://www.kryoflux.com/?page=links_sps>`_ that can read a 
wide variety of legacy floppy disks and create bit-for-bit disk images of their 
contents. Purchase of the KryoFlux hardware typically includes the controller board, 
a 3.5” floppy disk drive, the KryoFlux software, and any necessary cables, although 
the exact contents will vary depending on the package selected for purchase. The 
KryoFlux is available to buy at the `KryoFlux website 
<https://webstore.kryoflux.com/catalog/index.php>`_, where institutions may choose 
from a range of “pro” packages depending on their needs. An institutional license is 
required and is included with every order of a pro package hardware kit. This 
results in a cost that, while not huge, is also not insignificant. Because costs 
vary depending on institution size and may change over time, it is difficult to 
provide an estimated range here. However, institutions can `contact 
<https://www.kryoflux.com/?page=comp_contact>`_ the KryoFlux team for more 
information about pricing.

The KryoFlux has several features that differentiate it from an external USB floppy 
disk drive: 

*	**Supports a wide variety of encoding formats:** Data stored on a floppy disk is 
	encoded using one of a number of available formats. The KryoFlux supports a wide 
	variety of floppy disk encoding formats and can help users identify the correct 
	one. During disk imaging, the KryoFlux software reports the degree to which 
	image capture has been successful.
*	**Generates stream files where the encoding format is unknown or unsupported:**
	In cases when the encoding format is unknown or unsupported, the KryoFlux can 
	read the magnetic flux that represents data stored on a floppy disk and store it 
	as raw stream files. This can also be a useful feature if disks are 
	copy-protected. This allows users to capture an image of data stored on any 
	disk, regardless of format. That said, the KryoFlux’s stream file format is 
	proprietary and cannot be rendered. As such, it offers a temporary solution to 
	unknown or unsupported formats, but is not considered ideal for preservation 
	purposes.
*	**Creates disk images from stream files:** This process is called “deviceless 
	mode.” Deviceless mode allows for the creation of multiple images, without 
	having to physically image a disk again, by using stream files. This way, it is 
	possible to try multiple file systems out on the same set of stream files.
*	**Effectively handles degraded data:** There are several ways that floppy disks 
	can become difficult or impossible to read, all of which tend to occur within 
	10-20 years. Magnetic storage is vulnerable to wear, and the adhesive keeping 
	the magnetic coating in place can degrade, resulting in data loss. In addition, 
	contaminants can stick to the magnetic storage and damage it. Floppy disks can 
	also demagnetize over time due to changes in temperature or magnetic fields near 
	the disk. The KryoFlux has a better rate of success than external USB floppy 
	drives at imaging disks that have undergone this kind of damage.
*	**Includes built-in write-blocking functionality:** Users can enable a 
	write-blocker on the KryoFlux board to ensure a one-way information flow, 
	removing the need for extra write-blocking hardware.

**Example:**

Emory University’s Stuart A. Rose Manuscript, Archives, and Rare Book Library 
(formally, MARBL) experimented with a range of imaging methods, including the 
KryoFlux, in order to process thirty-seven 3.5” floppy disks included among the 
papers of writer and activist Alice Walker. The integrated setup of the KryoFlux 
allowed for an OS- and file system-agnostic approach that allowed for the 
identification and imaging of a wide variety of disks in various states of 
degradation. An article in the `June 2014 issue of Practical Technology for Archives 
<https://web.archive.org/web/20141016233702/http://practicaltechnologyforarchives.org
/issue2_waugh>`_ describes the project in greater detail.

