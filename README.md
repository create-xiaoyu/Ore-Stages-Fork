# Ore Stages (Fixed Fork) [![](http://cf.way2muchnoise.eu/1301559.svg)](https://minecraft.curseforge.com/projects/1301559) [![](http://cf.way2muchnoise.eu/versions/1301559.svg)](https://minecraft.curseforge.com/projects/1301559)

**This is a maintained fork of the original Ore Stages mod, with critical compatibility fixes for Minecraft 1.12.2 modpacks.**

> ⚠️ **Important Notice**: The original Ore Stages mod by Darkhax is no longer maintained. This fork provides essential fixes for compatibility issues with The One Probe-CE and The One Probe.

## 🛠️ Key Fixes in This Fork

### Critical Server Crash Fix
- **Fixed**: `java.lang.NoSuchMethodError` crashes related to `PlayerUtils.getClientPlayer()`
- **Cause**: Service thread attempting to access client-only methods
- **Impact**: Prevents dedicated server crashes when using The One Probe
- **Solution**: Replaced unsafe client references with server-safe implementations

## 📥 Installation
1. Download the latest build from [Releases](https://github.com/create-xiaoyu/Ore-Stages-Fork/releases)
2. **Remove** the original `orestages-*.jar` from your mods folder
3. Place `orestages-2.1.*.jar` in your mods folder
4. Start your server/client as normal

## 🚀 Setup
This mod uses CraftTweaker for configuration

```zenscript
// Example script (unchanged from original)
mods.orestages.OreStages.addReplacementById("one", "minecraft:potatoes:*", "minecraft:tallgrass:2");
mods.orestages.OreStages.addReplacementById("two", "minecraft:wheat:*", "minecraft:carrots:3");
mods.orestages.OreStages.addReplacement("three", <minecraft:obsidian>, <minecraft:cobblestone>);
```

## 📝 What Happens When Staged?
If a player does not have the right stage for the block:
- The block will look like its replacement
- The player cannot right-click the block
- Drops replacement block's items
- Mining time matches the replacement block

## 🔧 CraftTweaker Methods

```zenscript
// Standard replacements
mods.orestages.OreStages.addReplacement(String stage, IIngredient original);
mods.orestages.OreStages.addReplacement(String stage, IIngredient original, IItemStack replacement);
mods.orestages.OreStages.addReplacementById(String stage, String original, String replacement);

// Non-defaulting replacements
mods.orestages.OreStages.addNonDefaultingReplacement(String stage, IIngredient original);
mods.orestages.OreStages.addNonDefaultingReplacement(String stage, IIngredient original, IItemStack replacement);
mods.orestages.OreStages.addNonDefaultingReplacementById(String stage, String original, String replacement);
```

## 🛠️ Building from Source
```bash
git clone https://github.com/create-xiaoyu/Ore-Stages-Fork.git
cd Ore-Stages
./gradlew build
# Output: build/libs/orestages-2.1.x.jar
```

## 🙏 Credits
- **Darkhax**: Original mod author
- **The One Probe-CE Mods Team**: Assistance with compatibility fixes

## 💬 Support
For issues with **this fork**, please [open an issue](https://github.com/create-xiaoyu/Ore-Stages-Fork/issues).  

---

> **Sponsor Notice**  
> [![Nodecraft](https://i.imgur.com/sz9PUmK.png)](https://nodecraft.com/r/darkhax)    
> This project is based on work originally sponsored by Nodecraft.  
> Use code [Darkhax](https://nodecraft.com/r/darkhax) for 30% off your first month of service!

---

**Disclaimer**: This is an unofficial fork. Not affiliated with or endorsed by Darkhax or the original mod developers.
