# Carnal Instinct 简体中文汉化

非官方独立汉化 **v0.2.0-reviewed（2026-11-25，部分校订测试版）**，面向 **Carnal Instinct Steam Build v0.7.95.16435 / UE 5.5.4**。

从当前游戏英文原文重新提取和翻译，没有使用第三方旧汉化补丁的译文。本版由 GPT-6.1-sol 子代理结合原文和对话分组校订 **2,967 条独立原文**，并补充、修正 **523 条资源记录**。其余大量对话和长描述仍沿用本地 Argos 机翻，**尚未完成全游戏润色，仍可能存在误译和英文遗漏**。

## 下载与安装

从 [Releases](https://github.com/505598397/carnal-instinct-zh-cn/releases/tag/v0.2.0-reviewed) 下载 `CarnalInstinct_Independent_zhCN_v0.2.0-reviewed.zip`。

1. 退出游戏，并备份自己的存档。
2. 如果安装过其他汉化，将其补丁文件移出游戏的 `Paks` 文件夹，避免覆盖冲突。保留游戏本体文件。
3. 将压缩包内 `patch` 文件夹中的 `Carnal_Instinct_UE5` 复制到游戏根目录。
4. 确认以下四个文件位于 `Carnal_Instinct_UE5/Content/Paks/`，然后启动游戏。

```text
pakchunk998-IndependentText_P.pak
pakchunk997-IndependentQuests_P.pak
pakchunk997-IndependentQuests_P.utoc
pakchunk997-IndependentQuests_P.ucas
```

补丁同时提供 `en` 和 `zh-Hans-CN` 语言资源，一般无需额外切换游戏语言。也可以直接从仓库的 [patch](patch/) 目录取得相同文件；校验值见 [SHA256SUMS](SHA256SUMS)。本包不附带字体；测试环境已有中文字体支持，其他环境需另行确认。

## 本次更新

- 补上此前漏提取的蓝图字节码文字，覆盖加载提示、战斗与制作界面等；523 条补充或修正记录中，净新增 517 条，修正旧记录 6 条。
- 校订全部已提取的任务原文、补漏原文、常用界面和部分物品说明；修正“LOADING WORLD”误译为“乐天世界”等错误。
- 完整校订 Farak、Void Spirit、Reseph、Shaken Villager、Amara 五组对话，其中 Amara 包含首领战后的对话。统一费尔雷克、法拉克、金辉牧团等译名，并保留 Lovense 品牌名。
- 保留格式参数、富文本标记及换行；不改动首领战或动画逻辑。

## 当前范围

| 内容 | 数量 |
| --- | ---: |
| 语言资源条目 | 15,629 |
| 包含中文的条目 | 15,029 |
| 本次 GPT-6.1-sol 校订的独立原文 | 2,967 |
| 任务 | 68 |
| 任务目标 | 333 |
| 子目标 | 123 |
| 更改的任务显示字段 | 930 |

部分数字、按键、专名和技术标识保留原文。任务补丁基于当前版本原始表格，只修改显示文字的引用，保留任务编号、条件、事件及其他内部引用。

已通过语言资源格式、源文哈希、格式参数、换行、字符串引用计数和优化资源回读检查；任务包容器校验通过，任务非显示字段保持一致。发布词典与构建产物逐条核对一致。

本次新版尚未完成安装后的游玩验证，也未逐条验证所有任务、对话和版面。少数原游戏文字键对应多个不同原文，普通字符串也可能无法由语言资源覆盖，因此仍会有英文遗漏。其他游戏版本的兼容性未知。

## 已有任务仍显示英文

游戏会把部分任务文字缓存到存档中，仅安装资源补丁不一定刷新已接取任务的全部文本。可以先查看新接取的任务。本公开包不包含任何玩家存档，也不会自动修改你的存档；不要为了刷新文字删除自己的进度。

## 崩溃排查与复测

曾收到击败费尔雷克后自动进入对话动画时崩溃的反馈，记录中出现运行约 453 秒后的访问冲突。相关原始资源容器的完整性检查通过。

使用 **v0.1.0-draft 旧补丁和独立存档副本**复测时，玩家确认已正常进入并完成首领战后动画，没有生成新崩溃记录。**未确认偶发崩溃根因，本版不宣称修复崩溃。** 此次没有更改驱动、系统或画面设置。

此前启动排查中，备份并移走下列旧着色器缓存后曾成功进入主菜单及存档一次：

```text
%LOCALAPPDATA%\Carnal_Instinct_UE5\Saved\Carnal_Instinct_UE5_PCD3D_SM6.upipelinecache
```

这不足以证明缓存是根因，也不作为本版的通用修复建议。保留自己的 `SaveGames` 文件夹及游戏本体文件；如提交崩溃反馈，请说明游戏版本、触发操作及报错内容。

## 卸载

退出游戏，将安装时添加的四个 `Independent` 文件移出 `Paks` 文件夹即可。不要移除原始 `pakchunk0`、`global` 等游戏文件。若此前通过其他方式修改过存档中的任务文字，卸载资源补丁不会还原这些存档文字。

## 校对与贡献

- [translations/reviewed.json](translations/reviewed.json)：合并既有校对和本次 6.1 sol 校订后的英文与中文词条。
- [translations/localization.jsonl](translations/localization.jsonl)：本版语言资源的原文、译文、键和翻译方式。
- [translations/quests.jsonl](translations/quests.jsonl)：任务显示文字的独立译文。
- [manifest.json](manifest.json)：本版覆盖统计及验证范围。

欢迎通过 Issue 或 Pull Request 提交英文原文、建议译文和出现位置。修改译文文件不会直接改变已打包的二进制补丁，后续版本需要重新构建。

仓库不包含游戏本体、个人存档、解密密钥、翻译模型或第三方旧汉化包。游戏原始内容的权利归原权利人所有，本项目与官方无关。

## 使用的工具

- [Argos Translate](https://github.com/argosopentech/argos-translate) / [CTranslate2](https://github.com/OpenNMT/CTranslate2)：本地英中翻译。
- GPT-6.1-sol 子代理：本次部分词条及对话校订；整个翻译流程并非纯离线。
- [repak](https://github.com/trumank/repak)、[retoc](https://github.com/trumank/retoc)：资源打包与转换。
- [UnrealLocres](https://github.com/akintos/UnrealLocres)：语言资源写入。

这些工具和模型没有随补丁分发。
