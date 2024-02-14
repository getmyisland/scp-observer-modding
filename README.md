# SCP: Observer Modding Guide

> [!CAUTION]
> I'm currently making changes to modding process for SCP: Observer and I strongly advise against creating a mod now and instead wait until the revision is complete.

> [!TIP]
> Some example mods can be found in the [Examples](/Examples) folder.

Have fun modding.

## Creating Mods

Unfortunately, due to time constraints, only custom skins for modding are supported.

### Custom Skins

See [SKIN.md](/SKIN.md).

## SCP: Observer Tools

At this point, you should have a mod file ready from the previous steps.

You can now download the **SCP: Observer Tools** application in your Steam library. You may need to adjust your library settings so that Steam displays both Tools and Games.

![SCP: Observer Tools](https://i.imgur.com/6VeiE9Y.png)

### Create Mod Folder

1. In **SCP: Observer Tools** select the `Modding` tab.

2. Fill out all required fields.

> [!TIP]
> Mod is your file generated in the previous steps (e.g. `skin_mod`).

3. Copy the generated mod folder to `%STEAM%/steamapps/common/SCP_Observer/Mods/`.

### Testing Mods

1. Open **SCP: Observer** and activate your mod in the Skins menu.

2. Test your mod in the game and adjust possible issues.

> [!TIP]
> If your mod is not shown in the Skins menu make sure it is located in the correct folder (`%STEAM%/steamapps/common/SCP_Observer/Mods/`).

### Steam Workshop

> [!IMPORTANT]  
> Only upload mods that you are 100% sure work correctly.

1. In **SCP: Observer Tools** select the `Steam Workshop` tab.

2. Fill out all required fields.

> [!TIP]
> Icons are images or gifs in a square format. Recommended size `512x512 px`. Supported formats are `PNG`, `JPG` and `GIF`. Smaller than 1mb.
>
> To find the workshop item id of your mod, copy the URL of your mod's Steam Workshop page. The numbers after `?id=` are your workshop item id.
> 
> ![Workshop Item ID](https://i.imgur.com/iRcsjQJ.png)

That's it :)

> [!WARNING]  
> Before your mod will be visible on the Steam Workshop you have to accept the Steam Workshop Terms of Service and you have to set the item visibility to public.