AFU (AMI Firmware Update) is a package of utilities used 
to update the system BIOS under various operating systems.  

Note: AFU only works for APTIO with SMI FLASH support.
      Compatible with Aptio 5.

The package includes:

- AFULNX_64 5.16.02.0111
- AFU User Guide

To run, extract all of the files from the folder with the name corresponding to the desired operating system.


Usage (applies to AFUWIN, AFUEFI and AFUEFI64...
       for usage of AFULNX see help files provided in their folders):
------------------------------------------------------------------
AFUEFI <BIOS ROM File Name> [Option 1] [Option 2]
Or
AFUEFI <Input or Output File Name> <Command>
Or
AFUEFI <Command>

BIOS ROM File Name
The mandatory field is used to specify path/filename of the BIOS ROM file with extension.

Commands
The mandatory field is used to select an operation mode.
- /FV             Copy Secure FV to EFI. (*2)
- /O              Save current ROM image to file.
- /U              Display ROM File's ROMID.
- /S              Refer to Options: /S
- /D              Verification test of given ROM File without flashing BIOS.
- /A:             Refer to Options: /A:
- /OAD            Refer to Options: /OAD
- /CLNEVNLOG      Clear Event Log.
Options
The optional field used to supply more information for flashing BIOS ROM. Following lists the supported optional parameters and format:
- /SSB:           Send String  to BIOS. For example, /SSB:{xxx}.(*3)
- /CMD:           Send special command to BIOS. /CMD:{xxx, xxx, xxx}.
- /OEMCMD:        Send special value to BIOS. /OEMCMD:xxx.
- /DPC            Don't Check Aptio 4 and Aptio 5 platform.
- /PW:            Input password for file.
- /MEUL:          Program ME Entire Firmware Block, which supports.
                  Production.BIN and PreProduction.BIN files.
- /Q              Silent execution.
- /X              Don't Check ROM ID.
- /ATR:           Select AMI Twins ROM to flash. For example, /ATR:D or ATR:U.(*3)
- /ATR            Select Another Tank ROM to flash.(*3)
- /S              Display current system's ROMID.
- /JBC            Don't Check AC adapter and battery.
- /CLRCFG         Program without preserving setup configuration.
- /BCPALL         Save all question values before flash.
- /HOLEOUT:       Save specific ROM Hole according to RomHole GUID.
                  NewRomHole1.BIN /HOLEOUT:GUID
- /SP             Preserve Setup setting.
- /Rn             Preserve SMBIOS type N during programming.(n=0-255)
- /R              Preserve ALL SMBIOS structure during programming.
- /B              Program Boot Block.
- /P              Program Main BIOS.
- /K              Program all non-critical blocks.
- /N              Program NVRAM.(*4)
- /Kn             Program n'th non-critical block.(n=0-15)
- /K:<GUID>       Program non-critical block by GUID.
- /RLC:           To set default option for Rom layout change.(E:Entire BIOS
                  region, A:Abort, F:Force, M:Mix Non-BIOS region command.)
- /HOLE:          Update specific ROM Hole according to RomHole GUID.
                  NewRomHole1.BIN /HOLE:GUID
- /L              Program all ROM Holes.
- /Ln             Program n'th ROM Hole only.(n=0-15)
- /ECUF           Update EC BIOS when newer version is detected.
- /E              Program Embedded Controller Block.
- /ME             Program ME Entire Firmware Block.
- /MEUF           Program ME Ignition Firmware Block.
- /A:             Oem Activation file.
- /OAD            Delete Oem Activation key.
- /CLNEVNLOG      Clear Event Log.
- /CAPSULE        Override Secure Flash policy to Capsule.
- /RECOVERY       Override Secure Flash policy to Recovery.
- /EC             Program Embedded Controller Block. (Flash Type)
- /REBOOT         Reboot after programming.
- /SHUTDOWN       Shutdown after programming.
- /FDR            Flash Flash-Descriptor Region.(*1)
- /GBER           Flash GBE Region.(*1)
- /MER            Flash Entire ME Region.(*1)
- /OPR            Flash Operation Region of SPS.(*1)
- /PDR            Flash PDR Region.(*1)
- /PFRU           Updates platform firmware.(*3)
- /PFRU:CPLD      Updates platform firmware.(*3)
- /PFRA           Signal active image update intent.(*3)
- /PFRD           Signal dynamic region update of active image.(*3)
- /PFRR           Signal recovery image update intent.(*3)
- /PFRC           Signal CPLD update intent.(*3)
- /PFRW           Wait until reset to update.(*3)

(*1)If BIOS ME Module reports these commands, AFU will show this command.
(*2)If AFU is running on Linux OS and Windows OS, AFU will show this command.
(*3)If BIOS Module support, AFU will show this command.
(*4)If BIOS project has NVRAM preservation mechanism, AFU /N command cannot fully clear NVRAM data region.
To use a command of generic AFU on the Specific platform, please refer to the help menu (/?) in generic AFU.

Rules
- Any parameter encolsed by < > is a mandatory field.
- Any parameter enclosed by [ ] is an optional field.
- <Commands> cannot co-exist with any [Options].
- Main BIOS image is default flashing area if no any option present.
- [/REBOOT], [/X], and [/S] will enable [/P] function automatically.
- If [/B] present alone, there is only the Boot Block area to be updated.
- If [/N] present alone, there is only the NVRAM area to be updated.
- If [/E] present alone, there is only the Embedded Controller block to be updated.
- All options are case-insensitive and have no order.
