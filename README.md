## 视觉小说游戏引擎工具集

本项目提供了一套工具，用于视觉小说游戏引擎的解包与封包。

## 版本更新
- **V1.3.3.1**：
- `Softpal`引擎
	- 新增游戏标题修改

- **V1.3.3**：
- `Softpal`引擎
  - 新增 自动修改`游戏EXE`编码范围至 gbk
  - 优化提取`josn`时，识别`scripts`脚本文本行的准确性

- **V1.3.2**：
- `Softpal`引擎
  - 优化读取文件上的编码异常，减少错误
  - 优化提取`josn`时，人名`name`的识别
  - 修复`人名表.json`无法进行二次合成
  - 增加 `Pal.dll` 处理 - 通过16进制替换自动汉化弹窗。

- **V1.3.1**：
- `Softpal`引擎
  - 修复 无法从多个json文件合成至单个json的问题
  - 改进 json文本拆分逻辑

- **V1.3.0**：
- `WillPlus/AdvHD`引擎
  - 已实现 `pna` 复合图形的解包和封包，可用于汉化ui界面
  
- 新增加了对`Softpal`引擎的支持
    -  `pac` 文件的解包和封包3
    -  提取与合成 `TEXT.DAT` 文件
    -  将文本提取至 `json` 文件，`name`与 `message`
        - 单个`txt`文本可解析成多个`json`文件

- **V1.2.9**：
- `WillPlus/AdvHD`引擎
    - 新增'.NET运行库'检查
    - 修复`ws2Parse(net6.0)`文本提取问题
    - 修复`vntextpatch`提取文本时，不会自动创建文件夹问题

- **V1.2.8**：
- WillPlus/AdvHD引擎
    - 增加 `ws2Parse` 文本的3种编码文本处理方案
        - `utf-8`编码
        - `gbk`编码
        - `shift-jis`编码 （此编码无需修改游戏exe，通过sjis隧道实现）

## 功能概述

当前支持引擎

- **WillPlus/AdvHD引擎**:
    - **ARC文件处理**: 提供`.arc`文件的解包和封包功能。
    - **WS2文件编解码**: 提供`.ws2`文件的解码与编码。
    - **文本提取与合成**: 支持多种方案提取`.ws2`文件中的文本，并将翻译后的文本合成回`.ws2`文件。
        - **VNTextPatch方案**: 适用于较旧引擎的文本提取，建议在合成前进行游戏测试。
        - **If My Heart Had Wings Script Tools方案**: 适用于特定游戏的文本提取。
        - **.ws2parse 方案**: 提供优先选择的文本提取和合成。
    - **文本格式转换**: 提供文本与JSON格式之间的相互转换，便于翻译过程中的文本处理。
    - **PNA文件处理**: 提供`.pna`文件（复合图形）的解包和封包功能，可用于汉化ui界面。
    - **文本批量替换**: 提供全文本字符的批量替换功能，以便快速更新和修正翻译文本。
    - **自动化汉化流程**: 实现从原始`.arc`封包到汉化`.arc`封包的完整自动化流程。
    - **字节码长度匹配**: 匹配字节码长度和修复过长文本，确保翻译后的文本与原文在游戏中的显示一致(已废弃)。
- **Softpal引擎**:
    - **PAC文件处理**: 提供`.pac`文件的解包和封包功能。
    - **TEXT.DAT文件处理**: 提供`TEXT.DAT`文件的解包和封包功能。
    - **文本提取与合成**: 支持将`.txt`文件提取至`json`文件，`name`与`message`。
    - **Pal.dll处理**: 通过16进制替换自动汉化弹窗。
    - **游戏EXE编码范围修改**: 自动修改`游戏EXE`编码范围至 gbk。

工具集通过命令行界面提供这些功能，用户可以根据提示选择相应的操作，从而高效地完成翻译和汉化工作。

## 环境要求

- Python 3.x
- 通过 `requirements.txt` 安装的依赖库

## 安装(未上传源码)

一、通过源码安装

1. 确保Python 3.x已安装在您的系统上。
2. 安装必要的游戏引擎文件处理工具，并确保它们可以在命令行中调用。
3. 克隆本项目到本地系统。

```bash
git clone https://github.com/YIWANG-sketch/Galgame_automation_processing_tool.git
```

二、可以在 `release` 页面下载最新打包版本。

## 使用方法

运行`main.py`或者`run.bat`开始使用工具集。

```bash
python main.py
```

根据命令行提示进行操作选择，工具集将引导您完成所需的翻译和汉化步骤。

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.
