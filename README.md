# Tinyverses
<br/><br/>
This project focuses on the daily life of NPCs in a video game world.
Every character is simulated with a profession and a daily schedule, all arranged in Unrel Engine Blueprint logic.
<br/><br/>

https://github.com/user-attachments/assets/dc50156a-21c6-48c7-aba8-ec225f128d69

<br/><br/>

## NPC Behaviour
<br/><br/>
In order to keep every behaviour flexible and extendible, all NPC logic is managed inside their respective blueprints without the limitations and rigidity of behaviour trees.
The flow goes as follows:
1. upon Play, the NPC house is spawned with location markers for eg the bed, the kitchen, the light switch
2. the NPC class is spawned right in fron of the house
3. the NPC is assigned to their nearest house
4. the NPC gathers location info about their home and its interior
5. the NPC also gathers the locations of their workplace and relevant village spots, like the tavern or the marketplace
6. every NPC starts by going to bed, checking time regularly and decides their next action
7. all actions are managed in Custom Events, eg going to bed, going to work, switching on/off lights
<br/><br/>
Example below of the 'Worker' blueprint class (the green guys):
<br/><br/>
<img width="800" height="654" alt="image" src="https://github.com/user-attachments/assets/930baf0f-86d3-4f9f-9721-c4fcbcbd7e1c" />
<br/><br/>
1. an unavoidable but low-impact Tick node (the dreaded Update function in Unity), managing the billboard orientation of the character's debug board<br/>
2. BeginPlay: bundling the Cutom Events below, processing them one by one<br/>
3. getting house info<br/>
4. getting area location info<br/>
5. getting time-of-day info, naturally this one is called regularly<br/>
6. work routine<br/>
7. end-of-day routine, should I go to bed or to the bar instead? and if so, which table should i sit at?<br/>
8. going to bed and checking for wake-up time<br/>
9. a not-yet-implented check while walking for near NPCs, leaving room for social interaction, happy to show that one off later
<br/><br/>

## General Usage

1. the simulation speed can be set by selecting the clock and set up the day length in seconds
2. The 'Worker' and 'Farmer' houses technically have no number limits, so a village with 20+ of these house types will work (but of course from a certain number on they will start blocking each other everywhere)
3. in order to avoid funny logic breaks avoid placing more than one farm and one townhall
<br/><br/>

## Current Flaws

1. the NPC behaviour is still location-based, which on the one hand makes task assignment easier but (rarely) leads to some characters being inconclusive and 'changing their mind' mid-way
2. the general simulation speed can technically be configured, see above, but for some NPCs it's necessary to re-adjust some waiting times inside the Delay nodes (or they might get up in the middle of the night because their next action is already triggered)
<br/><br/>

## Road Map

1. the NPCs have already variables for Energy and Mood, these will feed into their schedules and task decisions
2. NPC-to-NPC interaction, controlling with whom they visit the tavern or having chats at the marketplace, and feeding into their mood
3. NPCs will be able to pick up crop from the farm and distribute it across the marketplac and the tavern

