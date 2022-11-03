# Livery Modding Guide - Adding Metallic Finish
This is a guide on how to enable and add metallic finish to cars that only have matte or paint finish in F1 Manager 2022.

## Requirements
- FModel or Carefreeduck's [unpacker](https://github.com/carefreeduck/F1ManagerModding/blob/main/Packing.md)
- [umodel](https://www.gildor.org/en/projects/umodel)
- [UE Asset Editor](https://github.com/kaiheilos/Utilities)
- Notepad++ or similar
- Photoshop or Krita, for exporting TGA files
- Unreal Engine 4.27
- Albomis' [packer](https://github.com/Ablomis/mod91/blob/main/Repacking.md)

## Editing the Material Instance file

First off we need a copy of the Material Instance file from a team that has metallic layers enabled.

Here's a list of teams that have the necessary files:
- Mercedes
- AstonMartin
- Williams

1. Unpack the file, **MI_<SourceTeam>_MaterialMask.uasset**. These files are stored in this directory.
  
`/F1Manager22/Content/Cars/RaceTeam/<SourceTeam>/Materials`
  
2. Open the newly extracted file using **Asset Editor**. Navigate to the 'Header List' section, and edit all entries with the <SourceTeam> name into your desired team, for example, McLaren. 
