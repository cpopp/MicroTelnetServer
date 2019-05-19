# utelnetserver

This is a simple implementation of a telnet server that will hook telnet clients up to the REPL.  The telnet server and associated logic run in the background so you can use the REPL or run other scripts with it.  A single client connection is supported at a time.

__Updated to support MPY v1.1__.

To get started with it just add the following to your `boot.py`

    import utelnetserver
    utelnetserver.start()

on boot you should see something like the following: `Telnet server started on 192.168.2.119:23`

I've only tested it with a telnet client on the mac, but with that it is as simple as:

    $ telnet 192.168.2.119
    Trying 192.168.2.119...
    Connected to esp_f4b4b3.
    Escape character is '^]'.

    >>> print("Hello!")
    Hello!

## Limitations
- One telnet client at a time
- No authentication support

## What is supported
- Telnet server is callback based
- Interact with REPL via a telnet client

## Other examples
The utelnetserver module is pretty straightforward, offering `start(port=23)` and `stop()` so you can start/stop it as needed or run it on a port different than the typical port 23 for telnet.

## Future Work
- Authentication support
- More robust handling of telnet control characters
- Won't restart after just a soft reboot due to https://github.com/micropython/micropython/issues/1896
