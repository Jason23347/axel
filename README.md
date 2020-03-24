# AXEL LITE

#### Axel - Lightweight CLI download accelerator

this project is based on [axel-download-accelerator/axel](https://github.com/axel-download-accelerator/axel)

### differences

- removed search
- download 1 url only

## Building from source ##

Release tarballs contain a pre-generated buildsystem, but if you need to
edit/patch it, or you're building from a copy of the repository, then you may
need to run `autoreconf -i` to generate it. Further instructions are provided in
the [INSTALL](INSTALL) file. The basic actions for most users are:

    ./configure && make && make install

To build without SSL/TLS support, use `./configure --without-ssl`.

### Dependencies for release tarballs ###

* `gettext` (or `gettext-tiny`)
* `pkg-config`

Optional:

* `libssl` (OpenSSL, LibreSSL or compatible) -- for SSL/TLS support.

### Extra dependencies for building from snapshots ###

* `autoconf-archive`
* `autoconf`
* `automake`
* `autopoint`
* `txt2man`

### Building on Ubuntu from Git ###

#### Packages ####

* `build-essential`
* `autoconf`
* `autoconf-archive`
* `automake`
* `autopoint`
* `gettext`
* `libssl-dev`
* `pkg-config`

### Build instructions ###

	$ autoreconf -fiv
	$ ./configure && make && sudo make install

## Mac OS X ##
### Install with Homebrew ###

    brew install axel

### Building ##

Install the following homebrew packages:

	brew install autoconf-archive automake gettext openssl

You'll need to provide some extra options to autotools so it can find gettext
and openssl.

	GETTEXT=/usr/local/opt/gettext
	OPENSSL=/usr/local/opt/openssl
	PATH="$GETTEXT/bin:$PATH"

	autoreconf -fiv -I$GETTEXT/share/aclocal/

	CFLAGS="-I$GETTEXT/include -I$OPENSSL/include" \
	LDFLAGS=-L$GETTEXT/lib ./configure

You can just run `make` as usual after these steps.

## Related projects ##

* [aria2](https://github.com/aria2/aria2)
* [hget](https://github.com/huydx/hget)
* [lftp](https://github.com/lavv17/lftp)
* [nugget](https://github.com/maxogden/nugget)
* [pget](https://github.com/Code-Hex/pget)

## License ##

Axel is licensed under GPL-2+ with the OpenSSL exception.
