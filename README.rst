A browser-based frontend/gui for GDB
====================================


.. figure:: https://github.com/cs01/gdbgui/raw/master/screenshots/gdbgui.png
   :alt: gdbgui

.. image:: https://travis-ci.org/cs01/gdbgui.svg?branch=master
  :target: https://travis-ci.org/cs01/gdbgui

.. image:: https://img.shields.io/badge/pyPI-v0.7.4.2-blue.svg
  :target: https://pypi.python.org/pypi/gdbgui/

.. image:: https://img.shields.io/badge/python-2.7, 3.4, 3.5, pypy-blue.svg
  :target: https://pypi.python.org/pypi/gdbgui/

.. image:: https://img.shields.io/badge/development-active-green.svg
  :target: https://github.com/cs01/gdbgui

.. image:: https://badges.gitter.im/gdbgui/Lobby.svg
   :alt: Join the chat at https://gitter.im/gdbgui/Lobby
   :target: https://gitter.im/gdbgui/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge

.. image:: https://img.shields.io/badge/SayThanks.io-☼-blue.svg
  :target: https://saythanks.io/to/grassfedcode

.. image:: https://img.shields.io/gratipay/cs01.svg
  :target: https://gratipay.com/cs01/


A modern, browser-based frontend to gdb (gnu debugger). Add breakpoints,
view stack traces, and more in C, C++, Go, and Rust! Simply run
``gdbgui`` from the terminal and a new tab will open in your browser. `Screenshots <https://github.com/cs01/gdbgui#screenshots>`_ are below.

Install (tested on Linux only)
------------------------------

::

    [sudo] pip install gdbgui --upgrade

Since gdbgui is under active development, consider running this command fairly often.

Run
---

::

    gdbgui [binary to debug]

A new tab in your browser will open with gdbgui in it.

Features
--------
- Debug a different program in each tab (new gdb instance is spawned for each tab)
- Set/remove breakpoints
- View stack, threads
- Switch frame on stack, switch between threads
- Inspect memory in hex/character form
- View all registers
- Dropdown of all files used to compile binary, with autocomplete functionality
- Source code explorer with ability to jump to line
- Show assembly next to source code, highlighting current instruction. Can also step through instructions.

Why gdbgui?
-----------
- Actively developed and compatible with the latest version of gdb (7.12)
- Does only one thing: debugs programs. No integrated build system, no project settings, nothing to make things more complicated than they need to be. Just a lightweight frontend.
- Design influenced by the amazing Chrome debugger: source code on the left, side panel on the right with collapsable widgets, console on the bottom
- Full gdb command line utility built in
- Written in widely used languages (Python and JavaScript)
- Open source and free

Examples
--------
See `https://github.com/cs01/gdbgui/tree/master/examples <https://github.com/cs01/gdbgui/tree/master/examples>`_

Options
~~~~~~~
optional positional arguments:
  ``command``: (Optional) The binary and arguments to run in gdb. This is a way to script the intial loading of the inferior binary you wish to debug. For example ``gdbgui ./mybinary -myarg -flag1 -flag2``

optional arguments:
  -h, --help            show this help message and exit
  -p PORT, --port PORT  The port on which gdbgui will be hosted
  --host HOST           The host ip address on which gdbgui serve.
  -g GDB, --gdb GDB     Path to gdb executable.
  -v, --version         Print version
  --debug               The debug flag of this Flask application. Pass this
                        flag when debugging gdbgui itself to automatically
                        reload the server when changes are detected
  --no_browser          By default, the browser will open with gdb gui. Pass
                        this flag so the browser does not open.

Compatibility
-------------

``gdbgui`` has been tested to work in these environments. It may work in
other environments as well.

Python versions: 2.7, 3.4, 3.5, pypy

Operating systems: Ubuntu 14.04, Ubuntu 16.04

Browsers: Chrome, Firefox, Ubuntu Web Browser

Gdb: 7.7.1 (tested), 7.12 (tested), likely works with intermediate versions

Development
-----------
Contributions and bug fixes are welcome. Before creating an issue, make sure you are using the latest version of gdbgui
since it is under active development.

To get started with development, set up a new virtual environment, then
run

::

    git clone https://github.com/cs01/gdbgui
    cd gdbgui
    pip install -r gdbgui/requirements.txt
    python -m gdbgui/backend.py --debug

License
-------
This software is free for personal use, and $30 per developer per year for commercial use. PayPal receipt is valid proof of purchase of a gdbgui license. Commercial users will receive priority for feature requests, support, and bugfixes.

.. raw:: html

    <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
    <input type="hidden" name="cmd" value="_s-xclick">
    <input type="hidden" name="encrypted" value="-----BEGIN PKCS7-----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-----END PKCS7-----
    ">
    <input type="image" src="https://www.paypalobjects.com/en_US/i/btn/btn_buynowCC_LG.gif" border="0" name="submit" alt="PayPal - The safer, easier way to pay online!">
    <img alt="" border="0" src="https://www.paypalobjects.com/en_US/i/scr/pixel.gif" width="1" height="1">
    </form>



How Does it Work?
-----------------
It uses Python to manage gdb as a subprocess. Specifically, the `pygdbmi library <https://github.com/cs01/pygdbmi>`__,  which returns key/value pairs (dictionaries) that can be used to create a frontend. To make a usable frontend, first a server must made to interface with gdb. In this case, the Flask server is used, which does three things: creates a managed gdb subprocess with pygdbmi, spawns a separate thread to constantly check for output from the gdb subprocess, and creates endpoints for the browser including http requests and websocket connections.

As output is parsed in the reader thread, it is immediately sent to the frontend through the websocket. As the browser receives these websocket messages, it maintains the state of gdb (whether it's running, paused, or exited, where breakpoints are, what the stack is, etc.) and updates the DOM as appropriate. Of course, the browser also sends commands to gdb through the Flask server, which it does as needed when various buttons are pressed, or when the user enters a command-line command. The server also has access to the filesystem, so the client can show source code of any file.

``gdbgui`` was designed to be easily hackable and extendable. There is
no build system necessary to run or develop this app.

The main components of gdbgui are

1. ``backend.py``: The backend consists of a single Python file, which
   makes use of `pygdbmi <https://github.com/cs01/pygdbmi>`__ to
   interact with a gdb subprocess, and
   `Flask <http://flask.pocoo.org/>`__ to set up url routing, websockets,
   and http responses.

2. ``gdbgui.pug``: HTML file that defines the frontend

3. ``gdbgui.js``: The majority of the application is contained in this file. If dynamically updates the page, and maintains gdb state. It sends AJAX requests and uses websockets to interact with gdb through the server, then gets the response and updates the DOM as necessary.

4. ``gdbgui.css``: css stylesheet


Testing
~~~~~~~

``python setup.py test`` runs unit tests located in
``gdbgui/tests/test_app.py``. Add new tests there as necessary.


Future Improvements
-------------------

-  Hover over a variable in source code to see its value
-  Embed plotting tools to plot a variable's value over time
-  Assign values to variables / memory addresses
-  Embed a binary/decimal/hex calculator


Screenshots
-----------
Enter the binary and args just as you'd call them on the command line. Binary is restored when gdbgui is opened at a later time.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/load_binary_and_args.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/load_binary_and_args.png

Intuitive control of your program. From left to right: Run, Continue, Next, Step, Return, Next Instruction, Step Instruction, send interrupt signal (SIGINT) to inferior process.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/controls.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/controls.png

Stack/Threads
-------------------------
View all threads, the full stack on the active thread, the current frame on inactive threads. Switch between frames on the stack, or threads by pointing and clicking.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/stack_and_threads.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/stack_and_threads.png

Source Code
-----------
View source, assembly, add breakpoints. All symbols used to compile the target are listed in a dropdown above the source code viewer, and have autocompletion capabilities.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/source.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/source.png

With assembly. Note the bold line is the current instruction that gdb is stopped on.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/source_with_assembly.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/source_with_assembly.png


Variables and Expressions
------------------------------------------------

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/locals.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/locals.png

All variables and their values are displayed each time gdb pauses. Arbitrary expressions can be evaluated as well.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/expressions.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/expressions.png


Memory Viewer
-------------
All hex addresses are automatically converted to clickable links to explore memory. Length of memory is configurable. In this case 16 bytes are displayed per row.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/memory.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/memory.png


Registers
---------
View all registers. If a register was updated it is highlighted in yellow.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/registers.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/registers.png


gdb console
-----------
Read gdb output, and write to the gdb subprocess as desired. Don't let any gdb commandline skills you've developed go to waste.

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/console.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/console.png


gdbgui at launch:

.. image:: https://github.com/cs01/gdbgui/raw/master/screenshots/ready.png
  :target: https://github.com/cs01/gdbgui/raw/master/screenshots/ready.png
