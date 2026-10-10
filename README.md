# Primer Primitives

This repo contains values for color, spacing, and typography primitives for use with [Primer][primer], GitHub's design system.

## Install

This repository is distributed on [npm][npm]. After [installing npm][install-npm], you can install `@primer/primitives` with this command.

```sh
$ npm install --save @primer/primitives
```

## Usage

Primitive data is served in several formats from the `dist/` folder:

* `dist/scss` contains [SCSS][scss] files that define CSS variables to be imported into other SCSS files
* `dist/json` contains JSON files for each set of primitives
* `dist/js` contains CommonJS-style JavaScript modules for each set of primitives, as well as an index file that loads all of the primitives for all primitive types; you can access this via `require('@primer/primitives')`. The JavaScript modules also include TypeScript typings files for use in TypeScript projects.

## License

[MIT](./LICENSE) &copy; [GitHub](https://github.com/)

[primer]: https://github.com/primer/primer
[npm]: https://www.npmjs.com/
[install-npm]: https://docs.npmjs.com/getting-started/installing-node
[scss]: https://sass-lang.com/

# GitHub Codespaces ♥️ React

Welcome to your shiny new Codespace running React! We've got everything fired up and running for you to explore React.

You've got a blank canvas to work on from a git perspective as well. There's a single initial commit with the what you're seeing right now - where you go from here is up to you!

Everything you do here is contained within this one codespace. There is no repository on GitHub yet. If and when you’re ready you can click "Publish Branch" and we’ll create your repository and push up your project. If you were just exploring then and have no further need for this code then you can simply delete your codespace and it's gone forever.

This project was bootstrapped for you with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

We've already run this for you in the `Codespaces: server` terminal window below. If you need to stop the server for any reason you can just run `npm start` again to bring it back online.

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) in the built-in Simple Browser (`Cmd/Ctrl + Shift + P > Simple Browser: Show`) to view your running application.

The page will reload automatically when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
# Building Node.js

Depending on what platform or features you need, the build process may
differ. After you've built a binary, running the
test suite to confirm that the binary works as intended is a good next step.

If you can reproduce a test failure, search for it in the
[Node.js issue tracker](https://github.com/nodejs/node/issues) or
file a new issue.

## Table of contents

* [Supported platforms](#supported-platforms)
  * [Input](#input)
  * [Strategy](#strategy)
  * [Platform list](#platform-list)
  * [Supported toolchains](#supported-toolchains)
  * [Official binary platforms and toolchains](#official-binary-platforms-and-toolchains)
    * [OpenSSL asm support](#openssl-asm-support)
  * [Previous versions of this document](#previous-versions-of-this-document)
* [Building Node.js on supported platforms](#building-nodejs-on-supported-platforms)
  * [Prerequisites](#prerequisites)
  * [Unix and macOS](#unix-and-macos)
    * [Unix prerequisites](#unix-prerequisites)
    * [macOS prerequisites](#macos-prerequisites)
    * [Building Node.js](#building-nodejs-1)
    * [Installing Node.js](#installing-nodejs)
    * [Running Tests](#running-tests)
    * [Running Coverage](#running-coverage)
    * [Building the documentation](#building-the-documentation)
    * [Building a debug build](#building-a-debug-build)
    * [Building an ASan build](#building-an-asan-build)
    * [Speeding up frequent rebuilds when developing](#speeding-up-frequent-rebuilds-when-developing)
    * [Troubleshooting Unix and macOS builds](#troubleshooting-unix-and-macos-builds)
  * [Windows](#windows)
    * [Windows Prerequisites](#windows-prerequisites)
      * [Option 1: Manual install](#option-1-manual-install)
      * [Option 2: Automated install with Boxstarter](#option-2-automated-install-with-boxstarter)
    * [Building Node.js](#building-nodejs-2)
  * [Android](#android)
* [`Intl` (ECMA-402) support](#intl-ecma-402-support)
  * [Build with full ICU support (all locales supported by ICU)](#build-with-full-icu-support-all-locales-supported-by-icu)
    * [Unix/macOS](#unixmacos)
    * [Windows](#windows-1)
  * [Trimmed: `small-icu` (English only) support](#trimmed-small-icu-english-only-support)
    * [Unix/macOS](#unixmacos-1)
    * [Windows](#windows-2)
  * [Building without Intl support](#building-without-intl-support)
    * [Unix/macOS](#unixmacos-2)
    * [Windows](#windows-3)
  * [Use existing installed ICU (Unix/macOS only)](#use-existing-installed-icu-unixmacos-only)
  * [Build with a specific ICU](#build-with-a-specific-icu)
    * [Unix/macOS](#unixmacos-3)
    * [Windows](#windows-4)
* [Configuring OpenSSL config appname](#configure-openssl-appname)
* [Building Node.js with FIPS-compliant OpenSSL](#building-nodejs-with-fips-compliant-openssl)
* [Building Node.js with external core modules](#building-nodejs-with-external-core-modules)
  * [Unix/macOS](#unixmacos-4)
  * [Windows](#windows-5)
* [Note for downstream distributors of Node.js](#note-for-downstream-distributors-of-nodejs)

## Supported platforms

This list of supported platforms is current as of the branch/release to
which it belongs.

### Input

Node.js relies on V8 and libuv. We adopt a subset of their supported platforms.

### Strategy

There are three support tiers:

* **Tier 1**: These platforms represent the majority of Node.js users. The
  Node.js Build Working Group maintains infrastructure for full test coverage.
  Test failures on tier 1 platforms will block releases.
* **Tier 2**: These platforms represent smaller segments of the Node.js user
  base. The Node.js Build Working Group maintains infrastructure for full test
  coverage. Test failures on tier 2 platforms will block releases.
  Infrastructure issues may delay the release of binaries for these platforms.
* **Experimental**: May not compile or test suite may not pass. The core team
  does not create releases for these platforms. Test failures on experimental
  platforms do not block releases. Contributions to improve support for these
  platforms are welcome.

Platforms may move between tiers between major release lines. The table below
will reflect those changes.

### Platform list

Node.js compilation/execution support depends on operating system, architecture,
and libc version. The table below lists the support tier for each supported
combination. A list of [supported compile toolchains](#supported-toolchains) is
also supplied for tier 1 platforms.

**For production applications, run Node.js on supported platforms only.**

Node.js does not support a platform version if a vendor has expired support
for it. In other words, Node.js does not support running on End-of-Life (EoL)
platforms. This is true regardless of entries in the table below.

| Operating System | Architectures    | Versions                          | Support Type                                    | Notes                                |
| ---------------- | ---------------- | --------------------------------- | ----------------------------------------------- | ------------------------------------ |
| GNU/Linux        | x64              | kernel >= 4.18[^1], glibc >= 2.28 | Tier 1                                          | e.g. Ubuntu 20.04, Debian 10, RHEL 8 |
| GNU/Linux        | x64              | kernel >= 3.10, musl >= 1.1.19    | Experimental                                    | e.g. Alpine 3.8                      |
| GNU/Linux        | x86              | kernel >= 3.10, glibc >= 2.17     | Experimental                                    | Downgraded as of Node.js 10          |
| GNU/Linux        | arm64            | kernel >= 4.18[^1], glibc >= 2.28 | Tier 1                                          | e.g. Ubuntu 20.04, Debian 10, RHEL 8 |
| GNU/Linux        | armv7            | kernel >= 4.18[^1], glibc >= 2.28 | Tier 1                                          | e.g. Ubuntu 20.04, Debian 11         |
| GNU/Linux        | armv6            | kernel >= 4.14, glibc >= 2.24     | Experimental                                    | Downgraded as of Node.js 12          |
| GNU/Linux        | ppc64le >=power8 | kernel >= 4.18[^1], glibc >= 2.28 | Tier 2                                          | e.g. Ubuntu 20.04, RHEL 8            |
| GNU/Linux        | s390x            | kernel >= 4.18[^1], glibc >= 2.28 | Tier 2                                          | e.g. RHEL 8                          |
| GNU/Linux        | loong64          | kernel >= 5.19, glibc >= 2.36     | Experimental                                    |                                      |
| Windows          | x64, x86 (WoW64) | >= Windows 10/Server 2016         | Tier 1                                          | [^2],[^3]                            |
| Windows          | x86 (native)     | >= Windows 10/Server 2016         | Tier 1 (running) / Experimental (compiling)[^4] |                                      |
| Windows          | x64, x86         | Windows 8.1/Server 2012           | Experimental                                    |                                      |
| Windows          | arm64            | >= Windows 10                     | Tier 2                                          |                                      |
| macOS            | x64              | >= 11.0                           | Tier 1                                          | For notes about compilation see [^5] |
| macOS            | arm64            | >= 11.0                           | Tier 1                                          |                                      |
| SmartOS          | x64              | >= 18                             | Tier 2                                          |                                      |
| AIX              | ppc64be >=power8 | >= 7.2 TL04                       | Tier 2                                          |                                      |
| FreeBSD          | x64              | >= 13.2                           | Experimental                                    |                                      |

<!--lint disable final-definition-->

[^1]: Older kernel versions may work. However, official Node.js release
    binaries are [built on RHEL 8 systems](#official-binary-platforms-and-toolchains)
    with kernel 4.18.

[^2]: On Windows, running Node.js in Windows terminal emulators
    like `mintty` requires the usage of [winpty](https://github.com/rprichard/winpty)
    for the tty channels to work (e.g. `winpty node.exe script.js`).
    In "Git bash" if you call the node shell alias (`node` without the `.exe`
    extension), `winpty` is used automatically.

[^3]: The Windows Subsystem for Linux (WSL) is not
    supported, but the GNU/Linux build process and binaries should work. The
    community will only address issues that reproduce on native GNU/Linux
    systems. Issues that only reproduce on WSL should be reported in the
    [WSL issue tracker](https://github.com/Microsoft/WSL/issues). Running the
    Windows binary (`node.exe`) in WSL will not work without workarounds such as
    stdio redirection.

[^4]: Running Node.js on x86 Windows should work and binaries
    are provided. However, tests in our infrastructure only run on WoW64.
    Furthermore, compiling on x86 Windows is Experimental and
    may not be possible.

[^5]: Our macOS x64 Binaries are compiled with 11.0 as a target. Xcode 13 is
    required to compile.

<!--lint enable final-definition-->

### Supported toolchains

Depending on the host platform, the selection of toolchains may vary.

| Operating System | Compiler Versions                                              |
| ---------------- | -------------------------------------------------------------- |
| Linux            | GCC >= 10.1                                                    |
| Windows          | Visual Studio >= 2022 with the Windows 10 SDK on a 64-bit host |
| macOS            | Xcode >= 13 (Apple LLVM >= 12)                                 |

### Official binary platforms and toolchains

Binaries at <https://nodejs.org/download/release/> are produced on:

| Binary package          | Platform and Toolchain                                                                                      |
| ----------------------- | ----------------------------------------------------------------------------------------------------------- |
| aix-ppc64               | AIX 7.2 TL04 on PPC64BE with GCC 10                                                                         |
| darwin-x64              | macOS 11, Xcode 13 with -mmacosx-version-min=11.0                                                           |
| darwin-arm64 (and .pkg) | macOS 11 (arm64), Xcode 13 with -mmacosx-version-min=11.0                                                   |
| linux-arm64             | RHEL 8 with GCC 10[^6]                                                                                      |
| linux-armv7l            | Cross-compiled on RHEL 8 x64 with [custom GCC toolchain](https://github.com/rvagg/rpi-newer-crosstools)[^7] |
| linux-ppc64le           | RHEL 8 with gcc-toolset-10[^6]                                                                              |
| linux-s390x             | RHEL 8 with gcc-toolset-10[^6]                                                                              |
| linux-x64               | RHEL 8 with gcc-toolset-10[^6]                                                                              |
| win-x64 and win-x86     | Windows Server 2022 (x64) with Visual Studio 2022                                                           |

<!--lint disable final-definition-->

[^6]: Binaries produced on these systems are compatible with glibc >= 2.28
    and libstdc++ >= 6.0.25 (`GLIBCXX_3.4.25`). These are available on
    distributions natively supporting GCC 8.1 or higher, such as Debian 10,
    RHEL 8 and Ubuntu 20.04.

[^7]: Binaries produced on these systems are compatible with glibc >= 2.28
    and libstdc++ >= 6.0.28 (`GLIBCXX_3.4.28`). These are available on
    distributions natively supporting GCC 9.3 or higher, such as Debian 11,
    Ubuntu 20.04.

<!--lint enable final-definition-->

#### OpenSSL asm support

OpenSSL-1.1.1 requires the following assembler version for use of asm
support on x86\_64 and ia32.

For use of AVX-512,

* gas (GNU assembler) version 2.26 or higher
* nasm version 2.11.8 or higher in Windows

AVX-512 is disabled for Skylake-X by OpenSSL-1.1.1.

For use of AVX2,

* gas (GNU assembler) version 2.23 or higher
* Xcode version 5.0 or higher
* llvm version 3.3 or higher
* nasm version 2.10 or higher in Windows

Please refer to <https://docs.openssl.org/1.1.1/man3/OPENSSL_ia32cap/> for details.

If compiling without one of the above, use `configure` with the
`--openssl-no-asm` flag. Otherwise, `configure` will fail.

### Previous versions of this document

Supported platforms and toolchains change with each major version of Node.js.
This document is only valid for the current major version of Node.js.
Consult previous versions of this document for older versions of Node.js:

* [Node.js 21](https://github.com/nodejs/node/blob/v21.x/BUILDING.md)
* [Node.js 20](https://github.com/nodejs/node/blob/v20.x/BUILDING.md)
* [Node.js 18](https://github.com/nodejs/node/blob/v18.x/BUILDING.md)

## Building Node.js on supported platforms

### Prerequisites

* [A supported version of Python][Python versions] for building and testing.
* Memory: at least 8GB of RAM is typically required when compiling with 4 parallel jobs (e.g: `make -j4`)

### Unix and macOS

#### Unix prerequisites

* `gcc` and `g++` >= 10.1 or newer
* GNU Make 3.81 or newer
* [A supported version of Python][Python versions]
  * For test coverage, your Python installation must include pip.

Installation via Linux package manager can be achieved with:

* Ubuntu, Debian: `sudo apt-get install python3 g++ make python3-pip`
* Fedora: `sudo dnf install python3 gcc-c++ make python3-pip`
* CentOS and RHEL: `sudo yum install python3 gcc-c++ make python3-pip`
* OpenSUSE: `sudo zypper install python3 gcc-c++ make python3-pip`
* Arch Linux, Manjaro: `sudo pacman -S python gcc make python-pip`

FreeBSD and OpenBSD users may also need to install `libexecinfo`.

#### macOS prerequisites

* Xcode Command Line Tools >= 13 for macOS
* [A supported version of Python][Python versions]
  * For test coverage, your Python installation must include pip.

macOS users can install the `Xcode Command Line Tools` by running
`xcode-select --install`. Alternatively, if you already have the full Xcode
installed, you can find them under the menu `Xcode -> Open Developer Tool ->
More Developer Tools...`. This step will install `clang`, `clang++`, and
`make`.

#### Building Node.js

If the path to your build directory contains a space, the build will likely
fail.

To build Node.js:

```bash
./configure
make -j4
```

We can speed up the builds by using [Ninja](https://ninja-build.org/). For more
information, see
[Building Node.js with Ninja](doc/contributing/building-node-with-ninja.md).

The `-j4` option will cause `make` to run 4 simultaneous compilation jobs which
may reduce build time. For more information, see the
[GNU Make Documentation](https://www.gnu.org/software/make/manual/html_node/Parallel.html).

The above requires that `python` resolves to a supported version of
Python. See [Prerequisites](#prerequisites).

After building, setting up [firewall rules](tools/macos-firewall.sh) can avoid
popups asking to accept incoming network connections when running tests.

Running the following script on macOS will add the firewall rules for the
executable `node` in the `out` directory and the symbolic `node` link in the
project's root directory.

```bash
sudo ./tools/macos-firewall.sh
```

#### Installing Node.js

To install this version of Node.js into a system directory:

```bash
[sudo] make install
```

#### Running tests

To verify the build:

```bash
make test-only
```

At this point, you are ready to make code changes and re-run the tests.

If you are running tests before submitting a pull request, use:

```bash
make -j4 test
```

`make -j4 test` does a full check on the codebase, including running linters and
documentation tests.

To run the linter without running tests, use
`make lint`/`vcbuild lint`. It will lint JavaScript, C++, and Markdown files.

To fix auto fixable JavaScript linting errors, use `make lint-js-fix`.

If you are updating tests and want to run tests in a single test file
(e.g. `test/parallel/test-stream2-transform.js`):

```bash
tools/test.py test/parallel/test-stream2-transform.js
```

You can execute the entire suite of tests for a given subsystem
by providing the name of a subsystem:

```bash
tools/test.py child-process
```

You can also execute the tests in a test suite directory
(such as `test/message`):

```bash
tools/test.py test/message
```

If you want to check the other options, please refer to the help by using
the `--help` option:

```bash
tools/test.py --help
```

> Note: On Windows you should use `python3` executable.
> Example: `python3 tools/test.py test/message`

You can usually run tests directly with node:

```bash
./node test/parallel/test-stream2-transform.js
```

> Info: `./node` points to your local Node.js build.

Remember to recompile with `make -j4` in between test runs if you change code in
the `lib` or `src` directories.

The tests attempt to detect support for IPv6 and exclude IPv6 tests if
appropriate. If your main interface has IPv6 addresses, then your
loopback interface must also have '::1' enabled. For some default installations
on Ubuntu, that does not seem to be the case. To enable '::1' on the
loopback interface on Ubuntu:

```bash
sudo sysctl -w net.ipv6.conf.lo.disable_ipv6=0
```

You can use
[node-code-ide-configs](https://github.com/nodejs/node-code-ide-configs)
to run/debug tests if your IDE configs are present.

#### Running coverage

It's good practice to ensure any code you add or change is covered by tests.
You can do so by running the test suite with coverage enabled:

```bash
./configure --coverage
make coverage
```

A detailed coverage report will be written to `coverage/index.html` for
JavaScript coverage and to `coverage/cxxcoverage.html` for C++ coverage.

If you only want to run the JavaScript tests then you do not need to run
the first command (`./configure --coverage`). Run `make coverage-run-js`,
to execute JavaScript tests independently of the C++ test suite:

```bash
make coverage-run-js
```

If you are updating tests and want to collect coverage for a single test file
(e.g. `test/parallel/test-stream2-transform.js`):

```bash
make coverage-clean
NODE_V8_COVERAGE=coverage/tmp tools/test.py test/parallel/test-stream2-transform.js
make coverage-report-js
```

You can collect coverage for the entire suite of tests for a given subsystem
by providing the name of a subsystem:

```bash
make coverage-clean
NODE_V8_COVERAGE=coverage/tmp tools/test.py --mode=release child-process
make coverage-report-js
```

The `make coverage` command downloads some tools to the project root directory.
To clean up after generating the coverage reports:

```bash
make coverage-clean
```

#### Building the documentation

To build the documentation:

This will build Node.js first (if necessary) and then use it to build the docs:

```bash
make doc
```

If you have an existing Node.js build, you can build just the docs with:

```bash
NODE=/path/to/node make doc-only
```

To read the man page:

```bash
man doc/node.1
```

If you prefer to read the full documentation in a browser, run the following.

```bash
make docserve
```

This will spin up a static file server and provide a URL to where you may browse
the documentation locally.

If you're comfortable viewing the documentation using the program your operating
system has associated with the default web browser, run the following.

```bash
make docopen
```

This will open a file URL to a one-page version of all the browsable HTML
documents using the default browser.

```bash
make docclean
```

This will clean previously built doc.

To test if Node.js was built correctly:

```bash
./node -e "console.log('Hello from Node.js ' + process.version)"
```

#### Building a debug build

If you run into an issue where the information provided by the JS stack trace
is not enough, or if you suspect the error happens outside of the JS VM, you
can try to build a debug enabled binary:

```bash
./configure --debug
make -j4
```

`make` with `./configure --debug` generates two binaries, the regular release
one in `out/Release/node` and a debug binary in `out/Debug/node`, only the
release version is actually installed when you run `make install`.

To use the debug build with all the normal dependencies overwrite the release
version in the install directory:

```bash
make install PREFIX=/opt/node-debug/
cp -a -f out/Debug/node /opt/node-debug/node
```

When using the debug binary, core dumps will be generated in case of crashes.
These core dumps are useful for debugging when provided with the
corresponding original debug binary and system information.

Reading the core dump requires `gdb` built on the same platform the core dump
was captured on (i.e. 64-bit `gdb` for `node` built on a 64-bit system, Linux
`gdb` for `node` built on Linux) otherwise you will get errors like
`not in executable format: File format not recognized`.

Example of generating a backtrace from the core dump:

```bash
$ gdb /opt/node-debug/node core.node.8.1535359906
(gdb) backtrace
```

#### Building an ASan build

[ASan](https://github.com/google/sanitizers) can help detect various memory
related bugs. ASan builds are currently only supported on linux.
If you want to check it on Windows or macOS or you want a consistent toolchain
on Linux, you can try [Docker](https://www.docker.com/products/docker-desktop/)
(using an image like `gengjiawen/node-build:2020-02-14`).

The `--debug` is not necessary and will slow down build and testing, but it can
show clear stacktrace if ASan hits an issue.

```bash
./configure --debug --enable-asan && make -j4
make test-only
```

#### Speeding up frequent rebuilds when developing

Tips: The `ccache` utility is widely used and should generally work fine.
If you encounter any difficulties, consider disabling `mold` as a
troubleshooting step.

If you plan to frequently rebuild Node.js, especially if using several
branches, installing `ccache` can help to greatly reduce build
times. Set up with:

On GNU/Linux:

Tips: `mold` can speed up the link process, which can't be cached, you may
need to install the latest version but not the apt version.

```bash
sudo apt install ccache mold   # for Debian/Ubuntu, included in most Linux distros
export CC="ccache gcc"         # add to your .profile
export CXX="ccache g++"        # add to your .profile
export LDFLAGS="-fuse-ld=mold" # add to your .profile
```

Refs:

1. <https://ccache.dev/performance.html>
2. <https://github.com/rui314/mold>

On macOS:

```bash
brew install ccache            # see https://brew.sh
export CC="ccache cc"          # add to ~/.zshrc or other shell config file
export CXX="ccache c++"        # add to ~/.zshrc or other shell config file
```

This will allow for near-instantaneous rebuilds when switching branches back
and forth that were built with cache.

When modifying only the JS layer in `lib`, it is possible to externally load it
without modifying the executable:

```bash
./configure --node-builtin-modules-path "$(pwd)"
```

The resulting binary won't include any JS files and will try to load them from
the specified directory. The JS debugger of Visual Studio Code supports this
configuration since the November 2020 version and allows for setting
breakpoints.

#### Troubleshooting Unix and macOS builds

Stale builds can sometimes result in `file not found` errors while building.
This and some other problems can be resolved with `make distclean`. The
`distclean` recipe aggressively removes build artifacts. You will need to
build again (`make -j4`). Since all build artifacts have been removed, this
rebuild may take a lot more time than previous builds. Additionally,
`distclean` removes the file that stores the results of `./configure`. If you
ran `./configure` with non-default options (such as `--debug`), you will need
to run it again before invoking `make -j4`.

If you received the error `nodejs g++ fatal error compilation terminated cc1plus`
during compilation, this is likely a memory issue and you should either provide
more RAM or create swap space to accommodate toolchain requirements or reduce
the number of parallel build tasks (`-j<n>`).

### Windows

#### Tips

You may need disable vcpkg integration if you got link error about symbol
redefine related to zlib.lib(zlib1.dll), even you never install it by hand,
as vcpkg is part of CLion and Visual Studio now.

```powershell
# find your vcpkg
# double check vcpkg install the related file
vcpkg owns zlib.lib
vcpkg owns zlib1.dll
vcpkg integrate remove
```

Refs:

1. <https://github.com/nodejs/node/issues/24448>
2. <https://github.com/microsoft/vcpkg/issues/37518> / <https://github.com/microsoft/vcpkg/discussions/37546>
3. [vcpkg](https://github.com/microsoft/vcpkg/)

#### Windows Prerequisites

##### Option 1: Manual install

* The current [version of Python][Python versions] from the
  [Microsoft Store](https://apps.microsoft.com/store/search?publisher=Python+Software+Foundation)
* The "Desktop development with C++" workload from
  [Visual Studio 2022 (17.6 or newer)](https://visualstudio.microsoft.com/downloads/)
  or the "C++ build tools" workload from the
  [Build Tools](https://aka.ms/vs/17/release/vs_buildtools.exe),
  with the default optional components
* Basic Unix tools required for some tests,
  [Git for Windows](https://git-scm.com/download/win) includes Git Bash
  and tools which can be included in the global `PATH`.
* The [NetWide Assembler](https://www.nasm.us/), for OpenSSL assembler modules.
  If not installed in the default location, it needs to be manually added
  to `PATH`. A build with the `openssl-no-asm` option does not need this, nor
  does a build targeting ARM64 Windows.

Optional requirements to build the MSI installer package:

* The .NET SDK component from [Visual Studio 2022](https://visualstudio.microsoft.com/downloads/)
  * This component can be installed via the Visual Studio Installer Application

Optional requirements for compiling for Windows on ARM (ARM64):

* Visual Studio 17.6.0 or newer
  > **Note:** There is [a bug](https://github.com/nodejs/build/issues/3739) in `17.10.x`
  > preventing Node.js from compiling.
* Visual Studio optional components
  * Visual C++ compilers and libraries for ARM64
  * Visual C++ ATL for ARM64
* Windows 10 SDK 10.0.17763.0 or newer

Optional requirements for compiling with ClangCL:

* Visual Studio optional components
  * C++ Clang Compiler for Windows
  * MSBuild support for LLVM toolset

NOTE: Currently we only support compiling with Clang that comes from Visual Studio.

##### Option 2: Automated install with Boxstarter

A [Boxstarter](https://boxstarter.org/) script can be used for easy setup of
Windows systems with all the required prerequisites for Node.js development.
This script will install the following [Chocolatey](https://chocolatey.org/)
packages:

* [Git for Windows](https://chocolatey.org/packages/git) with the `git` and
  Unix tools added to the `PATH`
* [Python 3.x](https://chocolatey.org/packages/python)
* [Visual Studio 2022 Build Tools](https://chocolatey.org/packages/visualstudio2022buildtools)
  with [Visual C++ workload](https://chocolatey.org/packages/visualstudio2022-workload-vctools)
* [NetWide Assembler](https://chocolatey.org/packages/nasm)

To install Node.js prerequisites using
[Boxstarter WebLauncher](https://boxstarter.org/weblauncher), visit
<https://boxstarter.org/package/nr/url?https://raw.githubusercontent.com/nodejs/node/HEAD/tools/bootstrap/windows_boxstarter>
with a supported browser.

Alternatively, you can use PowerShell. Run those commands from
an elevated (Administrator) PowerShell terminal:

```powershell
Set-ExecutionPolicy Unrestricted -Force
iex ((New-Object System.Net.WebClient).DownloadString('https://boxstarter.org/bootstrapper.ps1'))
get-boxstarter -Force
Install-BoxstarterPackage https://raw.githubusercontent.com/nodejs/node/HEAD/tools/bootstrap/windows_boxstarter -DisableReboots
refreshenv
```

The entire installation using Boxstarter will take up approximately 10 GB of
disk space.

#### Building Node.js

* Remember to first clone the Node.js repository with the Git command
  and head to the directory that Git created; If you haven't already
  ```powershell
  git clone https://github.com/nodejs/node.git
  cd node
  ```

> \[!TIP]
> If you are building from a Windows machine, symlinks are disabled by default, and can be enabled by cloning
> with the `-c core.symlinks=true` flag.
>
> ```powershell
> git clone -c core.symlinks=true <repository_url>
> ```

* If the path to your build directory contains a space or a non-ASCII character,
  the build will likely fail

To start the build process:

```powershell
.\vcbuild
```

To run the tests:

```powershell
.\vcbuild test
```

To test if Node.js was built correctly:

```powershell
Release\node -e "console.log('Hello from Node.js', process.version)"
```

### Android

Android is not a supported platform. Patches to improve the Android build are
welcome. There is no testing on Android in the current continuous integration
environment. The participation of people dedicated and determined to improve
Android building, testing, and support is encouraged.

Be sure you have downloaded and extracted
[Android NDK](https://developer.android.com/ndk) before in
a folder. Then run:

```bash
./android-configure <path to the Android NDK> <Android SDK version> <target architecture>
make -j4
```

The Android SDK version should be at least 24 (Android 7.0) and the target
architecture supports \[arm, arm64/aarch64, x86, x86\_64].

## `Intl` (ECMA-402) support

[Intl](doc/api/intl.md) support is
enabled by default.

### Build with full ICU support (all locales supported by ICU)

This is the default option.

#### Unix/macOS

```bash
./configure --with-intl=full-icu
```

#### Windows

```powershell
.\vcbuild full-icu
```

### Trimmed: `small-icu` (English only) support

In this configuration, only English data is included, but
the full `Intl` (ECMA-402) APIs. It does not need to download
any dependencies to function. You can add full data at runtime.

#### Unix/macOS

```bash
./configure --with-intl=small-icu
```

#### Windows

```powershell
.\vcbuild small-icu
```

### Building without Intl support

The `Intl` object will not be available, nor some other APIs such as
`String.normalize`.

#### Unix/macOS

```bash
./configure --without-intl
```

#### Windows

```powershell
.\vcbuild without-intl
```

### Use existing installed ICU (Unix/macOS only)

```bash
pkg-config --modversion icu-i18n && ./configure --with-intl=system-icu
```

If you are cross-compiling, your `pkg-config` must be able to supply a path
that works for both your host and target environments.

### Build with a specific ICU

You can find other ICU releases at
[the ICU homepage](https://icu.unicode.org/download).
Download the file named something like `icu4c-**##.#**-src.tgz` (or
`.zip`).

To check the minimum recommended ICU, run `./configure --help` and see
the help for the `--with-icu-source` option. A warning will be printed
during configuration if the ICU version is too old.

#### Unix/macOS

From an already-unpacked ICU:

```bash
./configure --with-intl=[small-icu,full-icu] --with-icu-source=/path/to/icu
```

From a local ICU tarball:

```bash
./configure --with-intl=[small-icu,full-icu] --with-icu-source=/path/to/icu.tgz
```

From a tarball URL:

```bash
./configure --with-intl=full-icu --with-icu-source=http://url/to/icu.tgz
```

#### Windows

First unpack latest ICU to `deps/icu`
[icu4c-**##.#**-src.tgz](https://icu.unicode.org/download) (or `.zip`)
as `deps/icu` (You'll have: `deps/icu/source/...`)

```powershell
.\vcbuild full-icu
```

### Configure OpenSSL appname

Node.js can use an OpenSSL configuration file by specifying the environment
variable `OPENSSL_CONF`, or using the command line option `--openssl-conf`, and
if none of those are specified will default to reading the default OpenSSL
configuration file `openssl.cnf`. Node.js will only read a section that is by
default named `nodejs_conf`, but this name can be overridden using the following
configure option:

```bash
./configure --openssl-conf-name=<some_conf_name>
```

## Building Node.js with FIPS-compliant OpenSSL

Node.js supports FIPS when statically or dynamically linked with OpenSSL 3 via
[OpenSSL's provider model](https://docs.openssl.org/3.0/man7/crypto/#OPENSSL-PROVIDERS).
It is not necessary to rebuild Node.js to enable support for FIPS.

See [FIPS mode](doc/api/crypto.md#fips-mode) for more information on how to
enable FIPS support in Node.js.

## Building Node.js with external core modules

It is possible to specify one or more JavaScript text files to be bundled in
the binary as built-in modules when building Node.js.

### Unix/macOS

This command will make `/root/myModule.js` available via
`require('/root/myModule')` and `./myModule2.js` available via
`require('myModule2')`.

```bash
./configure --link-module '/root/myModule.js' --link-module './myModule2.js'
```

### Windows

To make `./myModule.js` available via `require('myModule')` and
`./myModule2.js` available via `require('myModule2')`:

```powershell
.\vcbuild link-module './myModule.js' link-module './myModule2.js'
```

## Building to use shared dependencies at runtime

By default Node.js is built so that all dependencies are bundled into
the Node.js binary itself. This provides a single binary that includes
the correct versions of all dependencies on which it depends.

Some Node.js distributions, however, prefer to manage dependencies.
A number of `configure` options are provided to support this use case.

* For dependencies with native code, the first set of options allow
  Node.js to be built so that it uses a shared library
  at runtime instead of building and including the dependency
  in the Node.js binary itself. These options are in the
  `Shared libraries` section of the `configure` help
  (run `./configure --help` to get the complete list).
  They provide the ability to enable the use of a shared library,
  to set the name of the shared library, and to set the paths that
  contain the include and shared library files.

* For dependencies with JavaScript code (including WASM), the second
  set of options allow the Node.js binary to be built so that it loads
  the JavaScript for dependencies at runtime instead of being built into
  the Node.js binary itself. These options are in the `Shared builtins`
  section of the `configure` help
  (run `./configure --help` to get the complete list). They
  provide the ability to set the path to an external JavaScript file
  for the dependency to be used at runtime.

It is the responsibility of any distribution
shipping with these options to:

* ensure that the shared dependencies available at runtime
  match what is expected by the Node.js binary. A
  mismatch may result in crashes or unexpected behavior.
* fully test that Node.js operates as expected with the
  external dependencies. There may be little or no test coverage
  within the Node.js project CI for these non-default options.

## Note for downstream distributors of Node.js

The Node.js ecosystem is reliant on ABI compatibility within a major release.
To maintain ABI compatibility it is required that distributed builds of Node.js
be built against the same version of dependencies, or similar versions that do
not break their ABI compatibility, as those released by Node.js for any given
`NODE_MODULE_VERSION` (located in `src/node_version.h`).

When Node.js is built (with an intention to distribute) with an ABI
incompatible with the official Node.js builds (e.g. using a ABI incompatible
version of a dependency), please reserve and use a custom `NODE_MODULE_VERSION`
by opening a pull request against the registry available at
<https://github.com/nodejs/node/blob/HEAD/doc/abi_version_registry.json>.

[Python versions]: https://devguide.python.org/versions/
# Using GitHub Codespaces in Visual Studio Code

You can develop in your codespace directly in Visual Studio Code by connecting the GitHub Codespaces extension with your GitHub account.

## About GitHub Codespaces in Visual Studio Code

You can use your local install of Visual Studio Code to create, manage, work in, and delete codespaces. To use GitHub Codespaces in VS Code, you need to install the Codespaces extension. For more information on setting up GitHub Codespaces in VS Code, see [Prerequisites](#prerequisites).

By default, if you create a new codespace on GitHub, it will open in the browser. If you would prefer to open any new codespaces in VS Code automatically, you can set your default editor to be VS Code. For more information, see [Setting your default editor for GitHub Codespaces](/en/codespaces/setting-your-user-preferences/setting-your-default-editor-for-github-codespaces).

If you prefer to work in the browser, but want to continue using your existing VS Code extensions, themes, and shortcuts, you can turn on Settings Sync. For more information, see [Personalizing GitHub Codespaces for your account](/en/codespaces/setting-your-user-preferences/personalizing-github-codespaces-for-your-account#settings-sync).

## Prerequisites

To develop in a codespace directly in VS Code, you must install and sign into the GitHub Codespaces extension with your GitHub credentials. The GitHub Codespaces extension requires VS Code October 2020 Release 1.51 or later.

Use the Visual Studio Code Marketplace to install the [GitHub Codespaces](https://marketplace.visualstudio.com/items?itemName=GitHub.codespaces) extension. For more information, see [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) in the VS Code documentation.

1. In VS Code, in the Activity Bar, click the Remote Explorer icon.

   ![Screenshot of the Activity Bar. The icon for the "Remote Explorer" side bar (a rectangle overlaid by a circle) is highlighted with an orange outline.](/assets/images/help/codespaces/click-remote-explorer-icon-vscode.png)

   > \[!NOTE]
   > If the Remote Explorer is not displayed in the Activity Bar:
   >
   > 1. Access the Command Palette. For example, by pressing <kbd>Shift</kbd>+<kbd>Command</kbd>+<kbd>P</kbd> (Mac) / <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows/Linux).
   > 2. Type: `details`.
   > 3. Click **Codespaces: Details**.

2. Select "GitHub Codespaces" from the dropdown at the top of the "Remote Explorer" side bar, if it is not already selected.

3. Click **Sign in to GitHub**.

   ![Screenshot of the "Remote Explorer" side bar for "GitHub Codespaces" with the "Sign in to GitHub" button displayed.](/assets/images/help/codespaces/sign-in-to-view-codespaces-vscode.png)

4. If you are not currently signed in to GitHub you'll be prompted to do so. Go ahead and sign in.

5. When you're prompted to specify what you want to authorize, click the **Authorize** button for "GitHub."

6. If the authorization page is displayed, click **Authorize Visual-Studio-Code**.

## Creating a codespace in VS Code

After you connect your account on GitHub to the GitHub Codespaces extension, you can create a new codespace. For more information about the GitHub Codespaces extension, see the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=GitHub.codespaces).

1. In VS Code, in the Activity Bar, click the Remote Explorer icon.

   ![Screenshot of the Activity Bar. The icon for the "Remote Explorer" side bar (a rectangle overlaid by a circle) is highlighted with an orange outline.](/assets/images/help/codespaces/click-remote-explorer-icon-vscode.png)

   > \[!NOTE]
   > If the Remote Explorer is not displayed in the Activity Bar:
   >
   > 1. Access the Command Palette. For example, by pressing <kbd>Shift</kbd>+<kbd>Command</kbd>+<kbd>P</kbd> (Mac) / <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows/Linux).
   > 2. Type: `details`.
   > 3. Click **Codespaces: Details**.

2. Hover over the "Remote Explorer" side bar and click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-plus" aria-label="The plus icon" role="img"><path d="M7.75 2a.75.75 0 0 1 .75.75V7h4.25a.75.75 0 0 1 0 1.5H8.5v4.25a.75.75 0 0 1-1.5 0V8.5H2.75a.75.75 0 0 1 0-1.5H7V2.75A.75.75 0 0 1 7.75 2Z"></path></svg>.

   ![Screenshot of the "Remote Explorer" side bar for GitHub Codespaces. The tooltip "Create New Codespace" is displayed beside the plus sign button.](/assets/images/help/codespaces/create-codespace-vscode.png)

3. In the text box, type the name of the repository you want to develop in, then select it.

   ![Screenshot of "octo-org/he" entered into the text box and a list of four repositories that start with this string.](/assets/images/help/codespaces/choose-repository-vscode.png)

   A message is displayed at the right side of subsequent prompts telling you who will pay for the codespace.

   ![Screenshot of a prompt for a branch, with the message "Usage paid for by hubwriter."](/assets/images/help/codespaces/who-will-pay-vscode.png)

4. Click the branch you want to develop on.

5. If prompted to choose a dev container configuration file, choose a file from the list.

6. Click the machine type you want to use.

   > \[!NOTE]
   > Your choice of available machine types may be limited by a number of factors. These can include a policy configured for your organization, or a minimum machine type specification for your repository. For more information, see [Restricting access to machine types](/en/codespaces/managing-codespaces-for-your-organization/restricting-access-to-machine-types) and [Setting a minimum specification for codespace machines](/en/codespaces/setting-up-your-project-for-codespaces/configuring-dev-containers/setting-a-minimum-specification-for-codespace-machines).

## Opening a codespace in VS Code

1. In VS Code, in the Activity Bar, click the Remote Explorer icon.

   ![Screenshot of the Activity Bar. The icon for the "Remote Explorer" side bar (a rectangle overlaid by a circle) is highlighted with an orange outline.](/assets/images/help/codespaces/click-remote-explorer-icon-vscode.png)

   > \[!NOTE]
   > If the Remote Explorer is not displayed in the Activity Bar:
   >
   > 1. Access the Command Palette. For example, by pressing <kbd>Shift</kbd>+<kbd>Command</kbd>+<kbd>P</kbd> (Mac) / <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows/Linux).
   > 2. Type: `details`.
   > 3. Click **Codespaces: Details**.
2. Under "GitHub Codespaces", hover over the codespace you want to develop in.
3. Click the connection icon (a plug symbol).

   ![Screenshot of the "Remote Explorer" side bar. The connection icon for a codespace (a plug symbol) is highlighted with a dark orange outline.](/assets/images/help/codespaces/click-connect-to-codespace-icon-vscode.png)

## Changing the machine type in VS Code

Typically, you can run your codespace on a choice of remote machine types. These machine types offer a choice of hardware specifications ranging from 2 cores to 32 cores, although the full range of machine types may not always be available. Each machine type has a different level of resources and a different billing tier. For information, see [GitHub Codespaces billing](/en/billing/concepts/product-billing/github-codespaces).

By default the machine type with the lowest valid resources is used when you create a codespace. You can change the machine type of your codespace at any time.

> \[!NOTE]
> Your choice of available machine types may be limited by a number of factors. These can include a policy configured for your organization, or a minimum machine type specification for your repository. For more information, see [Restricting access to machine types](/en/codespaces/managing-codespaces-for-your-organization/restricting-access-to-machine-types) and [Setting a minimum specification for codespace machines](/en/codespaces/setting-up-your-project-for-codespaces/configuring-dev-containers/setting-a-minimum-specification-for-codespace-machines).

1. In VS Code, open the Command Palette with <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Mac) or <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows/Linux).

2. Search for and select "Codespaces: Change Machine Type."

   ![Screenshot of "change machine" entered as a search string and "Codespaces: Change Machine Type" in the dropdown list.](/assets/images/help/codespaces/vscode-change-machine-type-option.png)

3. If you're not following these instructions within a codespace, click the codespace that you want to change.

   ![Screenshot of a dropdown list of four codespaces.](/assets/images/help/codespaces/vscode-change-machine-choose-repo.png)

   If you are following these instructions in a codespace, the change will apply to the codespace you're working in.

4. Select the machine type you want to use.

5. If you're changing to a machine type with a different storage capacity, a prompt will appear asking if you would like to continue. Read the prompt and click **Yes** to accept.

If you changed to a virtual machine with a different storage capacity (for example, from 32 GB to 64 GB), your codespace will be unavailable for a short time while the machine type is changed. If the codespace is currently active, it will automatically be stopped. When the change is complete, you'll be able to restart the codespace running on the new machine type.

If you changed to a virtual machine with the same storage capacity, the change will be applied the next time you restart the codespace. An active codespace will not be stopped automatically. For more information on restarting a codespace, see [Stopping and starting a codespace](/en/codespaces/developing-in-a-codespace/stopping-and-starting-a-codespace#restarting-a-codespace).

## Deleting a codespace in VS Code

You can delete codespaces from within VS Code when you are not currently working in a codespace.

1. In VS Code, in the Activity Bar, click the Remote Explorer icon.

   ![Screenshot of the Activity Bar. The icon for the "Remote Explorer" side bar (a rectangle overlaid by a circle) is highlighted with an orange outline.](/assets/images/help/codespaces/click-remote-explorer-icon-vscode.png)

   > \[!NOTE]
   > If the Remote Explorer is not displayed in the Activity Bar:
   >
   > 1. Access the Command Palette. For example, by pressing <kbd>Shift</kbd>+<kbd>Command</kbd>+<kbd>P</kbd> (Mac) / <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows/Linux).
   > 2. Type: `details`.
   > 3. Click **Codespaces: Details**.
2. Under "GitHub Codespaces," right-click the codespace you want to delete.
3. Click **Delete Codespace**.

## Switching to VS Code Insiders in the web client

If you are using the VS Code web client, you can switch to the Insiders version of the application. For more information about this version of VS Code, see [Introducing the Insiders Build](https://code.visualstudio.com/blogs/2016/02/01/introducing_insiders_build) in the VS Code blog.

After you switch versions in a codespace, the web client will continue to use the Insiders version if you stop and restart the codespace. New codespaces that you create and open in the VS Code web client will also use the Insiders version.

1. In bottom left of the browser window that's displaying a codespace, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gear" aria-label="Manage" role="img"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg>**.

2. In the menu, select "Switch to Insiders Version."

   ![Screenshot of the VS Code web client. A gear icon is highlighted with an orange outline. "Switch to Insiders Version" is shown in the menu.](/assets/images/help/codespaces/codespaces-insiders-vscode.png)

3. Click **Reload**.

To switch back to the Stable version of VS Code, repeat the process but choose **Switch to Stable Version**. After you switch back, the codespace will continue to use the Stable version if you stop and restart the codespace. New codespaces that you create and open in the VS Code web client will also use the Stable version.

## Using the Insiders desktop application for Codespaces

To use GitHub Codespaces in the Insiders version of the VS Code desktop application, start or create your codespaces from within the VS Code Insiders application. For more information see [Creating a codespace in VS Code](#creating-a-codespace-in-vs-code) and [Opening a codespace in VS Code](#opening-a-codespace-in-vs-code) earlier in this article.

## Further reading

* [Using the Visual Studio Code Command Palette in GitHub Codespaces](/en/codespaces/reference/using-the-vs-code-command-palette-in-codespaces)
* [Using GitHub Copilot in GitHub Codespaces](/en/codespaces/reference/using-github-copilot-in-github-codespaces)<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>To-Do List</title>
  <style>
    :root {
      --bg: #f4f7fb;
      --card: #ffffff;
      --primary: #4f46e5;
      --primary-dark: #4338ca;
      --text: #1f2937;
      --muted: #6b7280;
      --danger: #ef4444;
      --success: #10b981;
      --border: #e5e7eb;
      --shadow: 0 10px 25px rgba(31, 41, 55, 0.08);
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, #eef2ff, #f8fafc);
      font-family: Arial, sans-serif;
      color: var(--text);
    }

    .app {
      width: min(90vw, 560px);
      background: var(--card);
      border-radius: 18px;
      box-shadow: var(--shadow);
      padding: 24px;
    }

    h1 {
      margin: 0 0 20px;
      font-size: 2rem;
      text-align: center;
    }

    .input-row {
      display: flex;
      gap: 10px;
      margin-bottom: 18px;
    }

    input[type="text"] {
      flex: 1;
      padding*
madib036/change-stack-84-b687f513/060a403
