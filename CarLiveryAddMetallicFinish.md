# Livery Modding Guide - Adding Metallic Finish
This is a guide on how to enable and add metallic finish to cars that only have matte or paint finish in F1 Manager 2022.

## Requirements
- FModel or Carefreeduck's [unpacker](https://github.com/carefreeduck/F1ManagerModding/blob/main/Packing.md) to unpack the necessary game files
- [umodel](https://www.gildor.org/en/projects/umodel) to extract files from .uasset format
- [UE Asset Editor](https://github.com/kaiheilos/Utilities) to edit .uasset files
- Notepad++ or similar
- Photoshop or Krita for editing and exporting TGA files
- Unreal Engine 4.27
- Ablomis' [packer](https://github.com/Ablomis/mod91/blob/main/Repacking.md)

## Editing the Material Instance file

First off we need a copy of the Material Instance file from a team that has metallic layers enabled.

Here's a list of teams that has the necessary files:
- Mercedes
- AstonMartin
- Williams

Here are combinations which have been tested & working:
- AstonMartin, works for Ferrari & AlfaRomeo
- Mercedes, works for Haas & Alpine
- Williams, works for McLaren

The Material Instance files are stored in this directory.
  
`/F1Manager22/Content/Cars/RaceTeam/<SourceTeam>/Materials`

1. Unpack the file, `MI_<SourceTeam>_MaterialMask.uasset`, using either Fmodel or Carefreeduck's unpacker. 
  
2. Open the newly extracted file using Asset Editor. Navigate to the 'Header List' section, then edit all entries with the `<SourceTeam>` name into your desired team, for example, from Williams to McLaren. If a Material Instance file doesn't work for that team, you need to try with the other MI files.

It would be easier to edit these using Notepad++, as can easily replace the names and it would retain formatting. Paste everything back into AssetEditor once done. 

3. Once you're finished replacing the team names, save your newly edited .uasset file into your 'ToPack' folder with the directory, 

`ToPack/F1Manager22/Content/Cars/RaceTeam/<TargetTeam>/Materials/MI_<TargetTeam>_MaterialMask.uasset`

## Masking out the livery

It is possible to enable metallic finish by editing the `Livery_materialmask.uasset` file. 

1. Create a mask for the parts of the livery you don't want to be metallic, then add black fill layer on the bottom. All parts masked in black will be paint finish. You can then adjust the Green channel for roughness using the `Livery_materialmask.tga` file if you want a smoother or rougher metallic finish.

You can find Livery mask files here:

`F1Manager22/Content/Cars/RaceTeam/<TargetTeam>/Textures`

2. Pack your texture files in Unreal Engine and copy the newly cooked .uasset files into your 'ToPack' directory for that team. 

`ToPack/F1Manager22/Content/Cars/RaceTeam/<TargetTeam>/Textures`

3. Repack your .uasset files into .pak using the repacker from Ablomis

## Closing Notes

Mercedes has its own Material Instance file which is a bit different to the Aston and Williams. It has fresnel variables built-in which is absent in the other two Material Instance files. Try to experiment with it to see which metallic finish you prefer. 
