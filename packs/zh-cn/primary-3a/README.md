# 中文听写内容包：primary-3a

这是 Dictation 的独立内容包。结构化词条、内容编排和 `tts/` 下的 MP3 录音由内容仓库
维护者独立制作或本人录制，并按 CC BY-NC 4.0 发布，仅授权署名后的非商业分享与改编；
`tts` 是兼容程序接口的目录名，不表示本版本运行时会调用第三方 TTS。

## 内容

- `lessons.json`：43 门课程（42 门可选课程和 1 个冷启动池）；
- `knowledge_points.json`：814 条知识点；
- `studio_manifest.json`：869 个唯一录音词条；
- `tts/w/`：869 个词条 MP3；
- `tts/sys/`：25 个系统提示音 MP3；
- `tts.sha256`：全部标准音频的逐文件校验值；
- `dataset.json`：内容身份、版本、运行参数、数量、权利和总体校验值。

## 不可变边界

这里不能存放学习历史或录音/质检台账。V2 的运行时会把内容音频复制到独立状态目录，
用户新增的未发布录音不会自动进入本仓库。要更新内容包，必须重新生成 `dataset.json`
与 `tts.sha256`，并通过：

```bash
python3 ../dictation/shared/tools/audio_bundle.py verify-dataset \
  --content-root packs/zh-cn/primary-3a
```

未来教材使用同级目录，例如 `packs/zh-cn/primary-3b`、`packs/zh-cn/primary-4a` 或
`packs/en/...`，不通过长期 Git 分支区分语言。

内容许可、署名和音频权利见仓库根目录 [NOTICE.md](../../../NOTICE.md) 与
[LICENSE](../../../LICENSE)。
