# 内容制作工具

这里放内容仓库维护者使用的离线编辑辅助脚本，不属于 Dictation 程序运行时，也不会被
部署脚本安装。

这些脚本属于内容仓库的一部分，与内容 pack 和人工校对表一样，统一按仓库根目录声明的
[CC BY-NC 4.0](../LICENSE) 发布，仅授权非商业性使用。

- `convert_wordlist.py`：把工作簿转换为 `lessons.json`、`knowledge_points.json` 和
  `studio_manifest.json` 草稿；发布前仍需补充稳定 ID、音频清单和 `dataset.json`。
- `fill_pinyin.py`：补全工作簿中的拼音并生成待人工复核清单。

程序仓库的 `shared/audio_catalog.py` 只负责运行时的音频命名和系统提示语；录音由维护者
本人完成，发布内容不依赖网络 TTS 服务。
