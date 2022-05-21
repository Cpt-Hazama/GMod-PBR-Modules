# GMod-PBR-Modules
Required files for my mods to work properly. This is the latest PBR setup for Source engine that allows 1:1 PBR.

## Installation
Place in /GarrysMod/garrysmod/ folder

## Developer Usage
If everything is installed correctly, you can use the PBR shader in your VMTs. This PBR shader allows for MRAO styled design.

```vmt
PBR
{
    "$basetexture"      "models/cpthazama/weapons/axe/axe_bc"
    "$bumpmap"          "models/cpthazama/weapons/axe/axe_n"
    "$mraotexture"      "models/cpthazama/weapons/axe/axe_mrao"
    "$emissiontexture"  "models/cpthazama/weapons/axe/mix25_e"
    "$model"            "1"
}
