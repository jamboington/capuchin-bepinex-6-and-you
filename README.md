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

[^1]: These are not offical requirements laid out by Capuchin staff. They are the only mod loaders that have worked (after experimentation) with Capuchin.
[^2]: These requirements are self-imposed because Capuchin V2 is a _IL2CPP_ Unity game. This means that none of it's internal libraries (``.dll``s) are avaliable.
[^3]: Major mod loaders, [BananaModManager](https://github.com/developerpixel0/bananamodmanager) and [CapuchinModManager](https://github.com/jamboington/capuchinmodmanager) are compatable with BepInEx 6.
[^4]: While you can use any text editor you would like, I recommend Visual Studio 2022.
[^5]: BepInEx 6 must be ran at least once to generate the built-in Unity libraries needed to develop mods. Unlike _Mono_ games like Gorilla Tag, they must be compiled by BepInEx first to use them.
