# gprm

## Parallel programming finally made easy!
The Glasgow Parallel Reduction Machine, *GPRM*,  is a task-based parallel programming framework.


## PREREQUISITES:

The essential prerequisites to build parallel programs using GPRM are a C++11 compliant compiler and the SCons build system.

### A C++11 Compiler

In principle any C++11-compliant compiler is fine, I use `g++`.

- [g++ >= 4.8](http://gcc.gnu.org)


### The SCons Build Tool

For building GPRM-based applications you need `scons`:

- [scons >= 1.2.0](http://www.scons.org)
- [python >= 2.5.1](http://www.python.org)

## INSTALLATION:

    # `git clone` the repo

The environment variable `GPRM_DIR` must be set to full path to the `gprm` directory.

    $ cd gprm
    $ export GPRM_DIR=$PWD

The file `etc/gprmc` contains the environment settings for GPRM.
To source it, put

    source "$GPRM_DIR/etc/gprmrc"

in your `.bashrc` (Linux) or `.profile` (Mac)

That's it, you can start using GPRM!

## HOW TO USE:

Create a skeleton example `gprm-project-skeleton`:

    $ gprm -i

Or copy the example from `$GPRM_DIR/examples`. To build e.g. the `HelloWorld` example with 4 threads:

    $ gprm -t HelloTask -n 4

To run it:

    $ ./main

## To build the GPRM framework from sources (optional)

There is no real need to build the framework unless you want to tinker with it. In that case you also need:

#### Haskell

The actual GPC compiler and bytecode generator is written in `Haskell`.

- [ghc >= 7.6.3](http://www.haskell.org) to compile the Gannet compiler,
- Install the [Haskell Platform](http://hackage.haskell.org/platform/)

- Install the following Haskell packages with `cabal`:

        $ cabal install lens
        $ cabal install errors
        $ cabal install wl-pprint
        $ cabal install HsSyck

#### Perl

The extensive code generation done by the GPRM build system is done using `Perl`.

- [perl >= 5.12](http://www.perl.org)
- Install the YAML::Syck Perl module from [CPAN](http://search.cpan.org/dist/YAML-Syck/), the easiest way is to install `cpanm` first, then do

        $ cpanm YAML::Syck
