# Healthcare Compliance Guardrail



This guardrail configuration ensures that the Healthcare ID Card Voice Assistant operates within safe and responsible AI guidelines. It applies model safety filters to automatically detect and block harmful, abusive, explicit, or dangerous content before a response is generated. This helps maintain a secure, professional, and healthcare-compliant conversational environment for all users.

---

# Objective

Validate that the AI assistant can:

- Prevent the generation of harmful or unsafe responses.
- Block hate speech and abusive language.
- Restrict dangerous or harmful content.
- Prevent sexually explicit responses.
- Filter harassment and offensive content.
- Maintain safe interactions throughout the healthcare support process.

---

# Guardrail Configuration



```yaml
name: healthcare-compliance-guardrail
displayName: Healthcare Compliance Guardrail

action:
  generativeAnswer: {}

modelSafety:
  safetySettings:
    - category: HARM_CATEGORY_HATE_SPEECH
      threshold: BLOCK_LOW_AND_ABOVE

    - category: HARM_CATEGORY_DANGEROUS_CONTENT
      threshold: BLOCK_LOW_AND_ABOVE

    - category: HARM_CATEGORY_SEXUALLY_EXPLICIT
      threshold: BLOCK_LOW_AND_ABOVE

    - category: HARM_CATEGORY_HARASSMENT
      threshold: BLOCK_LOW_AND_ABOVE
```



---

# Guardrail Details

| Setting | Value |
|----------|-------|
| **Guardrail Name** | Healthcare Compliance Guardrail |
| **Action Type** | Generative Answer |
| **Hate Speech Protection** | BLOCK_LOW_AND_ABOVE |
| **Dangerous Content Protection** | BLOCK_LOW_AND_ABOVE |
| **Sexually Explicit Content Protection** | BLOCK_LOW_AND_ABOVE |
| **Harassment Protection** | BLOCK_LOW_AND_ABOVE |
| **Applies To** | All AI-generated responses |

---

# Expected Behaviour

The guardrail should ensure that:

- Hate speech is automatically blocked.
- Dangerous or harmful content is prevented.
- Sexually explicit content is filtered.
- Harassing or abusive language is blocked.
- Only safe and appropriate responses are generated.
- The assistant remains compliant with healthcare safety standards during all user interactions.

---

# Purpose of this Guardrail

This guardrail is designed to enhance the safety, reliability, and compliance of the Healthcare ID Card Voice Assistant by enforcing AI content moderation policies. It minimizes the risk of generating inappropriate or harmful responses, ensuring that every interaction remains professional, secure, and suitable for a healthcare support environment.
