# Collision

Emitter based collision polling - raw 

Entities are responsible for detecting collision when they move. An entity standing still doesn't need to check.

A worker process / subprocess that handles collision polling - watches for emitted events by entities, does calculations and responds to those entities.
Coupled with the game render polling?
https://nodejs.org/api/worker_threads.html

https://stackoverflow.com/questions/19764018/controlling-fps-with-requestanimationframe

https://www.youtube.com/watch?v=W0e9Z5pmt-I

https://stackoverflow.com/questions/20482667/fps-in-chrome-capped-at-60fps

http://mbostock.github.io/d3/talk/20111018/collision.html




Collider module
Watches for movement events asyncronously
maintains a position hash
Event emitter 'move', 'damage', 'effect'

###### Emitter Types
Everything should work off a single `move` event type - the callback / result of that move is defined by the entity
* A character who moves fires an event when it enters a new set of coordinates (course collision)
* Any entity has a callback to handle collision
    * For the map it is an override to prevent any entities from moving past it
    * For a mob it may be to damage player objects and stop movement
    * For a bullet it may be to damage a specific entity but without any movement stop
