# Binwalk

Binwalk is a binary file analysis tool that allows you to identify, extract and analyze firmware, system images and other complex binaries. It is widely used in cybersecurity, reverse engineering and IoT device analysis.

## How Binwalk Works

Binwalk scans binary files for:
- **Magic bytes** (signatures) that identify embedded file types
- **Data entropy** to find compressed or encrypted sections
- **Filesystems** such as JFFS2, SquashFS, YAFFS2
- **Bootloaders** and embedded Linux kernels
- **Compressed archives** (ZIP, GZIP, LZMA, etc.)

## Basic Usage

```bash
binwalk firmware.bin        # Simple scan
binwalk -e firmware.bin     # Automatic extraction
binwalk -Me firmware.bin    # Recursive scan + extraction
```

## Essential Parameters

| Parameter | Description |
|-----------|-------------|
| `-B` | Scan only main signatures |
| `-E` | Show entropy of data (useful for finding encrypted sections) |
| `-H` | Output in hexadecimal format |
| `-A` | Scan for opcodes and code |
| `-g <pattern>` | Search for specific patterns in the file |
| `-e` | Automatically extract found files |
| `-M` | Recursive scan over extracted files |
| `-C <dir>` | Specify output directory |
| `-Z` | Compress extracted files |
| `-t <types>` | Include only specific types (eg: `-t filesystem`) |
| `-x <types>` | Exclude specific types (eg: `-x jpeg,png`) |
| `-y <types>` | Show only specific types |
| `-v` | Verbose output (more details) |
| `-q` | Silent output |
| `-f <file>` | Save results to file |
| `--log=<file>` | Verbose log file |

```