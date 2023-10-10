# SCP: Observer Modding Guide

This repository serves as both a tutorial and a template for the SCP: Observer mod creation process.

## Custom Skins

You can create custom skins for the following characters
- SCP-035
- SCP-049
- SCP-079
- SCP-096
- SCP-106
- SCP-173
- SCP-939
- SCP-3199

The process stays mostly the same for every character except SCP-079.

### SCP-079

Creating a mod for SCP-079 doesn't involve downloading the template and using Unity.

All you need is a folder with at least 1 image. The image(s) should have a resolution of `1280x720` pixel or an aspect ratio of `4:3`. Supported file types are `.png` and `.jpg`.

The folder (mod file) can now be prepared to be used in SCP: Observer. See `%STEAM%/steamapps/common/SCP_Observer/Mods/INSTRUCTIONS.txt` for more details.

### Other SCPs

#### Using the template

If you are completely new to Unity and/or SCP: Observer modding in general, I highly recommend using the template. For simplicity, these instructions assume that you have installed the template.

##### Download from GitHub

To create a custom skin first download this repository. You can do so by either cloning it or downloading it as a `.zip` file. Either way you have to click on the green `<> Code` button.

##### Open in Unity

This template requires the Unity version `2021.3.5f1`. Other Unity versions have not been tested and may or may not work. The steps may differ depending on the version you use.

If you don't have Unity and Unity Hub installed you can download the required version [here](https://unity.com/releases/editor/archive).

Open Unity Hub and click `Open` -> `Add project from disk`. Now select the location where you downloaded the template and open the project in Unity.

![Unity Hub](https://i.imgur.com/hLnzxnM.png)

#### Creating an Asset Bundle

##### Import Skin

To create a custom skin, you need a 3D model in a format that Unity supports (e.g. fbx, obj, ...).

Open the `SkinCreator` Scene which should be located inside the `Skin` folder.

![Skin Creator Folder](https://i.imgur.com/1KVZoVx.png)

Drag and drop your skin as well as all required files into the `Skin` folder. If needed you can now configure your skin by creating materials and applying textures. [Tutorial](https://docs.unity3d.com/2019.3/Documentation/Manual/Materials.html)

In the Scene Hierarchy View you should have a gameobject called `Skin`. You need to drag and drop your skin from the project explorer into the Scene Hierarchy View as a child of the `Skin` gameobject.

![Skin GameObject](https://i.imgur.com/4HnoBg0.png)

Size your skin accordingly so it is standing on the ground and about the same size as the SCP you want to replace. 

Tip: Activate one of the reference SCP gameobjects, by clicking on the small arrow next to the `References` gameobject and enabling the gameobject of an SCP. Now use the SCP to size your skin so it is roughly the same size. Don't make it to big or too small than the original skin or else it will look and feel wrong in game.

##### Animations

If an SCP has animations you can see a template animation controller for them located inside the `References` folder. Copy the animation controller for your SCP into the `Skin` folder and proceed.

IMPORTANT: Animations like Idle, Walk, Run need to enable loop in order to work as Unity does this not automatically. ([See the checkbox at image C](https://docs.unity3d.com/Manual/class-AnimationClip.html))

###### SCP-173

You can skip this section as SCP-173 doesn't have animations in the game.

###### SCP-106

SCP-106 requires a rise animation where he rises from the ground. If a skin doesn't have this, it would just stand there for a while until the game says the animation is finished. The process is still the same as with other SCPs so follow the steps below.

###### Other SCPs

Other SCPs are pretty straight forward. Open the animation controller you copied by double clicking it and you will see all the states. Select each state and choose a fitting motion (animation) from your model. If you need animations you can go on [Mixamo](https://www.mixamo.com/#/) and generate some.

![Animation Controller](https://i.imgur.com/G7uo9jS.png)

After everything is done make sure to attach the `Animator` component to your `Skin` gameobject and select your animation controller.

![Animator Component](https://i.imgur.com/zEoh42O.png)

#### Building an Asset Bundle

Create a prefab of your Skin gameobject by drag and dropping it inside the `Skin` folder. The prefab **MUST** be named `Skin` or else it won't work.

In order for Unity to recognize your skins as Asset Bundles you have to select the `Skin` prefab in the project explorer. In the lower right corner you see a label called `AssetBundle` and a dropdown next to it. Click on the dropdown and select `New...` to create a new tag. Now select your created tag on all files your skin requires in order to work (model, textures, animation controller, ...).

![Asset Bundle](https://i.imgur.com/NQG8Y3w.png)

If **all** the required files have the correct AssetBundle tag you can select `Assets` -> `Build AssetBundles` at the top.

![Build Asset Bundles](https://i.imgur.com/gHprKNg.png)

This should create a folder in your project called `AssetBundles` where the generated asset bundles will be stored.

Right click on the AssetBundles folder and select `Show in Explorer` to open it in the Windows Explorer. Copy all files with your tag that **DON'T** have a `.meta` file ending.

Your asset bundle files (mod files) can now be prepared to be used in SCP: Observer. See `%STEAM%/steamapps/common/SCP_Observer/Mods/INSTRUCTIONS.txt` for more details.