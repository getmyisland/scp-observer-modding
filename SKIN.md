# Custom Skins

You can create Custom Skins for the following characters:
- SCP-035
- SCP-049
- SCP-079
- SCP-096
- SCP-106
- SCP-173
- SCP-939
- SCP-3199

## SCP-079

Skin Scriptable Object field reference:
(**REQUIRED**) `Title` - Title of your mod as shown in SCP: Observer and the Steam Workshop.
(**REQUIRED**) `Character` - Character your skin replaces. `SCP_079` should be selected.
(**REQUIRED**) `SCP_079_Images` - Textures that will replace SCP-079's face when taking over a monitor.
(**OPTIONAL**) `Takeover Start Sounds` - Sounds SCP-079 will emit when taking over a monitor. If null or empty the default ones will be used.
(**OPTIONAL**) `Takeover Stop Sounds` - Sounds SCP-079 will emit after the playing interacts with him and his face disappears. If null or empty the default ones will be used.

> [!TIP]
> Images/Textures should have a resolution of `1280x720` pixel or an aspect ratio of `4:3`. Supported file types are `.png` and `.jpg`.

1. Right-Click on the `Assets/Modding/Skin` folder and click `Create` -> `SCP: Observer` -> `Skin`.

2. In the newly created Skin Scriptable Object set your character to `SCP_079`.

3. Drag and drop your assets (images, audio files) into the `Assets/Modding/Skin` folder.

4. Drag and drop the imported assets from the `Assets/Modding/Skin` folder into their respective variables of your Skin Scriptable Object.

5. In the Unity menu bar, click on SCP: Observer -> Export -> Skin.

6. If your setup is correct you can now find your mod inside `Assets/Modding/Export`.

## Other SCPs

Skin Scriptable Object field reference:
(**REQUIRED**) `Title` - Title of your mod as shown in SCP: Observer and the Steam Workshop.
(**REQUIRED**) `Character` - Character your skin replaces.
(**REQUIRED**) `Skin Prefab` - Prefab of your Skin.
(**OPTIONAL**) `Speed` - Maximum movement speed when following a path. If value is 0 or lower the default value will be used. Ignored by SCP-173.
(**OPTIONAL**) `Accelerration` - The maximum acceleration of a character as it follows a path, given in units / sec^2. If value is 0 or lower the default value will be used. Ignored by SCP-173.
(**OPTIONAL**) `Move Sound Chance` - Probability that a sound will be played when the character moves. If smaller than 1 the default chance will be used else sound will play 1 in n times.
(**OPTIONAL**) `Move Sounds` - Sounds the character will emit when starting to move. If null or empty the default ones will be used.
(**OPTIONAL**) `Rage Sounds` - Sounds the character will emit when starting to rage (e.g. hit by a Tesla Gate). If null or empty the default ones will be used.
(**OPTIONAL**) `Spotted Sound Chance` - Probability that a sound will be played when the character is spotted in the cameras. If smaller than 1 the default chance will be used else sound will play 1 in n times.
(**OPTIONAL**) `Spotted Sounds` - Sounds the character will emit when spotted in the cameras. If null or empty the default ones will be used.
(**OPTIONAL**) `Stinger Sound` - Sound which plays whenever an SCP is seen in the Security Room (e.g. Jumpscare Sound). If no sound is given the default sound will be used.
(**OPTIONAL**) `Security Room Chase Music` - Music which fades in when an SCP is seen in the Security Room. If no music are given the default music will be used.
(**OPTIONAL**) `Kill Sounds` - Sounds which play after the player was killed (e.g. Neck Snap sound). If no sounds are given the default sounds will be used.

1. Right-Click on the `Assets/Modding/Skin` folder and click `Create` -> `SCP: Observer` -> `Skin`.

2. In the newly created Skin Scriptable Object select your character.

3. Drag and drop your assets (model, textures, audio files) into the `Assets/Modding/Skin` folder. 

4. If needed configure your skin by creating materials and applying textures. [Unity Tutorial](https://docs.unity3d.com/2019.3/Documentation/Manual/Materials.html)

5. Open the `SkinCreator` Scene which is located inside the `Assets/Modding/Resources/Skin` folder.

6. Right-Click in the Scene Hierarchy View and press `Create Empty`. Name it whatever suits you for example `Skin`.

7. Drag and drop your skin from the Project View into the Scene Hierarchy View as a child of the newly created GameObject.

![Skin GameObject](https://i.imgur.com/4HnoBg0.png)

8. Size your skin accordingly so it is standing on the ground and about the same size as the SCP you want to replace. 

> [!TIP]
> Too see the actual size of other SCPs click on the small arrow next to the `References` GameObject and enable the GameObject of the SCP you want to replace. Now resize your model so it is roughly the same size.

9. Create a Prefab of your GameObject by drag and dropping it from the Scene Hierarchy View into the `Assets/Modding/Skin` folder in the Project View.

### Animations

If your SCP has animations you can see a template `AnimationController` for them located inside the `Assets/Modding/Resources/Skin/References` folder.

1. Copy the `AnimationController` for your SCP into the `Assets/Modding/Skin` folder.

> [!IMPORTANT]  
> Animations like Idle, Walk, Run need to enable loop in order to work as Unity does this not automatically. ([See the checkbox at image C.](https://docs.unity3d.com/Manual/class-AnimationClip.html))

##### SCP-173

You can skip this section as SCP-173 doesn't have animations in the game.

##### SCP-106

SCP-106 requires a rise animation where he rises from the ground. If a skin doesn't have this, it would just stand there for a while until the game says the animation is finished. The process is still the same as with other SCPs so follow the steps below.

##### Other SCPs

Open the `AnimationController` you copied by double clicking it and you will see all the states. Select each state and choose a fitting motion (animation) from your model. If you need animations you can go on [Mixamo](https://www.mixamo.com/#/) and generate some.

![Animation Controller](https://i.imgur.com/G7uo9jS.png)

After everything is done make sure to attach the `Animator` component to your `Skin` GameObject and select your `AnimationController` from the `Assets/Skin/Mod` folder.

![Animator Component](https://i.imgur.com/zEoh42O.png)

TODO Custom Sounds

### Building the AssetBundle

> [!IMPORTANT]  
> At this point the `Assets/Skin/Mod` folder should contain a `Skin` Prefab **or** an `SCP_079` folder.

1. In the `Editor Toolbar` at the top of the window hover over the `SCP: Observer` menu and select `Build Skin`.

2. This will generate the `Assets/Skin/AssetBundles` folder. Right-Click on the generated `skin_mod` file and select `Show in Explorer`.

3. Copy the `skin_mod` file (without any file ending) into a place where you can find it again because it is needed for the next steps.

You can now return to the [README](/README.md) to see how you can use this mod in SCP: Observer and upload it to the Steam Workshop.