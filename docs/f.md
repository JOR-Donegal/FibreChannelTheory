# NVMeOF

All the technology we have discussed so far is legacy. Fibre channel is 30 years old, and the disk technology has its origins a good 10 years before that. SAS and SATA controllers are a bottleneck, and this problem is common to the entire computer industry. The most advanced off-the-shelf interface technology which has emerged is NVMe and although there is some confusion on modern motherboards, SAS/SATA are not compatible with NVMe. This technology connects extremely fast flash-based storage directly with the PCI-e bus of the underlying computer hardware.

All the storage technologies we discussed so far in this course use the SCSI command language. NVMe has its own command language, the first real move from SCSI in my working lifetime.

NVMeOF is NVMe over Fabric, it allows NVMe commands to be communicated across the network, giving all the advantages of mature fibre channel standards, and the fastest available storage technology.

At time of writing this is leading-edge technology. Look at NetApps website and look for the information on their NVMe technology. 

