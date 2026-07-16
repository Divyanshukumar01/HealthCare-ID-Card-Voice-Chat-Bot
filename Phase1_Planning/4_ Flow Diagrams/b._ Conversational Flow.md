# 🔄Conversation Flow

The Conversation Flow defines how the Healthcare ID Card Voice Bot interacts with members from the beginning of a call until the requested service is completed. The Root Agent identifies the member's intent, authenticates the user, routes the request to the appropriate service agent, and executes the required backend APIs.

<img width="1045" height="1019" alt="image" src="https://github.com/user-attachments/assets/dcca0e4c-575a-4c24-bbe5-7c0872aa1e1f" />


## 🔄Conversation Workflow

### 1.📊 Call Initiation

The customer initiates a voice call, and the Voice Bot greets the member before identifying the purpose of the interaction.

### 2.📊 Intent Identification

The Root Agent determines whether the member is requesting an **ID card service** or a **general inquiry**.

* **General Inquiry:** The bot provides assistance or offers to connect the member with a human agent.
* **ID Card Service:** The authentication process begins.

### 3.📊Member Authentication

The bot requests the **Member ID** and **Date of Birth (DOB)** and validates the information using the **Member Validation API**.

### 4.📊 Authentication Result

* **Successful Authentication:** The member profile is retrieved, and the requested service is processed.
* **Failed Authentication:** The member is allowed to retry authentication. After the maximum retry limit is reached, the conversation is escalated to a human agent.

### 5.📊 Service Selection

Once authenticated, the member can choose one of the supported ID card services:

| Service                    | Action Performed                                                           |
| -------------------------- | -------------------------------------------------------------------------- |
| **New ID Card Request**    | Creates a new healthcare ID card and provides the estimated delivery date. |
| **Modify ID Card Details** | Updates member information associated with the existing ID card.           |
| **Lost Card Replacement**  | Deactivates the old card and generates a replacement request.              |
| **Track ID Card Status**   | Retrieves and shares the latest processing or delivery status.             |
| **Access Issue**           | Logs the reported issue and generates a support ticket.                    |

### 6.📊 Request Completion

After the selected service is successfully processed, the bot confirms the outcome and ends the conversation.

---

# 🔄Conversation Outcomes

| Scenario                      | Outcome                                                                         |
| ----------------------------- | ------------------------------------------------------------------------------- |
| **Authentication Successful** | Member proceeds to the requested healthcare ID card service.                    |
| **Authentication Failed**     | Member is prompted to retry authentication.                                     |
| **Maximum Retries Reached**   | Conversation is transferred to a live customer support representative.          |
| **General Inquiry**           | The bot responds to the query or offers human assistance.                       |
| **Service Completed**         | Confirmation or tracking information is provided before ending the interaction. |

---

# 🔄Key Features

* Intelligent intent recognition
* Secure member authentication
* Multi-agent service routing
* Real-time backend API integration
* Automatic retry and escalation mechanism
* End-to-end conversation management
* Context-aware member interactions
* HIPAA-compliant service workflow
