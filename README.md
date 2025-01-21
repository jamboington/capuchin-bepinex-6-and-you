# Capuchin, BepInEx 6, and You
I am Jambo, one of the developers for [BananaModManager](https://github.com/developerpixel0/bananamodmanager) and the only developer for [CapuchinModManager](https://github.com/jamboington/capuchinmodmanager).
We are on a mission to get mods out there for people to use, and we need some help from decicated modders that are willing to make good mods that do not ruin other's gameplay.

This paper will give you a rundown of how to start developing a BepInEx mod. Capuchin V2 currently requires either [MelonLoader](https://github.com/LavaGang/MelonLoader) or [BepInEx 6](https://github.com/bepinex/bepinex).[^1][^2]
For sake of simplicity (if you are coming from a background of making mods for _Gorilla Tag_), we will use BepInEx 6, which is supported by both major mod loaders.[^3]

## Prerequisites
- A working Steam installation, with Capuchin downloaded
- Any mod installer compatable with BepInEx 6[^3]
- Visual Studio 2019 or 2022.[^4]

## 1. Install BepInEx
### 1.1. Using Banana/Capuchin ModManager
Using BananaModManager or CapuchinModManager, check "BepInEx 6" on BananaModManager, or "BepInEx" on CapuchinModManager, then press install.
Run Capuchin.exe at least once to generate the libraries you need to develop the mods.[^5]

### 1.2. From Source
Download the latest BepInEx 6 release (most likely a pre-release) and drag it's contents into your Capuchin installation folder.
Run Capuchin.exe at least once to generate the libraries you need to develop the mods.[^5]

## 2. Mod Initialization
**If you have not run Capuchin at least once after your install[^5], please do so.**

There should be all the binaries you need to make your mod in your ``/BepInEx`` directory. It will have all the ``*.dll``s you need to import into your project. After that, create a Gorilla Tag mod as usual, however, **you must create the mod differently**.

```cs
using BepInEx;
using BepInEx.Logging;
using BepInEx.Unity.IL2CPP;

namespace MyMod
{
  public class ModInfo
  {
    public static string guid = "com.modauthor.capuchin.modname";
    public static string name = "Mod Name";
    public static string version = "1.0.0";
  }

  [BepInPlugin(ModInfo.guid, ModInfo.name, ModInfo.version)]
  public class Plugin : BasePlugin
  {
      internal static new ManualLogSource Log;
  
      public override void Load()
      {
          Log = base.Log;
          Log.LogInfo($"Hello world!");
      }
  }
}
```

This is the basic process to create a mod. From here, you should be able to change the game simularally to BepInEx 5[^6].

## 3. Other Information
- Capuchin V3 may be a Mono game with different kinds of syntax. I will update this for Capuchin V3 upon release, so please recheck to confirm your mods will remain compatable.
- Please do **not** abuse the power that being a developer gives you. Do not make illegal and bad cheats.
- If you have any issues, consult the Capuchin Modding Discord or the official Capuchin server.

[^1]: These are not offical requirements laid out by Capuchin staff. They are the only mod loaders that have worked (after experimentation) with Capuchin.
[^2]: These requirements are self-imposed because Capuchin V2 is a _IL2CPP_ Unity game. This means that none of it's internal libraries (``.dll``s) are avaliable.
[^3]: Major mod loaders, [BananaModManager](https://github.com/developerpixel0/bananamodmanager) and [CapuchinModManager](https://github.com/jamboington/capuchinmodmanager) are compatable with BepInEx 6.
[^4]: While you can use any text editor you would like, I recommend Visual Studio 2022.\
[^5]: BepInEx will generate the libraries you need when running for the first time, which is why it is essential to run Capuchin at least once after BepInEx is installed.
[^6]: BepInEx 5 and BepInEx 6 contain different syntax rules. You may still find success sideloading a ``MonoBehaviour`` class to keep simular syntax.
[^5]: BepInEx 6 must be ran at least once to generate the built-in Unity libraries needed to develop mods. Unlike _Mono_ games like Gorilla Tag, they must be compiled by BepInEx first to use them.
