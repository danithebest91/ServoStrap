ServoStrap
==========

servo-controlled reprap 3D printer:

this code take as input stepper information from a standard 3D printer motherboard
and use it to control a servo-motor with active position tracker.

 i have made this code for the LMD18245 motor controller, 
  i have merged the pid code of  Josh Kopel 
    whith the code of makerbot servo-controller board,
  you can use this code on the some board changing some values.
  Daniele Poddighe

   external ardware require a quadrature encoder, timing slit strip and a dc motor,
   all you can find inside an old printer, i have took it from canon and hp printers(psc1510)
   
   for motor controll you can choose different type of H-bridge, i have used LMD18245,
   you can order 3 of it on ti.com sample request, the hardware needed is explained on the datasheet but i'm drowing
   the schematic and PCB layout on eagle to make an integrated board aesy to add to ramps 1.4 or other printer motherboard
   
   improvements:
   
   1)moore faster movements on x-y axys, it mean less time to wait to print a part
   
   2)less noise from the motors, it will be silent
   
   3)the couple of the motor not decrease with the speed (like in a stepper motor)
   
   4)active position tracking, no more step losses, 
      almost all prints will end in perfect condition because if something stop 
      the head it will return to the print position
      
   5)less price to build a printer, almost all electronic woste (like 2D printers)
      have inside dc motors with all needed to control it
      
   6)resolution increased by fine setting PID costants and using angular encoder, doesn't matter if is slit disk or magnetic
   
   7)potentially endstops are not needed because the timing strip have special code at the begin/end 
     that can be interpreted as endstop
     
     
  To use the code you need first to put the two files called digitalWriteFast.h and Keywords.txt in a folder inside arduino/libraries
     
   
   here the youtube link of the test with this code: http://goo.gl/gAia5y
