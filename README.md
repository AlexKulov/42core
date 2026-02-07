# 42core - basic ("core") submodule of the 42shell

Brief.
1. 42core - lightweight fork and use in 42shell
https://github.com/AlexKulov/42shell   
   
But, You can use this fork independently:
2. For example, you can make 42core on Win by mingw32-make
2.1 download glew(freeglut) to /c/path/to/    
2.2 change string 149 in Makefile:   
from   EXTERNDIR = /c/42ExternalSupport/
to   EXTERNDIR = /c/path/to/glew
2.3 start mingw32-make from 42core folder

3. You can start 42.exe. Condition:   
3.1 near 42.exe you need glew(freeglut) dll-file. Or you can try make 42.exe without GUI
3.2 you need Model/Phobos.obj from origin 42 for start without GUI   
InOut/Inp_Sim.txt   
FALSE                            !  Graphics Front End?
3.3 if start with GUI (Graphics Front End is TRUE), then you need   
./Model/Noise3DTex.raw   
./Model/GlastLogo.ppm   

##More information   
  https://github.com/AlexKulov/42shell/blob/master/README.md


 

