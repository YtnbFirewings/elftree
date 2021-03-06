# ELF tree

Show library dependency of an ELF binary in a tree form.  It supports
folding and expanding subtree and shows related information.

![screenshot](https://github.com/namhyung/elftree/blob/master/screenshot.png)

## Usage

    $ elftree
    Usage: elftree [<options>] <executable>

    $ elftree -h
    Usage of elftree:
      -p	Show library path
      -stdio
		Show it on standard IO
      -tui
		Show it with TUI (default true)
      -v	Show binary info

    $ elftree -stdio `which firefox`
    firefox
       libpthread.so.0
          libc.so.6
             ld-linux-x86-64.so.2
          ld-linux-x86-64.so.2
       libdl.so.2
          libc.so.6
          ld-linux-x86-64.so.2
       libstdc++.so.6
          libm.so.6
             libc.so.6
             ld-linux-x86-64.so.2
          libc.so.6
          ld-linux-x86-64.so.2
          libgcc_s.so.1
             libc.so.6
       libm.so.6
       libgcc_s.so.1
       libc.so.6
       ld-linux-x86-64.so.2

### TUI keys
* `f`: file header view
* `s`: section header view
* `d`: dynamic info view
* `y`: symbol view
* `ENTER`: toggle folding
* `TAB`: switch window
* `q`: quit

## How to install
If you have golang environment setup:

    $ go get github.com/namhyung/elftree

Or, just download the binary:

    $ wget https://github.com/namhyung/elftree/releases/download/v0.1/elftree-linux-amd64
    $ sudo install -D elftree-linux-amd64 /usr/local/bin/elftree

