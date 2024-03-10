# Hacking the Filmbox Package

An attempt to parse [FBX][filmbox] files using Python.

## Background

I need to get [pyfbx][pyfbx] running on non-Windows machines, for work, but it
doesn't seem to be working. The [original author][nf] hasn't made much headway
on it for their own [reasons][thread], hope they're doing okay.

So this is to document my own efforts to poke about at it.

## Requirements

Based on the `requirements.txt` file provided:

- pybran=0.1.2
- numpy~=1.21.2

## Procedure

    git clone https://github.com/nannafudge/pyfbx
    cd pyfbx
    python -m venv filmbox && source filmbox/bin/activate       # recommended but optional
    pip install -r requirements.txt
    python setup.py install

After the above steps on Ubuntu 22.04 / Python 3.10, I was able to import `pyfbx`:

    from pyfbx import *

Doing `dir()` shows many methods under `pyfbx.core`, which should let me parse
FBX files, but doesn't seem to work on a file which I know contains some data.

[filmbox]: https://en.wikipedia.org/wiki/FBX
[pyfbx]: https://github.com/nannafudge/pyfbx
[nf]: https://github.com/nannafudge/
[thread]: https://github.com/nannafudge/pyfbx/issues/2#issuecomment-1026294475
