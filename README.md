# SCP: Observer Modding Guide

This repository serves as both a tutorial and a template for the SCP: Observer mod creation process.

This tutorial will guide you through all the steps from creating a mod, to preparing and testing it, to uploading it.

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

The process stays the same for every character except SCP-079.

### SCP-079

Creating a mod for SCP-079 doesn't involve downloading the template and using Unity.

All you need is a folder with at least 1 image. The image(s) should have a resolution of `1280x720` pixel or an aspect ratio of `4:3`. Supported file types are `.png` and `.jpg`.

The folder with all the images inside will now be referred to as your mod file. You can now skip to `Preparing a mod`. 

### Other SCPs

#### Download template from GitHub

To create a custom skin first download this repository. You can do so by either cloning it or downloading it as a `.zip` file. Either way you have to click on the green `<> Code` button.

#### Open template in Unity

This template requires the Unity version `2021.3.5f1`. Other Unity versions have not been tested and may or may not work. The steps may differ depending on the version you use.

If you don't have Unity and Unity Hub installed you can download them [here](https://unity.com/releases/editor/archive).

Open Unity Hub and click `Open` -> `Add project from disk`. Now select the location where you downloaded the template and open the project in Unity.

![Unity Hub](https://i.imgur.com/hLnzxnM.png)

#### Creating an Asset Bundle

##### Import Skin

To create a custom skin, you need, well, a skin. In Unity open the `SkinCreator` Scene which should be located inside the `Skin` folder.

![Skin Creator Folder](https://i.imgur.com/1KVZoVx.png)

Drag and drop your skin and all required files into the `Skin` folder. If needed you can now configure your skin by creating materials and applying the textures.

In the Scene Hierarchy View you should have a gameobject called `Skin`. You need to drag and drop your skin from the project explorer into the Scene Hierarchy View as a child of the `Skin` gameobject.

![Skin GameObject](https://i.imgur.com/4HnoBg0.png)

Size your skin accordingly so it is standing on the ground. 

To help with this, you can activate one of the reference SCP gameobjects. Do this by clicking on the small arrow next to the `References` gameobject and activate the gameobject of an SCP. Use the SCP to size your skin so it is roughly the same size. Don't make it to big or too small than the original skin or else it will look and feel wrong in game.

##### Animations

If an SCP has animations you can see a template animation controller for them located inside the `References` folder. Copy the animation controller for your SCP into the `Skin` folder and follow the next steps.

###### SCP-173

You can skip this section as SCP-173 doesn't have animations in the game.

###### SCP-106

SCP-106 is a little bit tricky because he requires a rise animation where he rises from the ground. If a skin doesn't have this it would just stand there for a while until the game says the animation is finished.

###### Other SCPs

The other SCPs are pretty straight forward. Open the animation controller you copied by double clicking it and you will see all the states. Select each state and choose a fitting motion (animation) from your model. If you need animations you can go on [Mixamo](https://www.mixamo.com/#/) and generate some.

![Animation Controller](https://i.imgur.com/G7uo9jS.png)

After everything is done make sure to attach the `Animator` component to your `Skin` gameobject and select your animation controller.

![Animator Component](https://i.imgur.com/zEoh42O.png)

#### Building an Asset Bundle

Create a prefab of your Skin gameobject by drag and dropping it inside the `Skin` folder. The prefab **MUST** be named `Skin` or else it won't work.

In order for Unity to recognize your skins as Asset Bundles you have to select the `Skin` prefab in the project explorer. In the lower right corner you see a label called `AssetBundle` and a dropdown next to it. Click on the dropdown and select `New...` to create a new tag. Now select this tag on all files your skin requires in order to work (model, textures, ...).

![Asset Bundle](https://i.imgur.com/NQG8Y3w.png)

If **all** the required files have the correct AssetBundle tag you can select `Assets` -> `Build AssetBundles` at the top.

![Build Asset Bundles](https://i.imgur.com/gHprKNg.png)

This should create a folder in your project called `AssetBundles`. This is where the generated Asset Bundles will be stored. 

Right click on the AssetBundles folder and select `Show in Explorer` to open it in the Windows Explorer. Copy all files with your tag that **DON'T** have a `.meta` file ending. These files will now be referred to as your mod files in the next steps. You can now skip to `Preparing a mod`. 

# Preparing a mod

If you have your mod file(s) ready you can create a new folder anywhere on your disk and call it something like the name of your mod. Paste the mod file(s) into the folder.

Inside the folder create a file called `mod.json`.

This is a simple configuration file for your mod that allows both the Steam Workshop and SCP: Observer to find your mod.

The structure of the `mod.json` is as follows:
```
{
	"title": "SCP: Containment Breach SCP-049",
	"tag": "skin",
	"mod": "cb_scp_049",
	"scp": "049"
}
```

`title` is the name of your mod that will be shown inside the Steam Workshop and SCP: Observer.

`tag` is the mod tag. Currently there is only one so keep this how it is.

`mod` is the name of your mod file located inside the mod folder. For SCP-079 mods this would be the folder with all the images for all other SCPs this is the AssetBundle file without the `.manifest` at the end.

`scp` is the SCP your mod will replace. Supported values are `035`, `049`, `079`, `096`, `106`, `173`, `939` and `3199`.

You can copy everything and adjust the file to your needs.

# Testing a mod

It is recommended to test your mod before trying to upload it to the Steam Workshop to ensure it works correctly.

Doing so is very easy. Paste the entire mod folder into `C:\Users\YOU\AppData\LocalLow\GetMyIsland\SCP_ Observer\mods`. If the `mods` folder doesn't exist you can just create it.

Tip: Use the Windows + R key combination and type `%appdata%` to reach the `AppData` folder easily.

If you did everything correctly your mod should now show up inside SCP: Observer. If you don't see the mod double check your `mod.json` file.

# Uploading a mod

If your mod works perfectly fine locally and you want to share it with other people you can upload it to the Steam Workshop.

Find out where SCP: Observer is installed locally. You can do this by going into your Steam library and right clicking on SCP: Observer -> `Manage` -> `Browse local files`.

Inside the installation folder you should see `Tools` folder. This is where the tools to interact with the workshop will be located.

## scpo_uploader

Open a `Command Prompt` inside the `Tools` folder. Follow the steps below to either create or update an existing item.

Tip: Use the `usage` command to see how to use the program (`scpo_uploader.exe usage`).

Note: Some commands need an `icon`. The icon will be visible on the Steam Workshop. It should be in a square format and have a size of `512x512` pixel. Smaller and bigger sizes are ok as long as the file size is not too big. Supported formats are `PNG`, `JPG` and `GIF`.

### Creating a new workshop item

To create a new workshop item you can use the `create` command.

Note: Before your mod will be visible on the Steam Workshop you have to accept the Steam Workshop Terms of Service and you have to set the item visibility to public.

Example:<br>
`scpo_uploader.exe create --mod "path/to/mod/folder" --icon "path/to/icon"`

### Updating an existing workshop item 

To update an existing item you can use the `update` command.

Note: The `icon` argument is only required if you want to update the icon.<br>
Note: You can update the title via Steam Workshop, but it is recommended to use this command, because SCP: Observer will always use the title specified in the `mod.json` file.

Example:<br>
`scpo_uploader.exe update --mod "path/to/mod/folder" --changes "Made it even better"`<br>
`scpo_uploader.exe update --mod "path/to/mod/folder" --changes "Made it even better" --icon "path/to/icon"`

# Enjoy

If you have any feedback or suggestions, feel free to contact me and also let me know what you created.

Have fun modding.