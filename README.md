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
1. upon Play, the NPC gathers location info about their home and its interior
2. the NPC also gathers the locations of their workplace and relevant village spots, like the tavern or the marketplace
3. every NPC starts by going to bed, checking time regularly and decides their next action
4. all actions are managed in Custom Events, eg going to bed, going to work, switching on/off lights
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
