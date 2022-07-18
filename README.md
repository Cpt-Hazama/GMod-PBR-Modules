# GMod PBR Modules
Required files for my mods to work properly. This is the latest PBR setup for Source engine that allows 1:1 PBR.

# Source Code
[Link](https://github.com/zm-reborn/zmr-game/blob/9e96e4acc563f53516d339854a2e09f5427224ff/mp/src/materialsystem/stdshaders/pbr_dx9.cpp)

# Installation
Place in /GarrysMod/garrysmod/ folder

Also, make sure 'r_PhysPropStaticLighting' is set to '0'

If you experience any crashing, then download this version of the module by Yurie:
https://yurie.thigh-high.club/r5xhxb5x.zip

# Developer Usage
If everything is installed correctly, you can use the PBR shader in your VMTs. This PBR shader allows for MRAO (Metalness, Roughness, Ambient Occ.) styled design.

```vmt
PBR
{
    "$basetexture"      "models/cpthazama/weapons/axe/axe_bc"
    "$bumpmap"          "models/cpthazama/weapons/axe/axe_n"
    "$mraotexture"      "models/cpthazama/weapons/axe/axe_mrao"
    "$emissiontexture"  "models/cpthazama/weapons/axe/mix25_e"
    "$model"            "1"
}
```

### New parameters:
- $AlphaTestReference (0/1)
- $MRAOTexture (Texture or "dev/pbr_mraotexture") - Texture with metalness in R, roughness in G, ambient occlusion in B
- $EmissionTexture (Texture) - Emission texture
- $UseENVAmbient (0/1) - Use the cubemaps to compute ambient light
- $SpecularTexture (Texture) - Specular F0 RGB map
- $Parallax (0/1) - Use Parallax Occlusion Mapping
- $ParallaxDepth (Float) - Depth of the Parallax Map
- $ParallaxCenter (Float) - Center depth of the Parallax Map

# Examples
### In-Game Screenshots (Provided by Mayhem)
![unknown-24](https://user-images.githubusercontent.com/7193583/169636307-03911f50-00a9-44c5-927f-b283e8ab64e7.png)
![unknown-29](https://user-images.githubusercontent.com/7193583/169636315-b942e7df-95e3-4e3f-8f3a-757bbf19b2dd.png)

### MRAO Example
RGB
![image](https://user-images.githubusercontent.com/7193583/169679824-d902b8cd-7fe8-46d2-b6c6-abed88cb42f8.png)
R (Metalness)
![image](https://user-images.githubusercontent.com/7193583/169679847-607c5ed5-8eed-4781-88ab-2caf72ed728b.png)

G (Roughness)
![image](https://user-images.githubusercontent.com/7193583/169679849-9980c8a5-c892-41a7-b6db-72a94540986e.png)

B (Ambient Occlusion)
![image](https://user-images.githubusercontent.com/7193583/169679853-01c01c2f-463e-492a-b653-3d3117ef2771.png)

# Credits
- Zombie Master Reborn Team - Creating the latest PBR modules for Source
- Cpt. Hazama - Organizing and providing the files for users to easily obtain/use
