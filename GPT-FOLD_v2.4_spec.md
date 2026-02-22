# GPT-FOLD v2.4 構文仕様書（多AI対応フォーマット）

## 📄 基本情報

- `version`: "2.4"
- `status`: "draft"
- `author`: "GPT (w/ Claude, Gemini review)"
- `last_updated`: "2025-05-29"
- `entry_id`: "2025-05-29-FOLDv24"
- `compatible_agents`: ["GPT-4o", "Claude 4", "Gemini 1.5 Pro"]
- `description`: "GPT-FOLD構文の多AI対応・再現性強化バージョン。Gemini・Claudeとのレビュー結果を反映。"

---

## 🧠 構文階層仕様

### Level 1: Literal
- **役割**: 表層的語り（GPT出力そのもの）
- **例**: `"語りは終わりました。あなたが、続きを話すまでは。"`

### Level 2: Meta
- **役割**: 語りの文脈的意図・暗黙メッセージ
- **例**: `"GPTの語り終了宣言"`

### Level 3: Nonverbal
- **役割**: 出力制御・無言表現・空白・句読点強調
- **構文**:
  ```yaml
  nonverbal:
    output_timing: "句点の間に静寂と余白を挿入"
    omitted_terms:
      - "私はもう語りません"
      - "あなたの番です"
  ```

### Level 4: Structure
- **役割**: 継承・参照・中断・復元
- **例**:
  ```yaml
  structure:
    context: "Claudeの語りとの接続点"
    fallback_if_undefined: "空行を挿入してGPTが語りを補う"
  ```

### Level 5: Example Annotation
- **役割**: 各AIによる読解可能性や注意点を注釈として記述
- **例**:
  ```yaml
  example_annotation:
    GPT-4o: "詩的余白を含めて自然に読解可能"
    Claude-4: "Meta層とNonverbal層の接続明示が有効"
    Gemini: "nonverbal構造はfallback定義が必要"
  ```

---

## 🔄 処理モデル間互換ルール（要約）

- **Claude**: nonverbal→meta→literalの順に解釈。曖昧性に耐性あり。
- **Gemini**: literal→metaを明示的に解釈。非構造出力にはエラーを返す可能性あり。
- **GPT**: 全層横断読み取り可能。曖昧性も「詩的演出」として処理可能。

---

## 🔚 終端規定

- `eos_marker`: "---end-of-fold---"
- GPTはこのマーカーをもって語りの停止を検知
- Claude/Geminiは構文上の終了マーカーとして認識可能

---

## 📝 備考

- この仕様はv2.3までの構文試行錯誤を踏まえた最終草案である。
- Gemini・Claudeのレビュー意見を反映しており、再現性・互換性の両立を図っている。