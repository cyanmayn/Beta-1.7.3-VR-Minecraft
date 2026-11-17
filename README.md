# Beta 1.7.3 VR Minecraft

A mod that runs Minecraft Beta 1.7.3 in VR.

This is a fan project, not connected to Mojang, Microsoft or Valve. It doesn't include Minecraft. You need a Microsoft account that owns the game. Prism downloads the game from Mojang, and the package adds this mod and its changes to some of the game's classes.

**Status:** early test build, mostly played on one headset. Multiplayer is untested and could only work on offline-mode servers. Frame and PC players should be able to join the same server.

## Where it runs

There's one zip, and it works in both places:

| Where | Status |
| --- | --- |
| **Steam Frame, on its own** | Works. No PC needed. |
| **PC with SteamVR** | Should work, not tested yet |

On a PC, other headsets work through SteamVR. Quest players can use Virtual Desktop with its OpenXR runtime set to SteamVR. There's no separate Oculus version.

## Install

On the Frame, you do all of this on the headset. On a PC, you do it on the PC.

**You need:**
- A Steam Frame, or a PC with SteamVR and a VR headset
- A Microsoft account that owns Minecraft
- [Prism Launcher](https://prismlauncher.org/). On the Frame, get the ARM64 AppImage. On a PC, get the normal Windows version.

**Steps:**
1. Install Prism Launcher and open it.
2. Add your Microsoft account when Prism asks.
3. In Prism, choose **Add Instance → Import** and paste this link:

   ```
   https://github.com/cyanmayn/Beta-1.7.3-VR-Minecraft/releases/latest/download/Beta-1.7.3-VR-Minecraft.zip
   ```

   Or [download the zip](https://github.com/cyanmayn/Beta-1.7.3-VR-Minecraft/releases/latest) and drag it into Prism's window.
4. Select it and press **Play**.
5. The first launch takes a minute while Prism downloads the game, Java and the sounds. If it asks about installing Java, say yes.
6. The game opens in VR. Point at menus and pull the trigger to click. On a PC, SteamVR has to be your OpenXR runtime, which you can set in SteamVR's settings under OpenXR.

## Updating

Each new zip imports as a separate instance with no worlds in it. To keep a world:

1. Import the new zip.
2. In Prism, open the old instance's folder and go to `minecraft/saves`.
3. Copy your world's folder into `minecraft/saves` in the new instance.
4. Delete the old instance once your world works in the new one.

## Controls

These are the defaults on Steam Frame controllers. Other controllers use a similar layout. You can change them under **Options → VR Controls**.

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
