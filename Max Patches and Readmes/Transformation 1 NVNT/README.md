This patch takes a monophonic, pitched input and performs a rudimentary l-system algorithm on it. Its output is a displayed message, as well as a corresponding OSC message over the channel defined in the bottom right corner of the patch. 

Make sure the audio is on and that the correct audio source is selected before attempting to use this patch. Use the 'flush' button for any data which shouldn't be there.

If using windows/linux, or if having any issues with pitch detection, switch out vb.pitch for the original fiddle plugin. This is inside the 'sysinput' subpatcher. The cooked output of this plugin can also be swapped out for a midi keyboard, presuming the mtof function has been utilised.