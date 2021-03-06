How to interface a PIC16F876 to a computer via RS232 serial comms, with Hi-Tech C
and VB 6 source code.

What you need:

- PIC16F876 on a breadboard.

- Schematic diagram for hardware(see the .gif file and the Protel 99 .sch file)

- MAX232 or SIPEX232 or MAX3222 (theres a lot of them around) serial chip for
  converting 5/0V logic levels of PIC to +13V/-13V logic levels of the RS232 port
  on a PC.

- Four capacitors above 1uF or more.

- A terminal program, such as HyperTerm for Windows for examining output from
  RS232 port.

Instructions

1.  Program your PIC with the supplied .hex file.  Remember to get the crystal
    speed correct.

2.  Get the schematics, including PIC, MAX232, etc working correctly.

3.  Run HyperTerm, using the supplied com1-19200.ht link.
      - The link is set up with:
        - COMx, N,8,1, 19200bps, no flow control
        - Local echo on, send line ends with line feeds, wrap lines (file..
          properties.. settings.. ascii setup.. "echo typed characters locally" and "send
          line ends ..." and "wrap lines"

4.  Apply power to the PIC, and you should see the following come up in HyperTerm:

    ----START OUTPUT FROM PIC----
    PICTest (c)2001 Shane Tolmie - see http://www.workingtex.com/htpic
    Starting up serial @ 19200 baud, N,8,1, no flow control ...

    This program tests the serial port.  It displays the text string '[alive]'
    every few seconds, and echoes back to the user the ascii value of the pressed
    key, plus one (+1), ie: putch(getch()+1)

    If the following test returns [pass] the EEPROM has been all initialized to
    0xEE by the downloaded .hex file (see eep_init.c). If [fail] it prints out the
    EEPROM contents for your examination.

    Testing EEPROM ... [pass]

    Key pressed:

    [alive] [alive] [alive] [alive] [alive] 12 [alive] ab
    ----END OUTPUT FROM PIC----


5.  As you can see, the PIC is communicating with the PC.  Notice how it echoes
    back everything you type, +1 ascii character, so typing '1' echos back '2'.

6.  To work out how Visual Basic connects to the PIC, see the attached archive
    'visual basic 6 terminal example.zip'. It is taken directly from the MSDN
    archive.




