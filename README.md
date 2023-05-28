# GMod PBR Modules
Required files for my mods to work properly. This is the latest PBR setup for Source engine that allows 1:1 PBR.

# Warning
x64 version of GMod is unsupported, you must use the default, pre-release, or dev branches to use this shader.

# Source Code
[Link](https://github.com/zm-reborn/zmr-game/blob/9e96e4acc563f53516d339854a2e09f5427224ff/mp/src/materialsystem/stdshaders/pbr_dx9.cpp)

# Installation
Place in /GarrysMod/garrysmod/ folder

Also, make sure 'r_PhysPropStaticLighting' is set to '0', otherwise when props "sleep" they will turn black. You can make this default to 0 by adding it to your autoexec.cfg in your /cfg/ folder

If you experience any crashing, then download this version of the module by Yurie:
https://yurie.thigh-high.club/r5xhxb5x.zip

# Developer Usage
If everything is installed correctly, you can use the PBR shader in your VMTs. This PBR shader allows for MRAO (Metalness, Roughness, Ambient Occ.) styled design.

```vmt
"PBR"
{
    	"$basetexture"              		"models/cpthazama/mgr/mg_ray/em0200000"
	"$bumpmap"				"models/cpthazama/mgr/mg_ray/em0200000_n"
	"$mraotexture"				"models/cpthazama/mgr/mg_ray/em0200000_mrao"
	"$emissiontexture"			"models/cpthazama/mgr/mg_ray/em0200000_g"
	"$speculartexture"			"models/cpthazama/mgr/mg_ray/em0200000_s"

	"$model"				"1"
	"$surfaceprop"      			"metal"
}
```

Note that you must have $model 1 enabled for anything that isn't a brush! Otherwise it will not load the texture.

### New parameters:
- $AlphaTestReference (0/1) - Specifies the minimum color value of the alpha channel in which the effect is rounded to 255. A value of ".3" will create a thicker shape while a value of ".7" will create a thinner shape
- $MRAOTexture (Texture or "dev/pbr_mraotexture") - Texture with metalness in R, roughness in G, ambient occlusion in B. Will default to the default texture if none is provided
- $EmissionTexture (Texture) - Emissive texture; is a color texture, not a mask
- $SpecularTexture (Texture) - Specular F0 RGB map, overrides metalness from the MRAO texture
- $UseENVAmbient (0/1) - Use the cubemaps to compute ambient light, seems to cause a static lighting effect at certain angles in some areas
- $Parallax (0/1) - Use Parallax Occlusion Mapping
- $ParallaxDepth (Float) - Depth of the Parallax Map
- $ParallaxCenter (Float) - Center depth of the Parallax Map

### VTF Stuff:
- Diffuse/Emission - DXT5
- MRAO/Specular - DXT1
- Normal - BGRA8888

# Examples
### In-Game Screenshots
![20220717234226_1](https://user-images.githubusercontent.com/7193583/179635340-67cbf1f0-944f-4644-b2a7-a917ea9191f8.jpg)
![20220707005942_1](https://user-images.githubusercontent.com/7193583/179635358-f350e345-24f9-41bc-8804-0446d2f941fb.jpg)
![20230215212551_1](https://user-images.githubusercontent.com/7193583/220002427-8a6207e9-44cf-42ed-8bbe-98625e2c3d24.jpg)
![20230216042225_1](https://user-images.githubusercontent.com/7193583/220002381-3cc444a0-55b7-4afa-8b3e-8765e64452c7.jpg)
![20230126004906_1](https://user-images.githubusercontent.com/7193583/220002476-f7705fce-cacb-4932-a2a8-bc12acbd1de9.jpg)
![20230123224112_1](https://user-images.githubusercontent.com/7193583/220002524-5da4d4b6-ac51-481a-80df-0c30f7fd6d39.jpg)
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
