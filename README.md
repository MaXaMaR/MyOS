# MyOS (only description)

Характеристики операционной системы, которую я когда-то написал (до 2011).

Operating system:
Tools: NASM, MSVC
First-level loader: 2 sectors FAT12, FAT32 using BIOS interrupts, no BIOS later
Second-level loader: NASM bootstrapper to 32-bit protected mode & kernel & only needed drivers (storage drivers & file system drivers)
Kernel: x86 32-bit, multithreading, I/O ports, interrupts (PIC), virtual memory (paging), IPC, timers
IPC: spinlocks, mutexes, messages
Device drivers: ISA DMA, PS/2 Keyboard, Teletype, PIC, FDC, FDD, (S)ATA HD, ATAPI CD
File system drivers: FAT12, FAT16, FAT32, NTFS (open source reverse engineering docs), CDFS (ISO 9660) - read only
BIOS drivers: SMBIOS parser, PCIBIOS parser
Virtual drivers: CMOS parser, MBR partitions parser
Adds: CPUID parser
Libs: STL collections, Unicode support
Utils: heap management
Virtual testing environment: QEMU, Bochs, OpenBox, VmWare
Real testing: FAT12 1.4 Mb diskette, FAT32 ATA HD partition (+ booting from NTFS partition)
Binary files size: ~ 0.5 Mb
Used time: 2.5 years

Based on standards:
1. Information Technology - AT Attachment with Packet Interface - 7 - Volume 1 (Register Delivered Command Set, Logical Register Set (ATA/ATAPI-7 V1)), Volume 2 (Parallel Transport Protocols and Physical Interconnect (ATA/ATAPI-7 V2)), Volume 3 (Serial Transport Protocols and Physical Interconnect (ATA/ATAPI-7 V3)) - American National Standard of Accredited Standards Committee INCITS.
2. Intel® Processor Identification and the CPUID Instruction - Intel Corp.
3. Intel® 82077AA CHMOS SINGLE-CHIP FLOPPY DISK CONTROLLER - Intel Corp.
4. Intel® 82078 44 PIN CHMOS SINGLE-CHIP FLOPPY DISK CONTROLLER - Intel Corp.
5. Intel® 64 and IA-32 Architectures Software Developer’s Manual - Volume 1 (Basic Architecture), 2A (Instruction Set Reference, A-M), 2B (Instruction Set Reference, N-Z), 3A (System Programming Guide, Part 1), 3B (System Programming Guide, Part 2) - Intel Corp.
6. Information technology - SCSI Primary Commands - 3 (SPC-3) - T10, a Technical Committee of Accredited Standards Committee INCITS (InterNational Committee for Information Technology Standards)
7. Information technology -SCSI Architecture Model - 3 (SAM-3) - T10, a Technical Committee of Accredited Standards Committee INCITS (InterNational Committee for Information Technology Standards)
8. INFORMATION TECHNOLOGY - Multi-Media Commands - 6 (MMC-6) - InterNational Committee for Information Technology Standards (INCITS)
9. System Management BIOS (SMBIOS) Reference Specification - Version 2.6.1, Version 2.7.0 - Distributed Management Task Force, Inc. (DMTF)
10. Standard ECMA-119 2nd edition - Volume and File Structure of CDROM for Information Interchange (ISO 9660) - ECMA
11. Modern Operating Systems Third Edition - Andrew S. Tanenbaum

Comments:
All disk devices use DMA, other devices - interrupts management, no I/O polling
(S)ATA HD, ATAPI CD, SMBIOS, CPUID, FDC, FDD, ISO 9660, virtual memory (paging) - wrote fully based on official standards
(S)ATA HD, ATAPI CD, SMBIOS, CPUID - all functions are supported

Advantages:
OS fully consists of C++ objects.
Easy driver development with objected collections support, easy dynamic memory access at kernel level.
Microsoft Visual Studio environment, IntelliSense support, MSVC compiler, Intel ASM syntax.
