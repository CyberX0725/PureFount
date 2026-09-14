# 璞源词库（PureFount）

> 汇字成泉，返璞成章。

PureFount 是一套与具体输入法皮肤、按键和候选栏配置无关的中文拼音词库。仓库只提供可复用的简体/繁体 Rime 词典，以及使用和授权所需的说明文件；每条数据均包含词条、完整拼音和权重。
## 配套项目推荐：Typure

如果你希望直接获得完整、简洁的中文输入体验，推荐使用 [泰璞输入法（Typure）](https://github.com/CyberX0725/Typure)。

Typure 是一款专注简洁体验的输入法项目，也是 PureFount 最初的应用与孵化项目。两者现在彼此解耦：

- **Typure** 提供完整的输入法程序、输入流程和交互体验，适合希望开箱使用的用户；
- **PureFount** 只维护通用词条、拼音和权重，适合 Rime 用户、输入法开发者和需要中文词频数据的项目。

PureFount 保持纯净、无方案绑定，Typure 则提供一套完整实现。欢迎访问 [CyberX0725/Typure](https://github.com/CyberX0725/Typure) 了解项目、试用输入法或参与开发。

## 内容

| 文件 | 词条数 | 格式 | 用途 |
| --- | ---: | --- | --- |
| `purefount.dict.yaml` | 1,539,229 | `词条<Tab>拼音<Tab>权重` | 简体中文词库 |
| `purefount_traditional.dict.yaml` | 1,539,229 | `词条<Tab>拼音<Tab>权重` | 繁体中文词库 |

仓库不包含输入方案、键位、标点、候选栏、主题、用户配置、OpenCC 运行文件或特定输入法安装包。你可以把 PureFount 接入自己的 Rime 方案，而不会覆盖原有输入法配置。

## 获取

```bash
git clone https://github.com/CyberX0725/PureFount.git
```

也可以只下载需要的 `.dict.yaml` 文件。

## 在 Rime 中使用

### 方法一：直接作为方案主词典

将选定的词典文件复制到 Rime 用户目录，然后在你自己的 `*.schema.yaml` 中引用它：

```yaml
translator:
  dictionary: purefount
```

繁体词库对应：

```yaml
translator:
  dictionary: purefount_traditional
```

保存后重新部署 Rime。

### 方法二：合并进你已有的词典

如果你想保留当前方案的主词典，可以在自己的聚合词典中通过 `import_tables` 引入 PureFount。下面以现有词典 `luna_pinyin` 为例：

```yaml
---
name: my_merged_dictionary
version: "1.0"
sort: by_weight
use_preset_vocabulary: false
import_tables:
  - luna_pinyin
  - purefount
...
```

再让自己的输入方案引用聚合词典：

```yaml
translator:
  dictionary: my_merged_dictionary
```

请同时把 `purefount.dict.yaml` 放在 Rime 用户目录，并重新部署。繁体版本只需把导入项替换为 `purefount_traditional`。

## 其他程序

词典正文位于 YAML 头部结束标记 `...` 之后，采用 UTF-8 编码，每行三列：

```text
词条<Tab>拼音<Tab>权重
```

不使用 Rime 的程序可以跳过头部，按制表符解析正文。权重为正整数，数值越大通常表示优先级越高。

## 数据质量

发布前已验证两份词典：

- 每份均为 1,539,229 条词条；
- 每条均恰好包含词条、拼音和整数权重三列；
- 不含空词条、空拼音或无法解析的权重；
- Rime 词典名称与文件名一致。

词库仍可能包含错词、歧义词、低频词、过时词或公开语料中的非规范表达。建议按自己的使用场景调整权重或维护过滤表。

## 来源与许可

PureFount 的说明文档和项目维护内容采用 [MIT License](LICENSE)。词典数据由多个上游公开词库和语料合并、转换而来，各部分仍遵循原始项目的许可或使用条款；顶层 MIT License 不会替代第三方条款。

来源、署名及许可证边界见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
