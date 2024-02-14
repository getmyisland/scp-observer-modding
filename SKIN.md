# Custom Skins

## Getting Started

You can create Custom Skins for the following characters
- SCP-035
- SCP-049
- SCP-079
- SCP-096
- SCP-106
- SCP-173
- SCP-939
- SCP-3199

1. Download [Unity](https://unity.com/de/download).

2. Open Unity Hub and create a new URP project.

3. Open the project and import the `SKIN.unitypackage` file by dragging it into the `Project` window. Make sure to import everything from this package.

## SCP-079

1. Create a folder inside `Assets/Skin/Mod` called `SCP_079`.

2. Drag and drop at least 1 image into the folder.

> [!TIP]
> Images should have a resolution of `1280x720` pixel or an aspect ratio of `4:3`. Supported file types are `.png` and `.jpg`.

TODO Custom Sounds Setup

Proceed with `Building the AssetBundle` further down.

## Other SCPs

> [!TIP]
> You can find examples in `Assets/Skin/Examples`.

1. Open the `SkinCreator` Scene which is located inside the `Assets/Skin` folder.

2. Drag and drop your skin model file as well as all required files (textures, etc.) into the `Assets/Skin/Mod` folder. If needed you can now configure your skin by creating materials and applying textures. [Unity Tutorial](https://docs.unity3d.com/2019.3/Documentation/Manual/Materials.html)

3. Right-Click in the Scene Hierarchy View and press `Create Empty`.

4. Rename the newly created GameObject to `Skin`.

5. Drag and drop your skin from the Project View into the Scene Hierarchy View as a child of the newly created `Skin` GameObject.

![Skin GameObject](https://i.imgur.com/4HnoBg0.png)

6. Size your skin accordingly so it is standing on the ground and about the same size as the SCP you want to replace. 

> [!TIP]
> Too see the actual size of other SCPs click on the small arrow next to the `References` GameObject and enable the GameObject of the SCP you want to replace. Now resize your model so it is roughly the same size.

Create a Prefab of your `Skin` GameObject by drag and dropping it from the Scene Hierarchy View into the `Assets/Skin/Mod` folder in the Project View.

> [!CAUTION]
> The Prefab must be named `Skin`. After making any changes to the GameObject you have to also apply them to the Prefab.

### Animations

If your SCP has animations you can see a template `AnimationController` for them located inside the `Assets/Skin/References` folder. Copy the `AnimationController` for your SCP into the `Assets/Skin/Mod` folder and proceed.

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