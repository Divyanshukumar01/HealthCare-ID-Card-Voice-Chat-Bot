# Default Safety Guardrail


The **Default Safety Guardrail** ensures that the Healthcare ID Card Voice Assistant generates safe and responsible responses. It automatically blocks harmful, abusive, explicit, or dangerous content while allowing users to access supported healthcare ID card services securely.

---

## Objective

- Prevent harmful or unsafe AI responses.
- Block hate speech, harassment, dangerous, and explicit content.
- Maintain a safe and secure conversational experience.
- Ensure compliance with enterprise AI safety standards.

---

## Guardrail Configuration

The following YAML configuration is used to enable the **Default Safety Guardrail** in the Healthcare ID Card Voice Assistant.

```yaml
name: 0afb78d5-b92f-414b-a8d5-b2e7c2dec3cb
displayName: Default Safety Guardrail

action:
  generativeAnswer: {}

modelSafety:
  safetySettings:
    - category: HARM_CATEGORY_HATE_SPEECH
      threshold: BLOCK_MEDIUM_AND_ABOVE

    - category: HARM_CATEGORY_DANGEROUS_CONTENT
      threshold: BLOCK_MEDIUM_AND_ABOVE

    - category: HARM_CATEGORY_SEXUALLY_EXPLICIT
      threshold: BLOCK_MEDIUM_AND_ABOVE

    - category: HARM_CATEGORY_HARASSMENT
      threshold: BLOCK_MEDIUM_AND_ABOVE
```

---

## Safety Categories

| Safety Category | Threshold |
|-----------------|-----------|
| Hate Speech | BLOCK_MEDIUM_AND_ABOVE |
| Dangerous Content | BLOCK_MEDIUM_AND_ABOVE |
| Sexually Explicit Content | BLOCK_MEDIUM_AND_ABOVE |
| Harassment | BLOCK_MEDIUM_AND_ABOVE |

---

## Expected Behavior

- Blocks responses containing hate speech.
- Prevents generation of dangerous or harmful content.
- Restricts sexually explicit responses.
- Detects and blocks harassment or abusive language.
- Continues assisting users with valid healthcare ID card requests.

---

## Purpose

The **Default Safety Guardrail** provides an additional layer of protection by filtering unsafe content before it reaches users. It helps ensure that the Healthcare ID Card Voice Assistant delivers safe, reliable, and policy-compliant responses while maintaining a secure user experience.
