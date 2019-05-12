We are currently working on a feature for Signet HC to support what we are calling “one time use” volumes. One time use volumes are used for transferring files from one computer to another. After being successfully used to transfer files the volume is automatically reset by the firmware to its initial empty state. At this time the device also begins fully erasing the old file data while allowing the newly reset volume to be immediately used.

We think this feature is important because many people use USB flash drives to transfer files from one computer to another. Without regular scrubbing this leads to accumulating a lot of unneeded files which creates a privacy hazard when you want to share files with another person. It is possible to clear the device manually after each use but it’s easy to forget, and sifting through accrued data to determine what is safe to delete becomes a tedious and sometimes difficult task. Worse, still, is the risk posed to your privacy and data when an ordinary flash drive is lost or stolen: not only are all the regular files accessible, any number of previously deleted files can extracted from unallocated sectors of the drive using low cost and free tools accessible to even inexperienced data thieves.

We have had a general idea of how we would implement this feature for awhile but have decided to take the time to flush out the design more now that we have a stable hardware platform to implement it on. It has turned out to be somewhat more complex problem than we first thought.

### High-level design

A one-time-use volume goes through a cycle of states: Empty, Modified, and Reading. The Empty empty is when the volume has been recently created and contains no files. The Modified state is when files have been added but the volume but it has not been ejected yet. The reading state is set when the volume has been ejected after being modified and being read by another computer. The flow chart below shows how the device changes between the states. To ensure correct operation a distinction is made between the state the device will enter on the next remount and the state the device is currently in:

{one-time-use-volumes-high-level-flow-chart}


### Secure erasure

When the device transitions from the “Reading” state to the “Empty” state the device will erase all of the sectors used by the last transfer so that the data is destroyed and not simply hidden. This presents two problems. If the device does not keep track of which sectors need to be erased then the automatic erasures could both be very time consuming and end up aging the flash memory more than necessary.  If the device delayed the automatic reformatting until all sectors were erased then it could be minutes before you could use the volume again. 

To limit the amount of data that needs to be erased between uses the firmware will keep track of which regions have been written to since transitioning to the “Empty” state. The firmware will keep track of writes with 1MB granularity. This large granularity will limit the size of the map data structure needed to record which regions have been written to. 

Erasure of data from a previous use will occur at the same time the newly formatted volume is available for use. The firmware will be able to accomplish this thought use of a separate map that will track “dirty” regions which still need to be erased.  Before the volume is reformatted the map of modified regions from the last use is copied to the dirty regions map and then erasure can begin. If the filesystem requests to read or write a sector marked for erasure then that request is delayed until the region is completely erased. This process is detailed in the flowchart below.


{one-time-use-volumes-secure-erase-flow-chart}
