# Floaxial
A modification for Minecraft that adds block physics.

# Overview

  - Make any block a falling type (stone, dirt, water).
  
  - Blocks move smoothly like regular sand but can also fall down slopes and form piles.
  
  - Built to tolerate slow multiplayer connections.
  
  - Update rates are configurable so large worlds can be handled. For example the client can display
  a maximum of N moves at a time.  The server can send N packets per second etc..
  
  - Uses plain rendering isntead of entities or block states.  That avoids some of the tracking done by the regular game client.
  
# Roadmap

  - 2022 Aug: 

    - Physics code complete using motion equations.

    - Tested 1,000 block falling 16 distance each.  No noticable tick latency and client displayed smoothly.
   
    - Network and data packing complete (32 bit per move on network).
    
    - Custom block render complete.
  
  - 2022 Sep:

    - Add chaining of multple moves to prevent jerkiness on client.  Server effectively opens a data stream to client and updates with the new block locations as it falls down a mountain.
    
    - Allow configurable blocks limited to 16 types.
    
    - Add archiving.  Stationary blocks are removed from list and no longer processed, until the terrain changes.

    - Add pyramid physics: slide down to hole that is 1 block away.
    
  - 2022 Oct:

    - Early alpha release.  Missing collisions and other important gameplay elements.
    
    - Basic water levelling as background task.  It requires storage for pathing towards holes so can be tricky for performance.

    - Basic collision against player or other falling blocks.  
    
  - 2022 Nov:
  
    - Tune code using simulated poor network.
        
    - Add simplified rule processor for cellular automata.  That allows many useful features such as plant growth, compost, mineral formation.  It finds a pattern of blocks and randomly replaces with a programmed pattern.
   
  - 2022 Dec:
  
    - Add skyblock and beachside mode.  Player starts on a sand pyramid with a tree and they need to build up soil to form a better island.  Lava and ores grow inside the island as it forms.

    - Render needs optimization. Materials need to be grouped and possibly rendered using instancing. 
    
    - Lighting also needs to be investigated because it's a heavy calculation to do per block.  It's currently being rendered without proper level shading.
