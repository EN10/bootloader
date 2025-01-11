# Simple Bootloader Project

This is a basic x86 bootloader project that demonstrates the fundamentals of OS development. The bootloader prints "Hello, boot world!" to the screen using BIOS interrupts.

## Project Structure

- `bootloader.asm` - The main bootloader source code written in x86 assembly
- `bootloader.bin` - The compiled binary bootloader image
- `bochs_config.bxrc` - Configuration file for the Bochs emulator

## Prerequisites

To build and run this project, you'll need:
- FASM (Flat Assembler) for compiling the assembly code
- Bochs x86 emulator for running the bootloader

## Building

To compile the bootloader, run:
```bash
fasm bootloader.asm bootloader.bin
```

## Running

To run the bootloader in Bochs:
```bash
bochs -f bochs_config.bxrc
```

## Technical Details

The bootloader:
- Is loaded by BIOS at memory address 0x7C00
- Runs in 16-bit real mode
- Uses BIOS interrupt 0x10 for video output
- Includes the standard boot signature (0x55, 0xAA)
- Fits within the required 512-byte size for boot sectors

## References

This project was inspired by:
- [Writing a Simple Operating System — from Scratch](https://www.youtube.com/watch?v=EzjnaMGxFko)

Technical references:
- [INT 10,E - Write Text in Teletype Mode](https://stanislavs.org/helppc/int_10-e.html) - Documentation for the BIOS interrupt used for text output

## License

This project is open source and available under the MIT License. 
