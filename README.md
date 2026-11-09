# Beta 1.7.3 VR Minecraft

A mod that runs Minecraft Beta 1.7.3 in VR.

This is a fan project, not connected to Mojang, Microsoft or Valve. It doesn't include Minecraft. You need a Microsoft account that owns the game. Prism downloads the game from Mojang, and the package adds this mod and its changes to some of the game's classes.

**Status:** early test build, mostly played on one headset. Multiplayer is untested and could only work on offline-mode servers.

## Editions

| Edition | Status | Runs on |
| --- | --- | --- |
| **Steam Frame Standalone** | Available | The headset itself. No PC needed. |
| **SteamVR** | Planned, not available yet | A PC with SteamVR |

The instructions below are for the Steam Frame Standalone edition.

## Install

You do all of this on the headset. You don't need a PC.

**You need:**
- A Steam Frame
- A Microsoft account that owns Minecraft
- [Prism Launcher](https://prismlauncher.org/), the ARM64 AppImage version

**Steps:**
1. Install Prism Launcher and open it.
2. Add your Microsoft account when Prism asks.
3. In Prism, choose **Add Instance → Import** and paste this link:

   ```
   https://github.com/cyanmayn/Beta-1.7.3-VR-Minecraft/releases/latest/download/Beta-1.7.3-VR-Minecraft-Steam-Frame-Standalone.zip
   ```

   Or [download the zip](https://github.com/cyanmayn/Beta-1.7.3-VR-Minecraft/releases/latest) and drag it into Prism's window.
4. Select it and press **Play**.
5. The first launch takes a minute while Prism downloads the game, Java and the sounds. If it asks about installing Java, say yes.
6. The game opens in VR. Point at menus and pull the trigger to click.

## Updating

Each new zip imports as a separate instance with no worlds in it. To keep a world:

1. Import the new zip.
2. In Prism, open the old instance's folder and go to `minecraft/saves`.
3. Copy your world's folder into `minecraft/saves` in the new instance.
4. Delete the old instance once your world works in the new one.

## Controls

These are the defaults on Steam Frame controllers. You can change them under **Options → VR Controls**.

| Control | Action |
| --- | --- |
| Right trigger | Break, attack, click in menus |
| Left trigger | Place, use items |
| Left stick | Walk |
| Right stick left/right | Turn |
| Right stick up/down, or D-pad left/right | Change hotbar slot |
| A | Jump |
| Left stick click | Sneak |
| B | Inventory |
| X | Drop item |
| Y | Pause / back |
| View button | Chat (multiplayer only) |

You can also swing the item in your hand to hit mobs and mine blocks.

To craft repeatedly, hold the trigger on the crafting result for a second.

## Settings

**Options → VR Controls:** button bindings, turning style, aiming hand, trigger or swing, hotbar position, room movement.

**Options → VR Video:** resolution, smooth distance, anti-aliasing, comfort vignette.

If the game stutters, lower the resolution or anti-aliasing, or shorten the render distance.

## Problems

The game writes a log called `betavr.log` in the instance's `minecraft` folder. Include it when reporting a problem. Its first line says which build you're running.

## Licences

The package includes third-party libraries. See [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt).
