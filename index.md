# Eric Wetzel CMPSC190D S24 Notes
My work done with Allolib during this class. Source code for my projects here: https://github.com/ericpretzel/allolib_playground

## Procedural music with Boids
The complex flocking and wandering behavior of "boids" comes from relatively simple rules. Here I attempt to use this chaotic behavior to make procedural music based on the size of "groups" formed by the boids as time goes on.

This was my first attempt at using allolib so it is quite messy.

Iteration 1 Video here: https://youtu.be/h7SJa4J97Pc

Iteration 2 video here: https://youtu.be/6n1AKxUpc6w

Source code is in the folder named "[boids](https://github.com/ericpretzel/allolib_playground/tree/master/boids)".

## Physical modeling of the Cello

Playable cello! I show off vibrato with frequency modulation and also crude physical modeling of a cello's bowed string (work in progress (I dont think I will ever finish))

Brief breakdown of the sound setup for a cello string:
- The signal for each string is a saw-tooth oscillator with the frequency set at its base level (i.e. A2 will be at 440 Hz).
- Add slight reverb to make it sound more resonant and realistic.
- Add low-frequency (5 Hz) vibrato that modulates the signal's frequency in order to mimic a musician's vibrato.
- The bow dictates the ADSR envelope of the sound: pushing the bow down (by clicking the mouse) or changing the direction of the bow will start the attack on the string and raising the bow (letting go of the mouse), stopping movement, or leaving the string will trigger the release.
- The faster the velocity of the bow, the louder the sound.
- Add a low-pass and a high-pass filter that I pretty much just played around with until everything sounded okay-ish. These affected the brightness and harshness of the sound.
- Pushing keys on the keyboard would also modulate the frequency in half steps above the base frequency of the string. For example, the A-string would have the keys `12345678` to represent A#, B, C, C#, D...; The D-string used `qwertyui` for D#, E, F, F#, G, G#... etc. We do this by multiplying the base frequency by $2^{-i/12}$ where i is the "index" of the key (no keys being pressed would represent an index of zero).
- Since it is a 2D environment, the strings needed to be set up in this staggered manner so that it is possible for me to play individual strings, double-stops, and chords while not playing physically impossible things such as playing all four strings at once or double-stopping the A and C string. This introduced even more levels of difficulty while playing! Maybe these other placements could lead to cool possibilities though.

Demo 1: https://youtu.be/pSX_qqyAOzY (Only has the A string and sounds like a bee.)

Demo 2: https://youtu.be/BhyFifdUczQ (Has all four strings and sounds like it's an underwater brass instrument.)

Demo 3: https://youtu.be/U3ju84UVjfY (sounds slightly less underwater.)

Source code is in the folder named "[cello](https://github.com/ericpretzel/allolib_playground/tree/master/cello)".
