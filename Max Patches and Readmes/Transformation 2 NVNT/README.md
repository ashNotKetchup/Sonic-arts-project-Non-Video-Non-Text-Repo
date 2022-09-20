Don't consolidate the project in Max! Because it's not explicitly in the patch, Max thinks our HTML isn't in use and bins it. We don't want that, eh?

Check all prerequisites are installed before using. Make sure the audio is on and that the correct audio source is selected before attempting to use this patch. If using windows/linux, or if having any issues with pitch detection, switch out vb.pitch for the original fiddle plugin. This is inside the 'sysinput' subpatcher. The cooked output of this plugin can also be swapped out for a midi keyboard, presuming the mtof function has been utilised.

Initial architecture (Max --> remote webSocket server --> local renderers)

If you're having issues with the live server or the webSockets not running, try the following:

`npm install kill-port,` `live-server``

To kill an existing process on a specific port, use: `npx kill-port [port]`

Everything can be run and stopped at once from the standard page. Additional controls, accessible via the 'nerd' and 'debug' sub-patches, should allow you to do pretty much anything else you might need.

However, to manually start the site (for development etc)

Start the webSocket server:
- `cd remote`
- `node server.js`

Start the renderer:

    Navigate to project root
    - `cd ~ `

    Start local web server
    - `live-sever`

Inspect the renderer webpage to get an example of the structure of objects it expects to receive. 

The main rendering engine is built in D3, contained in a file called graphing.js. Change that file to change the representation of the objects.

Now, using webSockets in Node for Max, start a max and remote webSocket server to communicate to the renderer. This is a bidirectional relationship, and anything sent across the webSocket connection gets sent to all entities connected to it.

TODO:
Filtering interface. If you so wish, you might want to build an interface for conditional filtering of nodes and links. Contributions are welcome at https://github.com/ashNotKetchup/dynamic-music-rendering
