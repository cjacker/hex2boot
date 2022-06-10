# hex2boot - Hex to EFM8 Bootload Record conversion utility

EFM8 Factory Bootloader package [AN945SW](https://www.silabs.com/documents/public/example-code/AN945SW.zip) contains all EFM8 bootloader images with UART, USB or SMBus interface. And related utilities such as 'hex2boot' and 'efm8load'.

This repo contains the source code of `hex2boot.py` with a BSD license.

![screenshot-2022-06-10-09-13-34](https://user-images.githubusercontent.com/1625340/172972561-e8297914-93dd-41bd-aae5-aabbbb5756c7.png)


For more information about bootload record, please refer to:

- [AN945: EFM8 Factory Bootloader User's Guide](https://www.silabs.com/documents/public/application-notes/an945-efm8-factory-bootloader-user-guide.pdf)
- [The detailed structure of bootload record](https://siliconlabs.force.com/community/s/article/the-detailed-structure-of-bootload-record?language=en_US)

# Usage:
```
usage: hex2boot [-h] [-v] -o OUT [-b {0,1}] [-e {0,1,2}] [-i [ID [ID ...]]]
                   [-l LOCK] [-m {bb2,bb50,bb51,bb52,sb2,ub1}] [-s ADDR] [-t ADDR] [-w]
                   [hexfile]

Hex to Boot Record conversion utility.

positional arguments:
  hexfile               hex file to convert

optional arguments:
  -h, --help            show this help message and exit
  -v, --version         show program's version number and exit
  -o OUT, --out OUT     boot record output file (required)

conversion parameters:
  -b {0,1}, --bank {0,1}
                        flash bank (default=0)
  -e {0,1,2}, --erase {0,1,2}
                        0=none, 1=separate, (2=with data)
  -i [ID [ID ...]], --id [ID [ID ...]]
                        identity values (default=None)
  -l LOCK, --lock LOCK  lock value (default=None)
  -m {bb2,bb50,bb51,bb52,sb2,ub1}, --map {bb2,bb50,bb51,bb52,sb2,ub1}
                        special map type (default: None)
  -s ADDR, --start ADDR
                        start address (default=0)
  -t ADDR, --top ADDR   top address (default=65535)
  -w, --wait            remain in bootloader mode (default: False)

If hexfile is not provided, the utility will create records to erase the
specified address range.
```
