# SGAT Technologies

Copyright (c) 2018 SGAT Technologies.\
Portions Copyright (c) 2014-2018 The Monero Project.\
Portions Copyright (c) 2012-2013 The Cryptonote developers.

## Development resources

- Web: [www.sgat-technologies.com](http://www.sgat-technologies.com/)
- GitHub: [https://github.com/sgat-technologies/sgat](https://github.com/sgat-technologies/sgat)

## What is SGAT ?

 - a public blockchain based on Monero and CryptoNote protocol
 - an innovative and scalable ecosystem offering tailor-made smart-contracts applications
 - a benefit in terms of reliability, confidentiality, security, ergonomics and portability
 - a platform dedicated to the community, an access to SGAT environement through a single member account
 - but also, a physical gateway to a virtual world and a place of exchange for a crypto-tech community
 
SGAT is one of the first decentralized smart-contracts and blockchain-based platform. 
While focusing on enhanced privacy and maintaining the transparency and security of our blockchain, 
we offer comprehensive and tailor-made transactions. Our ambition is to offer innovative smart-contracts 
solutions adapted to the challenges of today’s industries.

## Introduction

The real promise of the blockchain, what it will bring, is shared trust : trusted third parties can be 
replaced by these distributed books which are more accurate, more transparent and less expensive. 
In fact, like other industrial revolutions such as the steam engine or the Internet, 
the Blockchain will structurally change society.

SGAT has the ambition to be a strong player in this transformation by developing its own blockchain and 
its own crypto-currency, as well as a pre-blockchain application overlay. 
This platform will encompass all services and applications developed by SGAT. 
These services will focus on smart-contracts to ultimately have concrete applications that will be useful 
to everyone on a daily basis and in complete confidence.

## About this project

This is the core implementation of SGAT, forked from the Monero Project. It is open source and completely 
free to use without restrictions, except for those specified in the Monero license agreement below. 
There are no restrictions on anyone creating an alternative implementation of Monero or SGAT that uses the 
protocol and network in a compatible manner.

As with many development projects, the repository on Github is considered to be the "staging" area for 
the latest changes. Before changes are merged into that branch on the main repository, they are tested 
by individual developers in their own branches, submitted as a pull request, and then subsequently tested 
by contributors who focus on testing and code reviews. That having been said, the repository should be 
carefully considered before using it in a production environment, unless there is a patch in the repository 
for a particular show-stopping issue you are experiencing. It is generally a better idea to use a tagged 
release for stability.

Anyone is welcome to contribute to SGAT’s codebase! If you have a fix or code change, feel free to submit 
it as a pull request directly to the "master" branch. In cases where the change is relatively small or does 
not affect other parts of the codebase it may be merged in immediately by any one of the collaborators. 
On the other hand, if the change is particularly large or complex, it is expected that it will be discussed 
at length either well in advance of the pull request being submitted, or even directly on the pull request.

## License

See [LICENSE](LICENSE).

## Compiling SGAT from source

### Dependencies

The following table summarizes the tools and libraries required to build. A
few of the libraries are also included in this repository (marked as
"Vendored"). By default, the build uses the library installed on the system,
and ignores the vendored sources. However, if no library is found installed on
the system, then the vendored source will be built and used. The vendored
sources are also used for statically-linked builds because distribution
packages often include only shared library binaries (`.so`) but not static
library archives (`.a`).

| Dep          | Min. version  | Vendored | Debian/Ubuntu pkg  | Arch pkg     | Fedora            | Optional | Purpose        |
| ------------ | ------------- | -------- | ------------------ | ------------ | ----------------- | -------- | -------------- |
| GCC          | 4.7.3         | NO       | `build-essential`  | `base-devel` | `gcc`             | NO       |                |
| CMake        | 3.0.0         | NO       | `cmake`            | `cmake`      | `cmake`           | NO       |                |
| pkg-config   | any           | NO       | `pkg-config`       | `base-devel` | `pkgconf`         | NO       |                |
| Boost        | 1.58          | NO       | `libboost-all-dev` | `boost`      | `boost-devel`     | NO       | C++ libraries  |
| OpenSSL      | basically any | NO       | `libssl-dev`       | `openssl`    | `openssl-devel`   | NO       | sha256 sum     |
| libzmq       | 3.0.0         | NO       | `libzmq3-dev`      | `zeromq`     | `cppzmq-devel`    | NO       | ZeroMQ library |
| libunbound   | 1.4.16        | YES      | `libunbound-dev`   | `unbound`    | `unbound-devel`   | NO       | DNS resolver   |
| libsodium    | ?             | NO       | `libsodium-dev`    | ?            | `libsodium-devel` | NO       | libsodium      |
| libminiupnpc | 2.0           | YES      | `libminiupnpc-dev` | `miniupnpc`  | `miniupnpc-devel` | YES      | NAT punching   |
| libunwind    | any           | NO       | `libunwind8-dev`   | `libunwind`  | `libunwind-devel` | YES      | Stack traces   |
| liblzma      | any           | NO       | `liblzma-dev`      | `xz`         | `xz-devel`        | YES      | For libunwind  |
| libreadline  | 6.3.0         | NO       | `libreadline6-dev` | `readline`   | `readline-devel`  | YES      | Input editing  |
| ldns         | 1.6.17        | NO       | `libldns-dev`      | `ldns`       | `ldns-devel`      | YES      | SSL toolkit    |
| expat        | 1.1           | NO       | `libexpat1-dev`    | `expat`      | `expat-devel`     | YES      | XML parsing    |
| GTest        | 1.5           | YES      | `libgtest-dev`^    | `gtest`      | `gtest-devel`     | YES      | Test suite     |
| Doxygen      | any           | NO       | `doxygen`          | `doxygen`    | `doxygen`         | YES      | Documentation  |
| Graphviz     | any           | NO       | `graphviz`         | `graphviz`   | `graphviz`        | YES      | Documentation  |
| pcsclite     | ?             | NO       | `libpcsclite-dev`  | ?            | `pcsc-lite pcsc-lite-devel` | NO | Ledger     |          


[^] On Debian/Ubuntu `libgtest-dev` only includes sources and headers. You must
build the library binary manually. This can be done with the following command ```sudo apt-get install libgtest-dev && cd /usr/src/gtest && sudo cmake . && sudo make && sudo mv libg* /usr/lib/ ```

Debian / Ubuntu one liner for all dependencies  
``` sudo apt update && sudo apt install build-essential cmake pkg-config libboost-all-dev libssl-dev libzmq3-dev libunbound-dev libsodium-dev libminiupnpc-dev libunwind8-dev liblzma-dev libreadline6-dev libldns-dev libexpat1-dev doxygen graphviz libpcsclite-dev ```

### Cloning the repository

Clone recursively to pull-in needed submodule(s):

`$ git clone --recursive https://github.com/sgat-technologies/sgat`

If you already have a repo cloned, initialize and update:

`$ cd sgat && git submodule init && git submodule update`

### Build instructions

The GENESIS and the NETWORK ID are hidden for this moment.\
The complete build instructions will be online once the ICO has finished.

You can still build and run the SGAT blockchain on a local testnet environment, the same way you build the Monero.