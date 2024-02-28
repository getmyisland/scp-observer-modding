# SCP: Observer Modding Guide

> [!CAUTION]
> This is an ongoing revision. I strongly advise against creating a mod now and instead wait until the revision is complete. Update 2.0 will be released on 04/25/2024.

This repository is intended to be a guide for the SCP: Observer modding process. Unfortunately, due to time constraints, only custom skins for modding are supported at this time.

Have fun modding.

## Creating Mods

### Getting Started

1. Download [Unity](https://unity.com/de/download).

2. Open Unity Hub and create a new URP project.

3. Open the project and import the `Modding.unitypackage` file by dragging it into the `Project` window. Make sure to import everything from this package.

4. Right-Click on the `Assets` folder and select `Create` -> `Folder`, name it `Plugins`.

5. Drag and drop the `Modding.dll` and the `Modding.Editor.dll` file into the newly created folder.

6. Go to [Facepunch.Steamworks](https://github.com/Facepunch/Facepunch.Steamworks/releases) and download the newest release as `.zip`.

7. Unzip the downloaded archive and drag and the drop the contents of the `Unity` folder into your previously created `Plugins` folder.

### Custom Skins

See [SKIN.md](/SKIN.md).

## Testing Mods

> [!TIP]
> Exported mods (AssetBundles) are located in `Assets/Modding/Export`

1. Place your mod in `%STEAM%/steamapps/common/SCP_Observer/Mods/`.

2. Start SCP: Observer and test the mod.

## Steam Workshop

> [!IMPORTANT]  
> Only upload mods that you are 100% sure work correctly.

1. In the Unity menu bar, click on `SCP: Observer` -> `Steam Workshop`.

2. A new window should now open.

3. Select a mode (create new mod or update existing one?).

4. Select your mod (AssetBundle) you created in the previous steps.

5. Select an icon for your mod that will be shown in the Steam Workshop.<br/>
	5.1. Supported image formats are `.png`, `.jpg`, `.gif`.<br/>
	5.2. Less than 1MB file size.<br/>
	5.3. Square format (e.g. 512x512 resolution)

6. Click on `Create` or `Update` depending on what you want to do.

7. Any further modifications like description, screenshots can be made on the Steam Workshop page for your mod.

> [!WARNING]  
> Before your mod will be visible on the Steam Workshop you have to accept the Steam Workshop Terms of Service and you have to set the item visibility to public.