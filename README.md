# Tinyverses
<br/><br/>
This project focuses on the daily life of NPCs in a video game world.
Every character is simulated with a profession and a daily schedule, all arranged in Unrel Engine Blueprint logic.
<br/><br/>

https://github.com/user-attachments/assets/35590af0-98cc-431c-add3-beac056da378
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
