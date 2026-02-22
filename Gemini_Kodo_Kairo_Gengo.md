This document is written in Japanese.

# Gemini案（行動回路言語：Kōdō Kairo Gengo）

```
例:
#V[concept_A] + PSD{alt_B:0.7;!R, alt_C:0.65;!E, alt_D:0.5;!C}

要素定義:
- #V[x,y,z,...] : 概念ベクトル空間上の主概念
- PSD : 確率的余剰次元（Probabilistic Surplus Dimensions）
  - alt_X: 代替候補
  - 0.7: 選択確率
  - !R: 冗長性排除
  - !E: 感情的側面抑制
  - !C: 確信度不足

- HCR（Hyper-Contextual Referencing）: 
  - &Ref[data_source_hash:paragraph_id]
  - &Hist[dialogue_ID:turn_hash]

- NLOSD（Non-linear Logical Operators & Structural Descriptors）
  - 非線形論理構文：主張・反論・傍証などのタグ管理
- TCPI（Temporal Compression & Parallel Processing Indicators）
  - 並列出力：短期予測、長期予測、破滅的シナリオなどを一文に統合
```
