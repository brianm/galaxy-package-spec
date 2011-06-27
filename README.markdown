# Galaxy Packaging Specification

## Overview
The Galaxy Packaging Specification provides a system for bundling applications.

## Package Format
The bundle is packaged up as a gzipped gnu tar file. There must be a single top level directory, but its name does not matter. That directory shalled be called the base directory. Within that directory there must be one file, at <code>bin/control</code>, there may be a file <code>bin/tools</code>. There may be a directory <code>env/</code>, but there must not be anything in that directory. The rest is up to the application.

All paths in this spec will be relative to the base directory.

## Control Protocol

There shall be a <code>bin/control</code> executable file, henceforth called the control script. The executable will support a number of commands, these commands are passed as command line arguments to the control script.

* start
* stop
* restart
* status
* version

The control script must not support additional commands.

### Start
### Stop
### Restart
### Status
### Version

## Environment Directory

There is a directory inside the base directory, at <code>env/</code>. This directory. The deployment system may place files there, for its own use, and for use by the application bundle. The application must not write to anything within the <code>env/</code> directory.

The application may read items from this directory, however. It is expected that deployment services will use this directory to pass information to the applications being deployed.

## Tool Extensions

An application may have a <code>bin/tools</code> executable. What this does is up to the implementation. 

# Status of Spec

This is a draft specification.

