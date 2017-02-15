[![Build Status](https://travis-ci.org/GeoffWilliams/bmc_patrol.svg?branch=master)](https://travis-ci.org/GeoffWilliams/bmc_patrol)
# bmc_patrol

#### Table of Contents

1. [Description](#description)
1. [Usage - Configuration options and additional functionality](#usage)
1. [Reference - An under-the-hood peek at what the module is doing and how](#reference)
1. [Limitations - OS compatibility, etc.](#limitations)
1. [Development - Guide for contributing to the module](#development)

## Description

Install BMC agent using a tarball downloaded from a web server that contains a silent install script (`install.sh`)

## Setup

### What bmc_patrol affects
* Install a list of prereq_package
* Create a `patrol` user and group
* Download, extract and run the installer

## Usage

```puppet
class { "bmc_patrol":
  media_source   => "http://megacorp.com/software/BMCPATROL.tar",,
}
```
Download tarball from media source, extract and run installer

## Reference

### Classes
* `bmc_patrol` - Install BMC Patrol agent

## Limitations

* Proxies not supported
* The tarball must contain a directory with the same name as the downloaded file minus any `.tar.gz` extension.  Inside this directory, there must be an executable script called `install.sh`
* Not supported by Puppet, Inc.

## Development

PRs accepted :)

## Testing
This module supports testing using [PDQTest](https://github.com/GeoffWilliams/pdqtest).


Test can be executed with:

```
bundle install
bundle exec pdqtest all
```


See `.travis.yml` for a working CI example