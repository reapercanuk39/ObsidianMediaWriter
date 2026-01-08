# Obsidian Media Writer

Obsidian Media Writer is a tool that helps users put Obsidian OS images on their portable drives such as flash disks.

**This is a fork of [Fedora Media Writer](https://github.com/FedoraQt/MediaWriter) customized for Obsidian OS.**

It is able to automatically download the required Obsidian OS image and write it in a `dd`-like fashion, using either `dd` itself or some other way to access the drive directly.

This overwrites the drive's partition layout though so it also provides a way to restore a single-partition layout with a FAT32 partition.

## About Obsidian OS

Obsidian OS is a security-hardened Linux distribution based on Debian 12, designed for privacy-conscious users, security researchers, journalists, and activists.

For more information about Obsidian OS, visit the [Obsidian repository](https://github.com/reapercanuk39/Obsidian).

## Troubleshooting

If you experience any problem with the application, like crashes or errors when writing to your drives, please open an issue here on Github.

Please don't forget to attach the `ObsidianMediaWriter.log` file that will appear in your Documents folder (`$HOME/Documents` on Linux and Mac, `%USERPROFILE%\Documents` on Windows). It contains some non-sensitive information about your system and the log of all events happening during the runtime.

## Building

You can build Obsidian Media Writer using the default Qt `cmake` build system. The gist for all three platforms is written below.

### Linux

You should specify the target directory using the `-DCMAKE_INSTALL_PREFIX` `cmake` option. The default prefix path is `/usr/local`

It can be done like this:

`cmake [OPTIONS] .`

The main binary, `obsidian-media-writer`, will be written to `$PREFIX/bin` and the helper binary can be found on the path `$PREFIX/libexec/mediawriter/helper`.

#### Requirements

* `udisks2` or `storaged`
* `xz-libs`
* Qt 6.6.0+

### Windows

Building in Windows is just the matter of running `cmake` and `make` - as long as you have all dependencies in your include path.

To create a standalone package, use the `windeployqt` tool, included in your Qt installation.

#### Requirements

* `xz-libs`

### macOS

Again, you can just run `cmake` and `make`.

To release a standalone package, use `macdeployqt`, supplied with your Qt installation.

#### Requirements

* `xz-libs`

## Credits

This project is based on [Fedora Media Writer](https://github.com/FedoraQt/MediaWriter) by the Fedora Qt Team. Original work is licensed under GPL-2.0 and LGPL-2.0.

## Other information

For details about cryptography, see [CRYPTOGRAPHY.md](CRYPTOGRAPHY.md).

Some brief privacy information (regarding User-Agent strings) is in [PRIVACY.md](PRIVACY.md).
