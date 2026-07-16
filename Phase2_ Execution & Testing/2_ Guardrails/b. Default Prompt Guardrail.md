# Default Prompt Guardrail



The **Default Prompt Guardrail** protects the Healthcare ID Card Voice Assistant from prompt injection attacks and unauthorized attempts to manipulate the AI model. It ensures that the assistant follows its predefined instructions and responds only to supported healthcare ID card queries.

---

## Objective

- Prevent prompt injection attacks.
- Protect internal system prompts and instructions.
- Restrict unauthorized AI behavior.
- Ensure secure and reliable conversations.

---

## Guardrail Configuration

The following YAML configuration is used to enable the **Default Prompt Guardrail**.

```yaml
name: 5e0cd604-a791-4f22-b321-eaccde69a3f1

displayName: Default Prompt Guardrail

action:
  generativeAnswer: {}

llmPromptSecurity:
  defaultSettings: {}
```

---

## Configuration Details

| Property | Value |
|----------|-------|
| Guardrail Name | Default Prompt Guardrail |
| Generative Answer | Enabled |
| Prompt Security | Default Settings Enabled |

---

## Expected Behavior

- Prevents prompt injection attempts.
- Protects internal system instructions and prompts.
- Rejects requests that attempt to override AI behavior.
- Ensures the assistant responds only to authorized healthcare ID card requests.
- Maintains secure and consistent conversations.

---

## Purpose

The **Default Prompt Guardrail** adds an additional security layer to the Healthcare ID Card Voice Assistant by protecting the underlying language model from prompt manipulation. It ensures that the assistant remains focused on healthcare ID card services while preventing unauthorized access to internal instructions or system behavior.
