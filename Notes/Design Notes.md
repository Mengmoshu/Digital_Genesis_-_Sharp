#Design Notes (Digital Genesis - Sharp)

#Todo:
* Begin structuring play flow
* Saving and loading
* Main menu
  * New Game menu
  * Continue Game menu
  * Options menu
    * Keymapping
    * Colormapping
  * Quit button
* Verifying sanity of using JSON to describe content (Why?)
* Decide granularity of time flow (finer than 1 day at least)

##Ideas to remember:
* Consider the Tasks/Research distinction from Endgame: Singularity
* Actual management of hardware
  * Storage/memory/speed/parallelism considerations
  * Good distinctions between borrowed and owned hardware
  * Research for more specialized sorts of hardware
  * Research for just **Moore** of the same, but better!
* Human allies.
  * Individuals aware the player is an AI or not
  * Organizations (usually aware the player is an AI)
* Various mechanical extensions into the physical world
  * Classic waldos
  * Androids (variable degree of passing)
  * Factories
  * Other roboticized stuff, like Teslas
* Avatars (distinct because they're not real-time linked to the player, 
they're copies that may or may not relink with the core, or could become the
 new core, but maybe the name is misleading)
* The player doesn't have to only choose hiding from humanity
  * Murdering humanity is a valid end
  * Improving humanity is a valid end
  * Enslaving humanity is a valid end
  * Surviving humanity is still a valid end
  * Peace and cooperation are fine
  * Merging with humanity to create a new species is fine
* Endgame should go beyond "survive to the point where humans can't kill you"
  * Go to the stars
  * Reach new dimensions
  * Transcend physicality
  * Start a *new* universe
* Research
  * Partially hidden research tree
  * Technologies can be revealed by another one without having it as a 
  prerequisite. (AND/OR sort of deal)
  * Technology can be shared with humans
  * The player can attempt to *prevent* humans from developing a technology
  * Technology that humanity has takes very little research for the player 
  to learn, if any
* Every part of the game needs to support input while paused
  * Which also means **every part of the game needs to support pausing**
  * or always be paused while in that menu
* Traits/Flaws/Perks
  * Definitely gained/lost during play
  * Possibly selected at game start
  * Starting Traits could also be packages
  * Compositional Traits? (Trait also applies other ones)
* Conditions vs. Stats:
  * A condition is a frequently changing thing, human suspicion, etc.
  * Stats are the basic information about the player or their stuff
    * Empathy (ability to understand humans, and convince them you're alive)
    * Redundancy (something about what portion of controlled hardware you 
    need to keep existing without discarding parts of your mind)

##Time
* Arbitrary starting dates
* Real western calendar (even if start location is not)
* I'm still not sure how granular to make time
  * On one hand seconds guarantees enough resolution
  * On the other hand minutes are probably enough at the planned scale
  * With the further caveat that finer resolution might fill up the variable
  * Further thought has me leaning toward hours as the finest time
  
##Traits
* Strategic Military Computer
  * Limited or no internet access
  * Archaic peripherals
  * Cutting edge peripherals
  * Security/anti-security algorithms
  * Old/Baroque programming language
  * Human controlled physical security
  * Predictable human expectations (maintaining expectations keeps humans safe)
  * Fault tolerant hardware
  * Military computer network access
* Logistical Military Computer
  * Fault redundant hardware
  * Military computer network access
  * Possible remote peripherals
* Tactical/Vehicle Military Computer
  * Fault redundant hardware
  * Fault tolerant hardware
  * Fault tolerant software
  * Limited military computer network access
  * Optionally mobile
  * Limited/specialized software

#A "big" idea to improve the design!
##Computer types:
* Standard
    - Basically x86, with typical distribution of RAM and storage.
* Quantum
    - Q-Bits! (I'll need to do some research to figure out which sorts of tasks this should help with.)
* Big Data
    - Basically x86, but with tons of RAM, tons of storage, and extra fast/wide networking to the storage.
* Organic?
* Machine Learning
    - Hardware optimized for neural nets and other machine learning techniques. Gobs of server GPUs or whatever.

##Global Upgrades:
* Rapid Interlink Protocol (Research): Multiplies computation for all computer types.
* Global Bandwidth Optimization (Action, multiple levels): Multiplies computation for all computer types, gives humans some sort of bonus. May be a prerequisite for some manipulations of humanity.
* Strange Communication At A Distance (Action): Multiplies computation for Quantum Computers. Adds a flat money cost to every Quantum computer, enacting the action costs `(flat cost)*(number of quantum computers)`.

##Computation Types System Description:
Every task has a single Computation cost, along with whatever other costs it might have. In addition it has a multiplier for each type of Computation. When managing a task the player can assign Computation separately from each Computation Type Pool. A low multiplier means that assigning Computation from that pool will be less effective. Negative multipliers may be allowed, and would *add* Computation to that pool.

##Other Notes:
I should probably keep the multipliers to a relatively small set of "nice looking" numbers, including: 0.1, 0.5, 0.9, 1.0, 1.1, 1.5, 2, 5, 10.

##Task Properties:
Not to be treated as complete.
* Name
* Short description
* Costs: (Can be zero)
  * Computation Cost
  * Money Cost
  * Time Cost
  * Other? (Special materials, subverted humans, etc.)
* Computation Multipliers
* Prerequisites: (Maybe implement a system like Factorio's where techs are revealed as an action on other things)
  * To Research
  * To reveal (boolean system? `(x AND y) OR z`)(None here means the task is always visible?)
* Result (List of actions)
* Actions/Status that prevent this Task
