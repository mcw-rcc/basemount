Bootstrap: docker
From: ubuntu:16.04

%labels
Maintainer Matthew Flister
Version v1.0

%help
This container runs Basemount.

%post
    mkdir -p /scratch/global /scratch/local /rcc/stor1/refdata /rcc/stor1/projects /rcc/stor1/depts

    # Install necessary packages.
    apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        gcc-multilib \
        ca-certificates \
        zlib1g-dev \
        libssl-dev \
        curl \
        wget
    apt-get clean
    rm -rf /var/lib/apt/lists/*
    bash -c "$(curl -L https://basemount.basespace.illumina.com/install)"
    wget "https://api.bintray.com/content/basespace/BaseSpaceCLI-EarlyAccess-BIN/latest/\$latest/amd64-linux/bs?bt_package=latest" -O /usr/local/bin/bs && chmod +x /usr/local/bin/bs
    wget "https://api.bintray.com/content/basespace/BaseSpace-Copy-BIN/\$latest/linux/bscp?bt_package=develop" -O /usr/local/bin/bs-cp && chmod +x /usr/local/bin/bs-cp

