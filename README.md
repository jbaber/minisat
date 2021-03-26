Quick Install via make
======================

- Decide where to install the files . The simplest approach is to use
  GNU standard locations and just set a "prefix" for the root install
  directory (reffered to as $PREFIX below). More control can be
  achieved by overriding other of the GNU standard install locations
  (includedir, bindir, etc). Configuring with just a prefix:
  
      $ make config prefix=$PREFIX

- Compiling and installing:
      $ make install

Quick Install via modern CMake
==============================
    $ cmake -S . -B build
    $ cmake --build build -j
    
compiles into `build/`

Configuration
=============
- Multiple configuration steps can be joined into one call to "make
  config" by appending multiple variable assignments on the same line.

- The configuration is stored in the file "config.mk". Look here if
  you want to know what the current configuration looks like.

- To reset from defaults simply remove the "config.mk" file or call
  "make distclean".

- Recompilation can be done without the configuration step.

- *TODO: describe configuration possibilities for compile flags / modes*

Building
========
- *TODO: describe separate build modes*

Install
=======
- *TODO: ?*

Directory Overview
==================

minisat/mtl/            Mini Template Library
minisat/utils/          Generic helper code (I/O, Parsing, CPU-time, etc)
minisat/core/           A core version of the solver
minisat/simp/           An extended solver with simplification capabilities
doc/                    Documentation
README
LICENSE

Examples
========

Run minisat with same heuristics as version 2.0
-----------------------------------------------
    $ minisat <cnf-file> -no-luby -rinc=1.5 -phase-saving=0 -rnd-freq=0.02

If built with cmake
-------------------
    $ build/minisat <cnf-filename> <output-filename>
