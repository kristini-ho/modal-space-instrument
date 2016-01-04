# modal-space-instrument
An instrument that takes live visual input from camera to manipulate sound intuitively.

One of my favorite projects I've done.
Programmed in Max/MSP with cnmat odot, makes uses of computer vision externals for jitter by Jean-Marc Pelletier. 
The odot and cv.jit externals will be necessary for the patches to run. Also uses keyboard and mouse abstractions from music 158 
at UC Berkeley, included in this repo.

Modal space began with my modal map, which mapped a grid of 17 different musical modes to different 
areas of a computer screen. Performers can play live notes (with continuous pitch range) on the
computer keyboard, and manipulate the mode continuously by moving the mouse around.
The "keys" of the instrument are simply the computer keyboard. Recording is also possible, and playing 
live over the recorded accompaniment in the same patch is a key feature. This is done by recording the 
gestures that the musician makes, and entering them in real time as though they were being played, when 
"Play" is clicked. Modulating based on the current state of the mouse. Information about both live and 
recorded music is displayed. Damped and clear sound are adjustable, each uses a different method for
creating the sound, one allows more blurred polyphonic sound using delegation of sound to another voice if
the current voice is busy, the other is simply crisp, one note at a time sound. I think of the blur as something 
akin to a piano pedal. Everything is continuous, from pitch to ratios of blur and clarity. 

Modal space was my grand extension of the modal map. I wanted a person's movements, color, 
proximity to the instrument to affect how it reacts. So I made use of cv.jit, and a blobs
abstraction by Rama Gottfried. Now the camera of the instrument tracks the number of blobs,
size of the blobs, overall color, etc. 

After some time, I filtered the masses of information that came through the camera to map:

- the overall color of the scene to the base pitch of the music (still continuous; 
tones are not necessarily the Western twelve tones), by summing over the rgb values
to determine which color was most prominent, and scaling it to a pitch
- the mode (the grid now based on the what the camera could capture) can be determined either 
by the location of the largest blob, the reddest, greenest, or bluest blob, depending on the choice of the user. 
- the level of chaos or damping is controlled by the number of objects in screen (number of blobs).
- the overal amplitude is determined by the size of the largest blob (how close the person is to the instrument).

There is, in addition, the ability to record the music created or improvised on this instrument into an audio file.

Some musical notes:

Some of my favorite modes to create were the Balinese ones,
intervals for which I deduced partially from listening and experience from playing the gamelan,
and partially from comparison to Western typical intervals. Notably, these required a different 
programming than the rest, as in Balinese music, there is an everpresent ambak or wave texture,
which is created by having two frequencies very close together struck at the same time by two different
instruments. A certain Chinese mode I used also required every note to be paired with another in specific
harmonic ratios.

Having the timbre, mode, underlying pitch of your music manipulated not by how you touch it, but by 
how you move leads to this release of control, handing some over to the instrument itself.
I've found experimenting with creating music on it myself, that some beautiful sounds I would never have
discovered came from handing over this to the instrument, which detects how I move and takes into 
account the particular attributes of the setting, were created. I think part of it comes
from the free movement between Western classical modes, jazz modes, non-Western musical modes. 
Often people are stuck in the context of music they grew up in, separating different forms of music,
but music is all music, and the barriers for modal travel are at least removed, in this digital
instrument. 


