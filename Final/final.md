# final

I made my patch! It was
No matter what I, I can't get loading samples to work

First I tried start up files, which continued to have memory alloc errors. So I added a memory size option. Then it loads, but it doesnt recognize the files!!

```
s.options.memSize = 8192 * 32 * 100;

```
I routed it to the subfolder and I wan't getting the alloc error, and then I tried to alloc memory and boot from the samples folder but I got the error again.
Then I got this errors

```
exception in real time: alloc failed, increase server's memory allocation (e.g. via ServerOptions)
```
then it could atleast find the folders, but it told me it failed to read them

```

WARNING: File reading failed for path: '/Users/bellecirino/Github/livecoding/Dirt/samples/advtime/algebraic.wav'



WARNING: File reading failed for path: '/Users/bellecirino/Github/livecoding/Dirt/samples/advtime/fall.wav'



WARNING: File reading failed for path: '/Users/bellecirino/Github/livecoding/Dirt/samples/advtime/glob.wav'



WARNING: File reading failed for path: '/Users/bellecirino/Github/livecoding/Dirt/samples/advtime/intro.wav'

```
it also told me there was a duplicate node ID

```
FAILURE IN SERVER /g_new duplicate node ID
```
wtf

this is my boot file right now:

```
s.options.memSize = 8192 * 32 * 50;
(
s.waitForBoot {
	~dirt = SuperDirt(2, s); // two output channels
	~dirt.loadSoundFiles("/Users/bellecirino/Github/livecoding/Dirt/samples/**"); // specify sample folder to load
	s.sync; // wait for supercollider to finish booting up
	~dirt.start(57120, 0 ! 12); // start superdirt, listening on port 57120, create twelve orbits each sending audio to channel 0
};
);
```
suddenly is doesn't see sd or bd now

```
no synth or sample named 'sd' could be found.
module 'sound': instrument not found: sd
no synth or sample named 'bd' could be found.
module 'sound': instrument not found: bd

```
Okay i'm gonna try to boot it normally using Superdirt.start;

suddenly that no longer works and i'm about to cry. time to reinstall supercollider and super dirt.

i'm copying the startup file from the forum and trying that

running the startup causes this message:

```
exception in GraphDef_Recv: UGen 'SwitchDelay' not installed.
exception in GraphDef_Recv: UGen 'MdaPiano' not installed.
exception in GraphDef_Load: UGen 'FM7' not installed.
*** ERROR: SynthDef dirt_delay2 not found
FAILURE IN SERVER /s_new SynthDef not found
```
which is weird because i literally just reinstalled every thing

atleast it sees the sample folders lol

```
2 existing sample banks:
advtime (4) test (0)
... file reading complete. Required 13 MB of memory.
```
YESSS IT PLAYS THE SAMPLES!!!!  finally omfg but it seems like a lot of other stuff is broken so im gonna try my original start file and see if that changes anything

hmm. okay same errors. this is so weird
okay so... none of the samples are working...
OHH its because i replaced the one that originally runs the files with my own.

I DID IT!!!!

so heres my start files
```

(
s.waitForBoot {
	~dirt = SuperDirt(2, s); // two output channels
	~dirt.loadSoundFiles("/Users/bellecirino/Github/livecoding/Dirt/samples/**"); // specify sample folder to load
	  ~dirt.loadSoundFiles;
	s.sync; // wait for supercollider to finish booting up
	~dirt.start(57120, 0 ! 12); // start superdirt, listening on port 57120, create twelve orbits each sending audio to channel 0
};
);
```

yay!!!:)


um actually nvm. i had it wokring for a while and then i tried to add a sample and it freaked out.

its getting this error


```

*** ERROR: SynthDef dirt_delay2 not found
FAILURE IN SERVER /s_new SynthDef not found
FAILURE IN SERVER /g_new duplicate node ID

```

im gonna. reinstall. again. yay.

thats not helping.. sahbdfiwaf.
im literally just opening super collidar and its getting a million errors

okay that was bc of startup file, which i deleted but i'm still getting the same errors when trying to boot

ok i have literally reinstalled everything

SAME ERRORSCJscsavad

im gonna restart ig bc i can't think of anything else to do...

that did nothing. i resinstalled super collidar. it feels like its missing a dependancy but it wont FIX IT KJWHBSAVKJzc

so samples work.. but it seems like two things are missing:
```
*** ERROR: SynthDef dirt_delay2 not found
FAILURE IN SERVER /s_new SynthDef not found

```
very strange, but i've spent too long on this and if it ain't broke...
