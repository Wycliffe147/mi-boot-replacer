# MiPad Custom Boot Animation
English | [简体中文](/README_zh-CN.md)

## Introduction
A simple module designed exclusively for tablet devices, replacing the boot animations with custom ones. Unlike phones, tablets often adapt their animations based on device orientation. This repo also act as a storage to store different animation designs **(Update soon!)**.

## Requirements
- Magisk v26.1+ / KernelSU v0.8.0+ / APatch 10568+
- Android 11+ (API 30+)
> [!WARNING]
> This module is designed for Magisk. KernelSU and APatch are not fully supported and unexpected bugs may occur.

> [!NOTE]  
> Currently tested only on the Xiaomi Pad 6 Pro (liuqin) running V14.0.9.0.TMYCNXM or OS2.0.203.0.VMYCNXM. It should basically work on every other tablet models, brands, and systems, but further testing is needed to confirm compatibility.

## Themes
- Original but light themed
- **(Update soon!)**

## Installation
1. Download the [latest](https://github.com/G0246/mipad-custom-boot/releases/latest) release
2. Make sure to update the animation timing, design or resolution to your liking (Optional)
3. Flash .zip module in the Magisk / KernelSU / APatch app
> [!TIP]
> If you get a blank screen after adding your own animation, it’s likely because the ZIP file wasn’t compressed right. Use "store-only" mode (no compression) when creating the ZIP.

## To-Dos
1. ~~Add a script (Python) to automate the generation of different orientation/resolution animation ZIPs~~ (Done)
2. Auto detect and select path for corresponding models

## Zip Bootanimation Script (Initial Version)
> [!NOTE]
> This script is an **initial version** and may be updated in the future with more features and improvements.

A Python script to automate the creation of bootanimation ZIP files in store-only mode (no compression).

### Requirements
- Python 3.9+

### Usage
```bash
python zip_bootanimation.py <path_to_directory>
```

### How It Works
1. Place your bootanimation folders in a directory (e.g., `bootanimation/`, `bootanimation01/`, `bootanimation02/`, etc.)
2. Each folder **must** contain:
   - A `part0/` folder (with your animation frames)
   - A `desc.txt` file (animation descriptor)
3. Run the script with the path to your directory
4. The script will create `.zip` files for each valid bootanimation folder

### Example
```
my_animations/
├── bootanimation/
│   ├── desc.txt
│   └── part0/
│       ├── 00.png
│       └── 01.png
├── bootanimation01/
│   ├── desc.txt
│   └── part0/
│       └── 00.png
```

Run:
```bash
python zip_bootanimation.py my_animations
```

Output:
```
bootanimation.zip
bootanimation01.zip
```

## Disclaimer
**Flashing this module may cause your device to bootloop, a bootloop saver module is highly recommended. I am not responsible for any damages caused to your device or data by using this module. Use at your own risk.**

## License
    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
