# Alpine lx-brand Image Builder

[![Build Status](https://travis-ci.org/joyent/alpine-lx-brand-image-builder.svg?branch=master)](https://travis-ci.org/joyent/alpine-lx-brand-image-builder) (shellcheck)

This is a collection of scripts used for creating an lx-brand Alpine image.

## Requirements

In order to use these scripts you'll need:

- Alpine, Ubuntu or CentOS running in a VM (required for the `install` script). 
- A SmartOS (or SDC headnode) install (required for the `create-lx-image` script)

Note that the `install` script will fail if run in an lx-brand enironment.

## Usage

1. Run `./install -d <chroot> -m <mirror> -i <image name> -p <proper name> -u <image docs` uunder Alpine to install Alpine in a given directory. This will create a tarball of the installation in your working directory (named `<image name>-<YYMMDD>.tar.gz`). See `./install -h` for detailed usage.
2. Copy the tarball to a SmartOS machine or SDC headnode and run `./create-lx-image -t /full/path/to/<image name>-<YYMMDD>.tar.gz` (substituting the name of your tar file). This will create the image file and manifest.
