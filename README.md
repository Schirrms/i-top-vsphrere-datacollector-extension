# itop-vsphere-datacollector-extension
Some extensions I made in the VSphere Data Collector

I did some extensions to the VShere Data Collector for iTop.

While some of them are very specific to our environment, I put the whole here, it can be useful for other.

# Installation

As I edit directly the main branch files, you really need to use the files for the same version as your datacollector. The changes I made are all in the 'collector' sub directory of the datacollector module so you have to replace some or all of the files in this directory.

As of today, you'll find here or in the .zip file a subdirectory named collectors-1.0.11. This is the complete set of the file for this version. don't try it on other versions (well, not to much changes upstream between 1.0.10 and 1.0.11, but the 1.0.9 was completely different)

But just copying my files over the original may works ...or not. It's quite possible that I reference Custom destination fields in iTop that you may or may not have.

This is more to use as a source of inspiration :)

# Changes from upstream

(This list is probably not complete)

## Hypervisor Server

Collect the Serial Number, the UUID (in a non standard field named S_UUID) and the IP management address

## Virtual Machine

Collect for each VM the space usage on each Datastore (but this works because of other tasks I have collecting on my disk Array datastore informations)...

A picture better than a long text :

![](D:\git\itop-vsphere-datacollector-extension\images\VM-Datastore-Usage.png)

Collect the custom attributes, but most of them are for custom fields in iTop..

Collect the UUID (also for a custom field S_UUID)

For the OS : instead of using the VMware value 'OS from configuration field' I use (i available) the VMware value 'OS according to VMware tools' that I find more accurate.

I position the VM on the correct location (also a custom extension, and these tests are totally specific!). This is to know in wich Datacenter the VM is.

I position the 'move2production' date from one of our Custom attributes (again very specific).

Collect the VCenter, as an URL so I can jump from iTop to the good VCenter (useless if you have only one !)

Collect the PowerStatus of the VM : in some extractions, I only count 'poweredOn' VM

Many attributes are now updatables.

