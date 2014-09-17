avr-makefile
============

A general purpose makefile for building avr programs.

# Directory Structure

For this makefile to work, you must place it in the root folder of your project. All ``.c`` files should be placed an a directory called ``src``, and all libraries should be placed in a directory called ``include``. The output appears in folders called ``obj`` for object files and ``hex`` for hex files.

# Rules

## compile

Compiles all C files in the src directory to object files in the obj directory. Creates the obj directory if it does not exist.

Usage: ``make compile``

## hex

Executes ``compile`` and then creates hex files using the object files and stores them in the hex directory. Creates the hex directory if it does not exist.

Usage: ``make hex``

## load

Executes ``hex`` and then uses ``teensy_loader_cli`` to load it onto the Teensy++ 2.0. ``teensy_loader_cli`` must be installed and in your path for this rule to work.

The ``teensy_loader_cli`` program can be found [here](https://www.pjrc.com/teensy/loader_cli.html).

The file to load is selected by overriding the ``MAIN_FILE`` variable. NOTE: Do not include the extension (ie. .c, .hex)

Usage: ``make load MAIN_FILE=part1``