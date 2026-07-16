# 🔑Authentication & Security Flow

The Authentication & Security Flow verifies a member's identity before granting access to healthcare ID card services. The Root Agent authenticates users using their **Member ID** and **Date of Birth (DOB)** while enforcing security policies such as retry limits and escalation.

 <img width="975" height="781" alt="image" src="https://github.com/user-attachments/assets/b51fe338-ed75-40bc-8036-947457cd4973" />


## 🔑Authentication Workflow

1. **Member Authentication**
   The customer provides their Member ID and Date of Birth for identity verification.

2. **Identity Validation**
   The `validate_member()` API verifies the provided credentials against the member database.

3. **Successful Authentication**
   If validation succeeds, the member profile is retrieved and the conversation proceeds to the requested service.

4. **Failed Authentication**
   If validation fails, the customer is informed and prompted to re-enter their credentials.

5. **Retry Policy**
   The system allows a maximum of **three authentication attempts** before terminating automated verification.

6. **Human Escalation**
   If the retry limit is exceeded, the conversation and context are transferred to a live customer support representative.

---

## 🔑Security Checkpoints

| Security Check           | Description                                                                |
| ------------------------ | -------------------------------------------------------------------------- |
| **Member ID Validation** | Verifies that the Member ID exists in the healthcare system.               |
| **DOB Verification**     | Confirms the member's identity using the registered Date of Birth.         |
| **Retry Limit**          | Restricts authentication to three attempts to prevent unauthorized access. |
| **Context Transfer**     | Preserves conversation history during escalation to a human agent.         |

---

## 🔑Authentication Outcomes

| Result                        | Action                                                          |
| ----------------------------- | --------------------------------------------------------------- |
| **Authentication Successful** | Retrieve the member profile and continue the requested service. |
| **Authentication Failed**     | Notify the customer and allow another authentication attempt.   |
| **Maximum Retries Reached**   | Escalate the conversation to a live customer support agent.     |
