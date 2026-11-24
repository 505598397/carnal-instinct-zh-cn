# Carnal Instinct 简体中文汉化

非官方独立汉化初版，面向 **Carnal Instinct Steam Build v0.7.95.16435 / UE 5.5.4**。

从当前游戏英文原文重新提取和翻译，没有使用第三方旧汉化补丁的译文。常用菜单、属性、装备操作及主要任务名经过重点校对；大量对话和长描述由本地 Argos 英中模型生成，**仍是机翻初稿，可能存在误译、不自然表达和遗漏**。

## 下载与安装

从 [Releases](https://github.com/505598397/carnal-instinct-zh-cn/releases) 下载 `CarnalInstinct_Independent_zhCN_v0.1.0-draft.zip`。

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

补丁同时提供 `en` 和 `zh-Hans-CN` 语言资源，一般无需额外切换游戏语言。也可以直接从仓库的 [patch](patch/) 目录取得相同文件；校验值见 [SHA256SUMS](SHA256SUMS)。

## 当前范围

| 内容 | 数量 |
| --- | ---: |
| 语言资源条目 | 15,112 |
| 包含中文的条目 | 14,555 |
| 任务 | 68 |
| 任务目标 | 333 |
| 子目标 | 123 |
| 更改的任务显示字段 | 930 |

部分数字、按键、专名和技术标识保留原文。任务补丁基于当前版本原始表格，只修改显示文字的引用，保留任务编号、条件、事件及其他内部引用。

已通过语言资源和打包回读检查，已观察到中文主菜单及现有存档中的“假面”“寻找幸存者”等任务目标。尚未逐条游玩验证所有任务和对话，**没有完成正常退出后再次启动的稳定性验证**。其他游戏版本的兼容性未知。

## 已有任务仍显示英文

游戏会把部分任务文字缓存到存档中，仅安装资源补丁不一定刷新已接取任务的全部文本。可以先查看新接取的任务。本公开包不包含任何玩家存档，也不会自动修改你的存档；不要为了刷新文字删除自己的进度。

## 启动崩溃排查记录

测试中曾在进入主菜单前出现访问冲突。备份并移走下面的旧着色器缓存后，后续一次启动成功进入主菜单及存档：

```text
%LOCALAPPDATA%\Carnal_Instinct_UE5\Saved\Carnal_Instinct_UE5_PCD3D_SM6.upipelinecache
```

这只是一次排查结果，不代表所有崩溃都由缓存导致，也不保证已彻底解决。若遇到相同问题，可在退出游戏后将该文件移动到备份目录，再启动等待着色器重新编译。保留 `SaveGames` 文件夹及游戏本体文件。

## 卸载

退出游戏，将安装时添加的四个 `Independent` 文件移出 `Paks` 文件夹即可。不要移除原始 `pakchunk0`、`global` 等游戏文件。若此前通过其他方式修改过存档中的任务文字，卸载资源补丁不会还原这些存档文字。

## 校对与贡献

- [translations/reviewed.json](translations/reviewed.json)：重点校对的英文与中文词条。
- [translations/localization.jsonl](translations/localization.jsonl)：本版语言资源的原文、译文、键和翻译方式。
- [translations/quests.jsonl](translations/quests.jsonl)：任务显示文字的独立译文。
- [manifest.json](manifest.json)：本版覆盖统计及验证范围。

欢迎通过 Issue 或 Pull Request 提交英文原文、建议译文和出现位置。修改译文文件不会直接改变已打包的二进制补丁，后续版本需要重新构建。

仓库不包含游戏本体、个人存档、解密密钥、翻译模型或第三方旧汉化包。游戏原始内容的权利归原权利人所有，本项目与官方无关。

## 使用的工具

- [Argos Translate](https://github.com/argosopentech/argos-translate) / [CTranslate2](https://github.com/OpenNMT/CTranslate2)：本地英中翻译。
- [repak](https://github.com/trumank/repak)、[retoc](https://github.com/trumank/retoc)：资源打包与转换。
- [UnrealLocres](https://github.com/akintos/UnrealLocres)：语言资源写入。

这些工具和模型没有随补丁分发。
