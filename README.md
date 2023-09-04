# ReStock 0.625m Probes / Heatshield FIX
A Patch to Fix ReStock 1.4.3's overheating Probe Cores in KSP.

### The Problem
When using the ReStock mod for KSP, the OCTO probe core overheats to near-explosion on descent from a standard Low Kerbin Orbit, with a 33.5km Pe. This occurs when the craft consists of simply: The 0.625m Heat Shield (HeatShield0), the Probe Core, a 0.625m battery, and a standard parachute. On deeper dive, the other probe cores in the 0.625m class also suffer some less severe changes to their heat profiles.

### Why does that happen?
The stock CUBE_MESH for these probe cores has not been included in the 'restock-probes.cfg' file. So KSP generates a new mesh for each of them, based on ReStock's 3D models. The OCTO suffers most, out of the three small probes, because its model includes two little nubs protruding from the bottom... which penetrate the Heat Shield. Because of these nubs, when KSP generates the cube mesh for the OCTO, it ends up (this is my guess) extending the OCTO's mesh passed (or flush with) the heat shield's mesh. This leaves the OCTO significantly unoccluded during re-entry, and causes it to begin overheating in situations where the Stock part wouldn't even display a heat tick.

### What's the Fix?
The fix is to simply include the stock CUBE_MESH for each of the 0.625m probe cores, as lifted from the PartsDatabase.cfg at runtime. And that's all I've done here. Extracting this mod into your /Kerbal Space Program directory simply overwrites the restock-probes.cfg, adding these CUBE_MESH declarations, while emptying out your PartsDatabase.cfg, to force a refresh of any stored meshes.

# Installation
- Download the .zip from the [Releases](https://github.com/roninpawn/ReStock-0.625m-Probes-Heatshields-FIX/releases) page.
- Extract it into your /Kerbal Space Program directory. (Not into /GameData, but into your root /KSP directory)
- That it. You done.

### Additional Words
For the sake of search relavence and helping people who are having this problem land here, on the solution, I should say something like 'ReStock alters gameplay changes heatshields and probe core probestack for Probodyne probeCoreHex_v2 probeCoreOcto_v2 probeCoreOcto2_v2 occlusion probe pop go boomy make bye-bye no good!'

Also, I've put this under the MIT license because that's what PorktoberRevolution has [ReStock](https://github.com/PorktoberRevolution/ReStocked) under.
