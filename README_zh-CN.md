# 小米平板自定义开机动画
[English](/README.md) | 简体中文

## 介绍
专为平板设备打造的修改开机动画模块。平板与其他设备略有不同，其动画会根据设备的方向而更改。
> [!NOTE] 
目前仅在小米 Pad 6 Pro (liuqin) V14.0.9.0.TMYCNXM 及 OS2.0.203.0.VMYCNXM 上进行了测试。其他平板型号、品牌和系统的平板电脑基本都能兼容，但兼容性仍需进一步测试。

## 要求
- Magisk v26.1+ / KernelSU v0.8.0+ / APatch 10568+
- Android 11+ (API 30+)
> [!WARNING]
> 此模块专为 Magisk 设计。不会为 KernelSU 和 APatch 提供支持，有可能会出现错误。

## 主题
- （之後更新）

## 安装
1. 下载[最新](https://github.com/G0246/mipad-custom-boot/releases/latest)版本
2. 根据自己的喜好更改动画長短或设计（可选）
3. Magisk / KernelSU / APatch 应用中刷入 .zip 模块
> [!TIP]
> 如果您在添加自己的动画主题后看到空白一片，则说明您没有正确压缩它，创建时请使用仅存储模式进行压缩（无压缩）。

## 待办事项
1. ~~添加脚本（Python）以自动生成不同方向的动画 ZIP 文件~~（完成）
2. 自动检测并选择相应的路径

## 压缩开机动画脚本（初始版本）
> [!NOTE]
> 此脚本是**初始版本**，未来可能会更新更多功能和改进。

一个 Python 脚本，用于自动创建仅存储模式（无压缩）的开机动画 ZIP 文件。

### 要求
- Python 3.9+

### 使用方法
```bash
python zip_bootanimation.py <目录路径>
```

### 工作原理
1. 将开机动画文件夹放在一个目录中（例如：`bootanimation/`、`bootanimation01/`、`bootanimation02/` 等）
2. 每个文件夹**必须**包含：
   - `part0/` 文件夹（包含动画帧）
   - `desc.txt` 文件（动画描述符）
3. 使用目录路径运行脚本
4. 脚本将为每个有效的开机动画文件夹创建 `.zip` 文件

### 示例
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

运行：
```bash
python zip_bootanimation.py my_animations
```

输出：
```
bootanimation.zip
bootanimation01.zip
```

## 免责声明
**刷写此模块可能会导致您的设备进入引导循环，强烈建议使用引导循环保护模块。对于使用此模块对您的设备或数据造成的任何损害，我概不负责。使用风险自负。**

## 许可证
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
