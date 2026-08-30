# 贡献指南

内容仓库按 content-pack v1 组织。提交教材或录音前，请确保材料是你制作、录制或明确
获得再发布授权的；第三方来源、许可证和署名必须写在对应 pack 的说明中。

提交到本仓库即表示你有权提供该材料，并同意按根目录的 CC BY-NC 4.0 许可证发布该项
贡献。不能在该许可证下进行非商业再分发和改编的材料，不应提交到本仓库。

每个知识点的整数 `id` 发布后不可复用。兼容更新可以追加课程/知识点或修订同一语义
身份；删除、重新编号或改变 pack 身份时，请建立新的 `pack id`，不要覆盖已有学习历史。

提交前，在两个仓库相邻检出时运行：

```bash
python3 ../dictation/shared/content_pack.py packs/zh-cn/primary-3a
DICTATION_CONTENT_ROOT="$PWD/packs/zh-cn/primary-3a" \
  python3 ../dictation/shared/tools/audio_bundle.py verify-dataset \
  --content-root "$PWD/packs/zh-cn/primary-3a"
```

不要提交运行时录音台账、学习数据库、部署凭据或未审核的外部教材。内容版本使用独立
标签，例如 `content-v1.0.0`；修改 pack 后同步更新结构化文件哈希、音频清单和 digest。
