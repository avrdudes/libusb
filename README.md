# libusb for Windows

This library is a fork of [libusb-win32](https://sourceforge.net/projects/libusb-win32/).

The design objective of this library is to provide a better
out-of-the-box experience for [AVRDUDE](https://github.com/avrdudes/avrdude) Windows users.

This library only supports a subset of the original implementation.
The intend is not to provide a general purpose implementation,
but to satisfy the usage scenarios of AVRDUDE.

This library supports only **Microsoft Visual C/C++**,
as used in the **msvc** job of the [AVRDUDE build action](https://github.com/avrdudes/avrdude/blob/main/.github/workflows/build.yml).

The latest version of **libusb for Windows** can be found here:\
<https://github.com/avrdudes/libusb>

The original README of libusb can be found here: [README](./README).

## Notable Changes

This library was completely rewritten to support the default Windows
**WinUSB** driver, as well as the legacy **libusb0.sys** driver,
while maintaining a libusb-0.1 compatible programming API.
