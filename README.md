# GMod PBR Modules
Required files for my mods to work properly. This is the latest PBR setup for Source engine that allows 1:1 PBR.

# Installation
Place in /GarrysMod/garrysmod/ folder

Also, make sure 'r_PhysPropStaticLighting' is set to '0'

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
### Provided by Mayhem
![unknown-24](https://user-images.githubusercontent.com/7193583/169636307-03911f50-00a9-44c5-927f-b283e8ab64e7.png)
![unknown-29](https://user-images.githubusercontent.com/7193583/169636315-b942e7df-95e3-4e3f-8f3a-757bbf19b2dd.png)

# Credits
- Zombie Master Reborn Team - Creating the latest PBR modules for Source
- Cpt. Hazama - Organizing and providing the files for users to easily obtain/use
