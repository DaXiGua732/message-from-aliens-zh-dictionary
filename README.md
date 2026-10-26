# Message From Aliens · 外星语中文对照表

> 非官方粉丝制作的《Message From Aliens》外星语字形中文词典，帮助中文玩家边玩边查词。

**在线使用：** <https://daxigua732.github.io/message-from-aliens-zh-dictionary/>

## 这是什么

《Message From Aliens》（Artless Games）是一款“外星语言解码 + 科学读本 + 谜题”游戏。玩家需要在语言书里逐词猜义、填写母语翻译，再用词义解开算术、几何等章节谜题。

本项目对游戏资源做了只读静态分析：

- 从 `resources.assets` 提取全部 **1408 个外星词**与对应的 **100×100 字形贴图**；
- 解密游戏内的 `newalien` 词典（AES-CBC）与章节文本；
- 为每个词给出中文名、中文释义、英文原释义、字形构件拆解与语义分类；
- 还原 **90 个独体根字、15 种组合结构、七进制数字、语法小词**的读字规则；
- 提供可搜索、可筛选、可随机抽词的单文件网页词典。

## 网站功能

- 搜索中文、英文键名、释义、构件；
- 按语义分类、词性筛选；
- 点击任意字形查看大字图、释义、构件拆解、结构代码；
- “随机一字”适合边玩边复习；
- 内置“读字指南”，5 分钟理解造字、语法与七进制；
- 单文件 HTML，字形图全部内嵌，可离线使用。

## 仓库内容

| 文件 | 说明 |
|---|---|
| `index.html` | 单文件网页词典（GitHub Pages 首页） |
| `dictionary_zh.csv` | 1408 词 × 17 列完整词典数据 |
| `all_images_zh.csv` | 全部 2865 个图像对象（Texture2D + Sprite）的中文说明 |
| `NOTICE.md` | 版权、归属与非官方声明 |

## 数据与方法

- 游戏版本：Message From Aliens Demo，`isDemo = true`，版本 0.97，Steam AppID 1858720。
- 只读静态分析：UnityPy 解包、ILSpy 反编译、AES-CBC 解密 TextAsset；未运行游戏，未修改游戏文件。
- 1408 个词典词与 1408 张 100×100 字形贴图一一对应；指数词的冒号在运行时和贴图名中被去掉（`:1e1` → `1e1`）。
- 数字为七进制：0–6 是独体数字字，7 = `1e1`，49 = `1e2`；数字上/下的横杠表示 ×7^N / ÷7^N。
- 翻译以游戏内部英文 gloss 为准直译；原文中与现实相反的设定（如 electron 带正电）保留原意并加注，不擅自“纠正”。

## 本地使用

下载 `index.html` 后双击即可打开；也可以把整个仓库放到任意静态服务器。

## 反馈

发现错译、缺图或页面问题，欢迎在 [Issues](https://github.com/DaXiGua732/message-from-aliens-zh-dictionary/issues) 中反馈。请附上词条的英文键名或截图。

## 版权与免责声明

本项目是**非官方、非商业**的粉丝作品，与 Artless Games 无隶属关系。

《Message From Aliens》的游戏名称、字形、文本、图像及其他素材版权归 **Artless Games** 所有。本仓库仅出于语言学习与辅助游玩的目的，展示静态分析所得的字形缩略图与中文释义；不包含游戏本体、可执行文件或原始资源包。

如果你喜欢这款游戏，请在 [Steam](https://store.steampowered.com/app/1858720/) 购买正版。若权利人认为本仓库内容不当，请通过 Issue 联系，我会及时处理或下架。
