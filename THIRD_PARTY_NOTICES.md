# 第三方来源与许可声明

PureFount 的词典数据是经合并、去重、拼音转换和权重整理后形成的集合，包含或派生自以下来源。第三方内容仍归原作者及贡献者所有，并遵循各自的许可或使用条款。

## CustomPinyinDictionary

- 项目：https://github.com/wuhgit/CustomPinyinDictionary
- 用途：日常输入场景的大型拼音词库来源之一
- 说明：上游 README 还列出了 FREEMDICT、中国行政区划数据、公共机构数据和第三方输入法词库等多种来源。上游仓库当前未提供统一的顶层许可证，因此 PureFount 的 MIT License 不适用于这些数据。再分发或商业使用前，请自行核对上游项目及其各数据来源的授权条件。

## THUOCL

- 项目：https://github.com/thunlp/THUOCL
- 作者：清华大学自然语言处理与社会人文计算实验室（THUNLP）及贡献者
- 许可证：MIT License
- 用途：IT、财经、成语、地名、诗词、医学、法律等分类词表和词频数据

Copyright (c) 2018 THUNLP

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

THUOCL 建议在论文或科研成果中注明使用了清华大学开放中文词库，引用格式请参阅其上游 README。

## Rime Essay（八股文）

- 项目：https://github.com/rime/rime-essay
- 用途：Rime 预设词汇与语言模型数据来源之一
- 许可证：GNU Lesser General Public License v3.0（LGPL-3.0）
- 许可证原文：https://github.com/rime/rime-essay/blob/master/LICENSE

词典数据中源自或派生自 Rime Essay 的部分继续遵循 LGPL-3.0；PureFount 的顶层 MIT License 不会覆盖该部分。

## jieba

- 项目：https://github.com/fxsjy/jieba
- 作者：Sun Junyi 及贡献者
- 用途：中文分词高频词库来源之一
- 许可证：MIT License
- 许可证原文：https://github.com/fxsjy/jieba/blob/master/LICENSE

Copyright (c) 2013 Sun Junyi

jieba 的完整 MIT 许可文本可通过上方链接查看。

## 许可边界

仓库顶层 `LICENSE` 仅适用于 PureFount 自有的说明文档、元数据和项目维护内容。`purefount.dict.yaml` 与 `purefount_traditional.dict.yaml` 是多来源数据集合，使用者应同时遵守适用于相应数据的上游条款。本文件不是法律意见；如果你的使用场景涉及再分发、嵌入商业产品或训练数据合规，请进一步核对各上游项目的最新许可。
