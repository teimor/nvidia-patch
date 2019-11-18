readme-autogen
==============

readme-autogen is a tool for internal usage, which purpose is to simplify maintenance of fresh and correct README files for this project.

It rebuilds REAME files from templates located in `templates` directory and driver data specified in `drivers.json` file.

## Requirements

* Python 3.4+

## Usage

Just run script. It will update files in your repo working copy.

add\_driver
==========

add\_driver is a tool for internal usage, which purpose is to simplify proper introduction of new driver records into `drivers.json` file.

## Requirements

* Python 3.4+

## Usage

Just run script. It will update files in your repo working copy.

## Synopsis

```
$ ./add_driver.py --help
usage: add_driver.py [-h] (-L | -W) [--variant VARIANT] [-P {GeForce,Quadro}]
                     [-w {win10,win7,ws2012,ws2016}] [--patch32 PATCH32]
                     [--patch64 PATCH64] [--skip-patch-check] [-U URL]
                     [--skip-url-check]
                     version

Adds new Nvidia driver into drivers.json file of in your repo working copy

positional arguments:
  version               driver version

optional arguments:
  -h, --help            show this help message and exit
  -U URL, --url URL     override driver link (default: None)
  --skip-url-check      skip driver URL check (default: False)

OS options:
  -L, --linux           add Linux driver (default: None)
  -W, --win             add Windows driver (default: None)

Windows-specific options:
  --variant VARIANT     driver variant (use for special cases like "Studio
                        Driver") (default: )
  -P {GeForce,Quadro}, --product {GeForce,Quadro}
                        product type (default: GeForce)
  -w {win10,win7,ws2012,ws2016}, --winseries {win10,win7,ws2012,ws2016}
                        Windows series (default: win10)
  --patch32 PATCH32     template for Windows 32bit patch URL (default:
                        https://raw.githubusercontent.com/keylase/nvidia-patch
                        /master/win/${winseries}_x64/${drvprefix}${version}/nv
                        cuvid32.1337)
  --patch64 PATCH64     template for Windows 64bit patch URL (default:
                        https://raw.githubusercontent.com/keylase/nvidia-patch
                        /master/win/${winseries}_x64/${drvprefix}${version}/nv
                        cuvid64.1337)
  --skip-patch-check    skip patch files presense test (default: False)
```