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

1. Right-Click on the `Assets/Modding/Skin` folder and click `Create` -> `SCP: Observer` -> `Skin`.

2. In the newly created Skin Scriptable Object set the `Title` and `Character` variables accordingly.

3. Drag and drop your assets (model, textures, audio files) into the `Assets/Modding/Skin` folder.<br/>
	3.1. If you have models configure them by creating materials and applying textures. ([Unity Tutorial](https://docs.unity3d.com/2019.3/Documentation/Manual/Materials.html))

> [!TIP]
> Hover over variables in the Skin Scriptable Object for more information about what the variable does. Most variables are optional and the default values will be used if the variable is empty.

## SCP-079

> [!TIP]
> SCP-079 textures should have a resolution of `1280x720` pixel or an aspect ratio of `4:3`. Supported file types are `.png` and `.jpg`.

1. Populate the `SCP_079_Images` array by drag and dropping textures from the `Assets/Modding/Skin` folder into the list.

2. (Optional) Drag and drop audio files into the `Takeover Start Sounds` and `Takeover Stop Sounds` arrays.

## Other Characters

1. Open the `SkinCreator` Scene which is located inside the `Assets/Modding/Resources/Skin` folder.

2. Right-Click in the Scene Hierarchy View and press `Create Empty`. Name the empty GameObject whatever suits you for example `Skin`.

3. Drag and drop your skin from the Project View into the Scene Hierarchy View as a child of the newly created GameObject.

![Skin GameObject](https://i.imgur.com/4HnoBg0.png)

4. Size your skin accordingly so it is standing on the ground and about the same size as the character you want to replace.<br/>
	4.1. Too see the actual size of other SCPs click on the small arrow next to the `References` GameObject and enable the GameObject of the character you want to replace. Now resize your model so it is roughly the same size.

5. Create a Prefab of your Skin GameObject by drag and dropping it from the Scene Hierarchy View into the `Assets/Modding/Skin` folder in the Project View.

6. Drag and drop the created Prefab into the `Skin Prefab` variable of the Skin Scriptable Object.

7. (Optional) Configure animations or drag and drop audio files into the custom sound variables.

### Animations

If your character has animations you can see a template `AnimationController` for them located inside the `Assets/Modding/Resources/Skin/References` folder.

1. Copy the `AnimationController` for your character into the `Assets/Modding/Skin` folder.

> [!IMPORTANT]  
> Animations like Idle, Walk, Run need to enable loop in order to work as Unity does this not automatically. ([See the checkbox at image C.](https://docs.unity3d.com/Manual/class-AnimationClip.html))

**SCP-173**

You can skip this section as SCP-173 doesn't have animations in the game.

**Other Characters**

1. Open the `AnimationController` you copied by double clicking it and you will see all the states.

2. Select each state and choose a fitting motion (animation) from your model. If you need animations you can go on [Mixamo](https://www.mixamo.com/#/) and generate some.

![Animation Controller](https://i.imgur.com/G7uo9jS.png)

3. Attach the `Animator` component to your **model** GameObject (not the Skin GameObject itself or animations won't work) and select your `AnimationController` from the `Assets/Modding/Skin` folder.

![Animator Component](https://i.imgur.com/zEoh42O.png)

## Building the AssetBundle

> [!IMPORTANT]  
> At this point the `Assets/Modding/Skin` folder should contain a Skin Scriptable Object with all required values populated.

1. In the Unity menu bar, click on `SCP: Observer` -> `Export` -> `Skin`.

2. If you did everyting correctly you can now find your mod inside `Assets/Modding/Export`.