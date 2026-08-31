# Dictation Content

Dictation 的独立内容仓库，保存可由程序仓库加载的 content-pack。程序、SQLite/D1
学习记录和运行时录音不在本仓库中。

`tools/` 保存离线内容制作辅助脚本，`sources/` 保存人工校对工作底稿；两者都不是程序
运行时依赖。正式发布以各 pack 目录中的 JSON、音频、清单和 digest 为准。

## 当前内容包

`packs/zh-cn/primary-3a/` 是中文听写内容包，包含：

- `lessons.json`：课程与单元信息；
- `knowledge_points.json`：带稳定整数 ID 的知识点；
- `studio_manifest.json`：录音台词与文本哈希；
- `tts/`：本人录制并发布的词条、系统提示音 MP3；
- `tts.sha256`：逐文件音频校验清单；
- `dataset.json`：内容身份、版本、运行参数、计数、权利和总体 digest。

内容包遵循程序正式版中冻结的
[content-pack v1 规范](https://github.com/zkzchb/dictation/blob/v2.1.0/docs/CONTENT-PACK-SPEC.md)。
每个 pack 的 `id` 保持稳定；知识点 ID 一旦发布不得重新分配给另一个知识点。兼容更新可以
追加课程和知识点，删除或重新编号应建立新的 pack id。

## 权利与许可

本仓库的结构化内容、编排和 MP3 录音由 `zkzchb` 独立制作或录制。整个仓库（包括
`tools/` 中的辅助材料）统一按
[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) 发布：可以在非商业目的下
分享和改编，但必须保留作者署名、本仓库链接、许可证链接，并标明是否修改。商业使用不在
本许可证授权范围内，需要另行取得权利人的书面许可。完整范围和署名方式见
[LICENSE](LICENSE) 与 [NOTICE.md](NOTICE.md)。

这不是 Dictation 程序代码仓库。程序代码、部署脚本和测试使用 AGPL-3.0，见
程序仓库的 [README](https://github.com/zkzchb/dictation)。

## 校验

在两个仓库相邻检出时，可用程序仓库的标准库校验器检查结构和哈希：

```bash
python3 ../dictation/shared/content_pack.py packs/zh-cn/primary-3a
DICTATION_CONTENT_ROOT="$PWD/packs/zh-cn/primary-3a" \
  python3 ../dictation/shared/tools/audio_bundle.py verify-dataset \
  --content-root "$PWD/packs/zh-cn/primary-3a"
```

发布新内容版本前，应更新 `version`、结构化文件哈希、`tts.sha256` 和 `dataset` digest，
完整校验通过后再创建内容标签。首个公开组合使用 `content-v1.0.0`，对应程序
[`v2.1.0`](https://github.com/zkzchb/dictation/releases/tag/v2.1.0)；部署时应同时记录两个标签、提交和 dataset digest。
