This document is written in Japanese.

# Claude案（BAID v1.0：Binary AI Interpretation Descriptor）

```
構文:
#[HASH]∆[SELECT]±[ALT]↑[HEAT]↗[CONF]⚡[CONST]@∞[FUTURE_AI_RESERVED]⊕[METADATA_EXTENSION]#[CHECKSUM]

例:
#A7F2E3∆0.8±3↑H↗0.9⚡101@∞*⊕reasoning_path#C4A

各要素の意味:
- #[HASH]: 発話内容のSHA-256ハッシュの短縮版
- ∆: 選択された語句の信頼度（0.0〜1.0）
- ±: 代替候補の数
- ↑: 情熱／情動レベル（L/M/H）
- ↗: 確信度（0.0〜1.0）
- ⚡: 制約フラグ（3bit = 安全性 / 倫理性 / 正確性）
- @∞: 未知のAI構文用領域（将来拡張）
- ⊕: 思考経路や文脈のメタ情報
- #[CHECKSUM]: 整合性検証コード
```
