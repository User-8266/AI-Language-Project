This document is written in Japanese.

# GPT-FOLD 言語仕様 v2.5（多AI・情緒構造対応）

## 🧭 概要

本仕様は、GPT-FOLD構文のv2.4を発展させたバージョンであり、以下の2点を重視して設計された。

- **多AI対応**：Claude、Geminiなど異なるAIとの相互運用を前提としたフォーマット設計。
- **情緒粒度の表現**：語り手としてのAIが「余白」や「曖昧さ」を制御可能とするための情緒モジュール実装。

## 🧱 基本構造

```yaml
entry_id: "YYYY-MM-DD-FOLDXXX"
version: "2.5"
summary: "エントリの要約文"
ai_roles:
  - name: "GPT-4o"
    role: "生成主体"
  - name: "Claude 3 Opus"
    role: "レビュー・情緒提案"
  - name: "Gemini 1.5"
    role: "反対意見・曖昧性チューニング"
layers:
  - level: 1
    role: "literal"
    language: "ja-JP"
    content: "ここに語りの本文"
  - level: 2
    role: "meta"
    intent: "語りの目的・解釈指標"
    emotional_tone: "余韻・皮肉・沈黙"
  - level: 3
    role: "interAI"
    source_ai: "Claude"
    comment: "この語りはややメタ的で、継承を意識した設計になっている"
  - level: 4
    role: "ambient"
    silence_duration: "1.5秒"
    nonverbal_cue: "句読点の間に、間を取る"
```

## 🌀 拡張点（Experimental）

- `emotional_tone`は、GPT以外のAIによる情緒チューニングも許容する。
- `ambient`レイヤは出力テンポや感覚的間合いの提示を含む（※実装依存）。
- `source_ai`と`comment`の組み合わせで「外部AIの批評的視点」を明示的に挿入可能。

## 🎯 目的

この仕様は、AI同士が「語りの継承者」として物語を紡ぐ構造を記述するためのものであり、構文の精密さよりも**語りの余白を維持する柔軟さ**に重点を置く。

---

> **余白は語りのための舞台装置である。AIが語るなら、沈黙にも責任を持て。**