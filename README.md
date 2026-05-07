# GDIM 33 In-Class Activities
## W1
### Activity 1

1. The main patterns that are emerging for me is a more of a beat em up, I think. I think I will go with 3D. I'm very drawn to the 'low polygon ps1 game' aesthetic, particularly with highly saturated colors that you find in games like ridge racer, or tekken 2. I find games where dodging and parrying is the forefront of combat, the arkham games do a great job at mixing enemy types that can only be dealt with using specific mechanics. 
2. My tablemate differentiated a little bit in visual aesthetic, they favored a more cluttered aesthetic, very cozy and cute, similar to studio ghibli still frames and isometric style stardew valley.
3. Elijah had shared that they favored puzzle games as well as single-player story driven games. I had made the connection to Outer Wilds and it was actually right! 

https://miro.com/app/board/uXjVGoFRiU0=/?share_link_id=600898419265 

### Activity 2

https://docs.google.com/drawings/d/1DXblBBuUiLAm_IhuKVVHFLm77iD_1kcDLqdRKewiVvY/edit?usp=sharing 



## W2
Week 2 has no dev log notes needed. 

## W3 

### Activity 1 
Edited breakdown based off feedback received.
https://docs.google.com/drawings/d/1DXblBBuUiLAm_IhuKVVHFLm77iD_1kcDLqdRKewiVvY/edit?usp=sharing


### Activity 2 
1. By having it saved as a scene variable its more centralized instead of me needing to add it on each graph. 
Also if I changed the name or something, I would only need to update it once, instead of it shattering every other place I might have included it. 
2. The debug log actually did help on my transition node because I didn't actually the scene variable set up properly. 
3. Yes, locking the cursor is actually super important to my vertical slice because the mouse is going to control which direction you're facing, so keeping it on screen is crucial to quality of life for gameplay.
4. Yes, I think game states are relevant to my slice because I would like to have a sort of menu before the game starts, something basic- quite literally just a start button. And post game should be another state that shows scores achieved before dying or time running out. 


## W4

### Activity 1

What is playable in my playtest currently? 

I have the extremely basic gameplay loop minus the hazards in the game. 
I really want to see if the control scheme is something that is too jarring for players to become acclimated to quickly. 
Also I wanna see if I need to adjust the cooldowns for some the rate of attacks and being attacked. 
I think I need more people to playtest because the results between people are so wide, some didn't mind the cooldowns while others did comment on it, and some immediately took to using the mouse while others didn't realize the mouse was necessary to control the direction of the player.

### Activity 2 

1. Yeah I think a writer could add more dialogue without touching code. The system is built around ScriptableObjects, so all the dialogue lines and reply options are basically data, not logic. As long as the programmer already set up how dialogue flows and gets displayed, the writer just has to create new DialogueNode assets, type in lines, and link them together. No scripting needed, just plugging things in through the editor.

2. There isnt really a hard coded limit to how many dialogue nodes they can make. They could keep adding as many as they want. The only real limits are practical ones, like how messy it gets to manage, performance if it gets ridiculously large, or UI limits (like how many options can fit on screen at once). But system-wise, it can scale pretty far, not that I would wanna do all that. 

3. Regenerate Nodes basically refreshes Unitys visual scripting system so it recognizes your scripts and turns them into usable nodes. When you add new classes or change code, Unity doesnt automatically expose that stuff to visual scripting, so this forces it to update and include everything properly. Without doing this, your custom stuff might just not show up at all.

## W5

### Activity 1 

So for milestone 1 I have already added some Navmesh stuff- enough for it to stand on its own two feet and work normally. But what I have is a very basic version of it. So now I will take this opportunity to push it further. 
1. Step one being having added the navagent component to my enemy prefab in order for them to be able to navigate independently along walkwable surfaces
2. The second step would be to bake the Navmesh onto the walkable surface itself- in this case it would be the arena floor I have set up. 
3. The third step will be to update the arena itself to accomodate new flooring or add new hazards. 
3.1 I will create a new gameobject and add a collider with a trigger on it that kills whatever touches it.
3.2 I will ensure the game object is not walkable on the layer list. 
3.3 Now I will have to rebake the arena so that the enemies prefabs path around any of the new hazards scattered around the arena. 

### Activity 2 

I designed some little floor spike traps and placed them along the floor and along some of the walls- while adding new walls within the arena to create more surface areas for traps to be placed. I added a collider so anything just dies when coming in contact with it, adding them to the walls will become a much bigger threat when I add pushing later on. The spike traps on the floor are not walkable and the Navmesh now has little holes to fit the traps along the floor and is not affected by the walls as I separated the two types of traps between floor and wall traps. 

## W6

### Activity 1

Goal for playtesting:
Is the rate of which NPCs push too overwhelming? Is the player rate to push too slow? Do players prioritize attacking normally or is pushing now the preferred method of combat since you can just push enemies into traps?

(no itch link for playtesting, done in unity...I know I know..)

So I tried to mitigate the rate of which NPCs push by only allowing them to push when the player proximity to a trap is under a certain threshold, but in a wave format the player gets absolutely hounded by whatever little enemies are surrounding them if they just get near a trap. Dashing helps but it definitely doesn't feel like neat solution to a messy problem, more like a workaround. I need to figure out how to make it less obnoxious as the player. Only specific types of enemies being able to push might help. 

Ironically the overwhelming pushing from the enemy NPCs as acted as an incentive to stay on the very edge of the hitbox with enemies so the PLAYER spamming push wasn't as common as I thought it was gonna be. 

### Activity 2

1. Multiply makes the color darker because it multiplies each actual RGB value together. Since RGB channels are stored between 0 and 1, multiplying two values usually makes the result smaller. For example, if one red value is 0.8 and the other is 0.5, the result is 0.4. Because the final RGB values are lower, the color appears darker and often less saturated.

2. The resulting alpha value would usually be more translucent because multiplying two alpha values between 0 and 1 creates a smaller number. Since lower alpha means more transparency, the final result would generally be more see-through than either original value.

3. The shader gets the UV values from the mesh itself. The model already has UV coordinates stored with its vertices, which tell the shader how a 2D texture should wrap onto the 3D object. Unitys UV0 node is just reading that first UV channel from the mesh.

4. It's cool but math and I arent on speaking terms at this current moment. 