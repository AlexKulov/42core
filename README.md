# 42core - basic ("core") submodule of the 42shell

## Brief.   
1. 42core - lightweight 42 fork and use in 42shell like submodule  
https://github.com/AlexKulov/42shell   
   
But, You can use this fork independently:   
2. For example, you can make 42core on Win by mingw32-make   
2.1 download glew(freeglut) to /c/path/to/    
2.2 change string 149 in Makefile:   
   ~~EXTERNDIR = /c/42ExternalSupport/~~   
     EXTERNDIR = /c/path/to/glew   
2.3 start mingw32-make from 42core folder   
   
3. You can start 42.exe. Condition:   
3.1 near 42.exe you need glew(freeglut) dll-file. Or you can try make 42.exe without GUI   
3.2 you need ./Model/Phobos.obj from origin 42 for start without GUI   
```
InOut/Inp_Sim.txt   
FALSE                            !  Graphics Front End?
```   
3.3 if start with GUI (Graphics Front End is TRUE), then you need   
./Model/Noise3DTex.raw   
./Model/GlastLogo.ppm   

## Branches

Now there is 2 branches:   
* master   
* server
* server+MPI   
Server branch only for console mode.   
You don't need anything except to compile (Make or CMake) and run.   
I left only 2 examples from the native 42: InOut and Standalone    
server+MPI: easy MPI test. You need MPI lib for Windows. Testing on Windows by MinGW64   
   
> My be in future will be exist branch "stm32"   

## More information   
  https://github.com/AlexKulov/42shell/blob/master/README.md


 

