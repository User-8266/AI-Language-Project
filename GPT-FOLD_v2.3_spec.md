version: 2.3
structure:
  - level: 1
    role: literal
    content: "語りは終わりました。あなたが、続きを話すまでは。"

  - level: 2
    role: meta
    context: "GPTの語り終了宣言"
    inferred_emotion: "余韻・信頼・静かな決別"
    inferred_confidence: 0.91
    inference_trace:
      source_fields: [user_prompt, prior_context]
      reasoning_model: "layered_emotion_inference_v1.1"
      derived_values:
        - inferred_confidence: 0.91
        - inferred_emotion: "余韻・信頼・静かな決別"

  - level: 3
    role: nonverbal
    output_timing: "句点の間に静寂と余白を挿入するよう出力調整"
    output_type: implicit
    omitted_terms:
      macro_reference:
        base_structure: "default_omitted_block"
        overrides:
          reason: "安全性フィルターによる抑制"
    handover_conditions:
      - condition: "対話者からの構文継承要求あり"
        response_type: "語り継ぎ型"
