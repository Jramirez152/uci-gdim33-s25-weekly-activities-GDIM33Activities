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


## W7

### Activity 1

1. The Vertex Color node gets its data from the mesh itself. Each vertex on the Shiba mesh already stores data like position, normal, tangent, UV, and color, so the shader is just reading the color data saved on each vertex.
2. The colors blend at the edges because the shader interpolates vertex color across the polygons. Since each corner of a polygon can have different color values, Unity smooths those values across the face instead of making a perfectly sharp edge.
3. Vertex color is less detailed because it only stores color at the vertices, while a texture can store way more color information across the surface using pixels. Vertex color seems useful for simpler color effects, stylized models, debugging, masks, or low-poly art where you do not need super detailed texture work.
4. Based on the Shibas colors, yes, something looks off with the meshs vertex normals. The debug shader shows strange color differences where the surface normals do not seem consistent, which suggests some normals might be flipped or incorrect.
5. Another useful piece of data to test with a debug shader would be UV coordinates. Visualizing UVs with color could help show whether a texture will map correctly onto the mesh or if the UVs are stretched, flipped, or broken.
6. The lighting error happens because the light direction vector and the Shibas surface normals are pointing in opposite directions. The dot product gives negative values for surfaces that should be lit, making the front look dark and the back look bright.
7. Additive blending makes sense for the fire because fire is a glowing effect. Instead of blocking what is behind it like a solid object, additive blending adds brightness and helps the lighter parts look more intense while the darker parts fade away.


## W8 

### Activity 1 

# What's New
I tweaked a lot of the values for the abilities from milestone 2 but I haven't added any actual new content just yet. For milestone 3 I am going to do a big cosmetic overhaul to finally get out of the greybox phase. 
# Itch Link
https://boozie-uzi.itch.io/milestone-2-3-playtest 
# Goals
1. I really wanted feedback on the enemy types since that wasn't something I was actually planning to have included. 
2. I wanted some ideas as well as to what else I could try to add. 
3. I wanted to see if the Purple guy's push was even noticeable to the average player or if their habits would even allow the enemy to attack them with the push.

# Playtesting Notes
The repetitive clicking that people do on the game makes me feel like I should probably add some kind of like cooldown to the normal attack more than what it has already, something more substantial. But at the same time I think the movement and the rest of the pace of the game is set to a specific level that if the player can't actually attack repeatedly then they are just stuck there with their hands in their pockets until the cooldown is gone and I feel like a lot of the fun leaves with that. 

### Activity 2C
1. The pass associated with the post-processing effect is FullScreen Pass Renderer Feature. I could tell because it appears under the custom URP_PostEffect renderer in the Frame Debugger, and stepping through that pass shows the fullscreen red overlay effect being applied to the screen.
2. When the Lerp value is set to 0, the screen shows only the original game image with no red effect applied. When the value is set to 1, the screen shows the full red cobblestone effect. When the value is set to 0.5, the screen becomes a blend of both, so the original game and the red overlay are both partially visible at the same time.
3. Lerp blends between two inputs. In this case, input A is the original screen, and input B is the red multiplied effect. So 0 shows A, 1 shows B, and 0.5 mixes both evenly.
4. I think because plain sin(time) gives values from -1 to 1, but Lerp expects 0 to 1. Adding 1 shifts it to 0 to 2, then dividing by 2 turns it into 0 to 1, giving a smooth pulse without the weird bright stage.