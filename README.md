# Beta 1.7.3 VR Minecraft

A mod that runs Minecraft Beta 1.7.3 in VR.

This is a fan project, not connected to Mojang, Microsoft or Valve. It doesn't include Minecraft. You need a Microsoft account that owns the game. Prism downloads the game from Mojang, and the package adds this mod and its changes to some of the game's classes.

**Status:** early test build, mostly played on one headset. Multiplayer works on offline-mode Beta 1.7.3 servers; see Multiplayer below.

## Where it runs

There's one zip, and it works in both places:

| Where | Status |
| --- | --- |
| **Steam Frame, on its own** | Works. No PC needed. |
| **PC with SteamVR** | Works. |

On a PC, other headsets work through SteamVR. Quest players can use Virtual Desktop with its OpenXR runtime set to SteamVR. There's no separate Oculus version.

## Install

Pick your setup and open its steps.

<details>
<summary><b>Steam Frame (standalone, no PC)</b></summary>

<br>

Do all of this on the headset.

**You need:**
- A Steam Frame
- A Microsoft account that owns Minecraft
- [Prism Launcher](https://prismlauncher.org/), the **ARM64 AppImage**

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
6. The game opens in VR. Point at menus and pull the trigger to click.

</details>

<details>
<summary><b>PC with SteamVR</b></summary>

<br>

Do all of this on the PC.

**You need:**
- A PC with SteamVR and a VR headset (Quest players: Virtual Desktop or Steam Link into SteamVR)
- A Microsoft account that owns Minecraft
- [Prism Launcher](https://prismlauncher.org/), the normal **Windows** version

**Steps:**
1. Install Prism Launcher and open it.
2. Add your Microsoft account when Prism asks.
3. In Prism, choose **Add Instance → Import** and paste this link:

   ```
   https://github.com/cyanmayn/Beta-1.7.3-VR-Minecraft/releases/latest/download/Beta-1.7.3-VR-Minecraft.zip
   ```

   Or [download the zip](https://github.com/cyanmayn/Beta-1.7.3-VR-Minecraft/releases/latest) and drag it into Prism's window.
4. Start SteamVR and put your headset on.
5. In Prism, select the instance and press **Play**.
6. The first launch takes a minute while Prism downloads the game, Java and the sounds. If it asks about installing Java, say yes.
7. The game opens in VR. Point at menus and pull the trigger to click. The PC window shows a view for recording or streaming (**Options → VR Video → Desktop view**).

If SteamVR is running, the game uses it, even if another OpenXR runtime is your default.

</details>

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
| View button | Chat (multiplayer) |

You can also swing the item in your hand to hit mobs and mine blocks.

To craft repeatedly, hold the trigger on the crafting result for a second.

## Settings

**Options → VR Controls:** button bindings, turning style, aiming hand, trigger or swing, hotbar position, room movement.

**Options → VR Video:** resolution, smooth distance, comfort vignette, desktop view.

**Desktop view** sets what the game window on your PC shows, for recording or streaming. **Smooth centre** (the default on a PC) is a steadied camera from between your eyes, with the menus and HUD on top. **Centre** is the same without the steadying. **Left eye** copies one eye, which is cheaper. **Off** shows nothing. The centre camera draws the world one extra time, so turn it off if the game stutters.

If the game stutters, lower the resolution or shorten the render distance.

## Multiplayer

Any **Minecraft Beta 1.7.3** server works, as long as it's in **offline mode** (`online-mode=false` in `server.properties`). Mojang's Beta login servers no longer exist, so online-mode servers can't be joined. VR players and desktop players can play together.

**To see VR players' real head and hand movement,** the server needs the **BetaVR server add-on**. With it, other players who have this mod (in VR or on a desktop) see a VR player's head turn and tilt and their arms follow their hands. Players on a plain Beta game still see a normal player. Without the add-on, everyone looks like a normal player.

**Setting up the add-on** (BisectHosting or any host that lets you choose a custom jar):

1. Download `BetaVR-Server-Addon.jar` from this project's Releases page.
2. Put it in the server's main folder, next to the official server jar (`minecraft_server-b1.7.3.jar`). The add-on doesn't include Minecraft; it starts the official jar with its changes in front.
3. Choose `BetaVR-Server-Addon.jar` as the server jar (on BisectHosting: the custom jar setting).
4. Set `online-mode=false` in `server.properties`, and turn off any "online mode" switch in your host's panel.
5. Start the server. The console should say `Server add-on ... starting minecraft_server-b1.7.3.jar (official b1.7.3)`, and `<name> has the BetaVR mod` when a player with the mod joins.

In offline mode anyone who knows the address can join under any name, so only share it with people you trust.

**Typing the address:** the VR keyboard has **Paste**: copy the address in another app, then press Paste.

## Known issues

<details>
<summary><b>Steam Frame streaming from a PC: pinning a window takes away the game's controls</b></summary>

<br>

**What happens:** if you play on a PC and stream to a Steam Frame, pinning a window from the Frame's menu stops the game from getting any controller input. Your controls come back as soon as you close that window.

**Why:** while a window is pinned, the Frame keeps telling SteamVR that its menu is open. Any time the menu is open, SteamVR gives the controllers to the menu instead of the game. SteamVR's logs show the Frame sending "menu open" when the window is pinned and "menu closed" only once it's gone. This affects any PC game streamed to the Frame, not just this one.

**Not affected:** other headsets through SteamVR. A Quest Pro through Virtual Desktop was tested and keeps its controls with pinned windows.

**Why it isn't fixed yet:** the only workaround found so far is changing SteamVR's own settings on the player's PC, so the menu doesn't take over the controllers. That would change how SteamVR behaves for every game, not just this one. A mod shouldn't do that to people's setups, so it's been left alone for now.

**For now:** close the pinned window to get your controls back, or play through another headset.

</details>

## Problems

The game writes a log called `betavr.log` in the instance's `minecraft` folder. Include it when reporting a problem. Its first line says which build you're running.

## Licences

The package includes third-party libraries. See [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt).
