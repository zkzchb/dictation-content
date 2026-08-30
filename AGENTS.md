# Dictation content repository guidance

This repository publishes independently authored Dictation content packs and
recordings under CC BY-NC 4.0. It does not contain application code, runtime
databases, learning history, deployment configuration, or unpublished recording
ledgers.

Before publishing a pack change, run the validator and audio inventory from the
compatible `dictation` program revision. Update every affected structured-file
hash, `tts.sha256`, the dataset digest, and the pack version in the same change.

## Code Review Rules

### Preserve stable identities

- Flag deletion, reassignment, or semantic reuse of a published pack ID,
  lesson ID, or knowledge-point ID. Additive content may keep the existing pack;
  destructive or incompatible changes require a new pack identity and explicit
  migration guidance.

### Keep manifests and audio verifiable

- Flag any JSON, recording, checksum, count, or version change that leaves
  `dataset.json`, `studio_manifest.json`, `tts.sha256`, or the dataset digest out
  of sync. A release is valid only when the complete pack and every declared MP3
  pass the program validator.

### Enforce rights and privacy boundaries

- Flag third-party course materials, recordings, images, or source material without explicit
  provenance and redistribution terms. Never accept student/teacher data,
  credentials, deployment identifiers, learning history, runtime recording
  ledgers, or unpublished recordings into a public pack or verification log.
