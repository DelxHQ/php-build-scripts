# Custom PHP build scripts for Genisys

## compile.sh

Use this script to build the custom PHP binary. Make sure you have ``make autoconf automake libtool m4 wget getconf gzip bzip2 bison g++``.

| Flag   | Description                                                  |
| ------ | ------------------------------------------------------------ |
| -t     | Set target                                                   |
| -j     | Set make threads to #                                        |
| -c     | Will force compile cURL                                      |
| -l     | Will compile with LevelDB support (not supported with PHP7)  |
| -f     | Enabling abusive optimizations...                            |

* If you want to compile it for arm devices, use arm-linux-musleabi-gcc 1.1.6 or later.

### Example:

| Target  | Arguments |
| ------- | --------- |
| linux64 | ``-t linux64 -l -j 2 -c -f x86_64`` |
| mac64   | ``-t mac64 -l -j -c -f``            |

## installer.sh

Script to install Genisys and PHP binaries.

| Flag   | Description                         |
| ------ | ----------------------------------- |
| -u     | Update Genisys.                     |
| -d     | Install directory                   |
| -v     | Channel (stable or development)     |

## jenkins.sh

PHP binaries provided by Genisys are build using this script. The script runs the ``compile.sh`` with some default arguments.
