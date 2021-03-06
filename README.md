====
mona

Fork of Corelan’s mona.py for x64dbg. mona is a Windows exploit development swiss army knife. It supports ROP techniques, SEH, cyclic patterns, etc.

To see all commands and usage details, run mona with the `help` command.

Installation instructions
-------------------------

### x64dbg
First, get [x64dbgpy](https://github.com/x64dbg/x64dbgpy) for x64dbg Python support. You can grab a release [here](https://ci.appveyor.com/project/mrexodia/x64dbg-python/build/artifacts). Drop the contents of the `plugins` directory into your x64dbg `plugins` folder. 

Then, put `mona.py` into the `plugins/x64dbgpy` folder. You will also need the `pykd.py` and `x64dbgpylib.py` files from https://github.com/x64dbg/x64dbgpylib. Finally, put the `clean_mona.py` script in `x64dbgpy/x64dbgpy/autorun`. 
 
Now, run mona commands at the x64dbg Python command line with `mona.mona(“command”)`.

### Immunity Debugger
Simply drop mona.py into the 'PyCommands' folder (inside the Immunity Debugger application folder).

### WinDBG
See https://github.com/corelan/windbglib

Some Supported Commands
-------------------------

* `modules` — Show all loaded modules and their properties (ASLR, Rebase, DEP, etc.)
* `heap` — Show heap related information
* `seh` — Find pointers to assist with SEH overwrite exploits
* `jmp` — Find pointers that will allow you to jump to a register
* `rop` — Finds gadgets that can be used in a ROP exploit and do ROP magic with them
* `jop` — Finds gadgets that can be used in a JOP exploit
* `pattern_offset` — Find location of 4 bytes in a cyclic pattern