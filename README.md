ZERO Stratum Standalone Miner 1.0
=================================

This miner is based on zcash's standalone miner from str4d. (http://z.cash)

It was modified by ocminer (https://www.suprnova.cc) for use with ZERO (https://bitcointalk.org/index.php?topic=1796036.0) on Stratum Pools
like https://zero.suprnova.cc

Currently only Linux is supported.

Building on Ubuntu 16.04:

sudo apt-get install \
      build-essential pkg-config libc6-dev m4 g++-multilib \
      autoconf libtool ncurses-dev unzip git python \
      zlib1g-dev wget bsdmainutils automake

git clone https://github.com/ocminer/zero-standaloneminer

cd zero-standaloneminer

./zcutil/fetch-params.sh
./zcutil/build.sh 

cd src

./zcash-miner -equihashsolver=tromp -stratum=stratum+tcp://zero.suprnova.cc:6568 -user=suprnova.1 -debug -printtoconsole -genproclimit=2

Replace the number after genproclimit by the threads you want to run on your system. Be aware that you net A LOT of RAM, so probably you don't want to run more
than 4 threads at all unless you have > 16 GB RAM. If your system becomes unresponsive after launching the miner you have too much threads running.

Notes:
This is a developer-version, a beta version. Shares will be found but the miner is very slow. At the time of this writing there are already optimized miners
available to the non-public (https://bitcointalk.org/index.php?topic=1796036.msg17938607#msg17938607) which gives those a major advantage against "normal" miners.
This miner was released as an incentive to also open source and release other miners and they hopefully will be available shortly.

