## What is Nanvix Playground

This project, named Nanvix Playground, is a fork of the original **[Nanvix](https://github.com/nanvix/nanvix)**, a simple operating system written for educational purposes.

The idea is to be able to use this repository as a playground, being free to break anything while learning a bit more about operating systems' architecture.

The reason this repository is not forked using GitHub's fork feature is because it creates a strong dependency. Pull Requests, for example, always focus on the forked repository rather than the fork itself. Opening Pull Requests on the original project that are not intended to me berged, by accident, would be annoying for the maintainers.

A huge "thank you" to [Pedro H. Penna](https://github.com/ppenna) and all the other contributors! This project is awesome, and it is really helpful for those interested on learning how operating systems work.

---

## Building

### Linux-like systems
In order to build Nanvix, you will need a Linux like programming
environment, the x86 GCC compiler and the x86 GNU binutils.

If you are running a Debian-based Linux distribution, like Ubuntu,
you can simply run the following commands at the root directory:

```sh
sudo apt-get install make
sudo bash tools/dev/setup-toolchain.sh
sudo bash tools/dev/setup-bochs.sh
sudo reboot now
```

When done, you can build Nanvix by typing, at the root directory:

```sh
make nanvix
```

Or you can build a Live System's Image by typing, at the same directory:

```sh
make image
```

### macOS

The support of Nanvix on macOS is still experimental.
It relies on the Homebrew package manager (https://brew.sh), to get
the necessary UNIX-like packages to build Nanvix.

The general flow for building Nanvix on macOS from the root directory
is as follows:

```sh
bash tools/dev/setup-toolchain.sh
make TARGET=i386-elf nanvix
make image
```

Unlike the Linux-like systems procedure, this flow does not build
bochs from source. Instead, it installs the bochs package using brew.
As this package does not come with gdb-stubs support, you cannot run
Nanvix with `--debug` option (see details below).

## Running

To run Nanvix, type the following command at the root directory:

```sh
bash tools/run/run.sh
```

The script above accepts some optional parameters to configure bochs.
Please, run `bash tools/run/run.sh --help` for more details.

## License and Maintainers

Nanvix is a free software that is under the GPL V3 license and is
maintained by Pedro H. Penna. Any questions or suggestions send him an
email: <pedrohenriquepenna@gmail.com>
