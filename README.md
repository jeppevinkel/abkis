# abkis
Arch BTRFS KDE Install Script


## Prerequisites
- A root, efi, and swap partition
- Efi on FAT32
- Root on BTRFS

## Instructions

## Prepare the system

1. Create the needed partitions  
   Using `cfdisk` create the following partitions:
   - `EFI System` partition (1 GiB or larger recommended)
      - Don't make this if reusing an existing EFI partition
   - `Linux swap` partition (4 GiB or larger recommended)
   - `Linux filesystem` partition (all the space you want for your root system)
2. Format the partitions  
   For the `<device name>`, see the values in `cfdisk`. For the `device lavel` come up with a simple name to remember the purpose of the partition
   - For the `EFI System` partition, run: (only if you created a new partition, DO NOT DO THIS IF USING AN EXISTING)  
     `mkfs.fat -F 32 /dev/<device name>`
   - For the `Linux swap` partition, run:  
     `mkswap /dev/<device name>`
   - For the `Linux filesystem` partition, run:  
     `mkfs.btrfs -L <device label> /dev/<device name>`

## Run the install

- `curl -L https://jeppevinkel.github.io/abkis | bash`
Simply follow the on-screen instructions until it's complete.
- `reboot`
