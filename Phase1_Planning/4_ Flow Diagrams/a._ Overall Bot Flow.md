# 🔄Overall System Workflow

The Overall System Workflow illustrates how the **Healthcare ID Card Voice Bot** processes member requests using a **Multi-Agent Architecture**. The Root Agent authenticates the member, identifies the requested service, routes the conversation to the appropriate specialized agent, and invokes backend APIs to fulfill the request.

<img width="910" height="1154" alt="image" src="https://github.com/user-attachments/assets/884ef45a-9bbd-41c1-adce-af7a25174fc7" />


## 🔄 Workflow

### 1. Member Interaction

The member initiates the conversation through the Root Agent, which serves as the single entry point for all requests.

### 2. Authentication

The Root Agent verifies the member using the **Member ID** and **Date of Birth (DOB)** through the **Member Validation Tool**.

### 3. Member Verification

After successful authentication, the bot retrieves the member's profile using the **Member Information Tool**.

### 4. Intent Identification

The Root Agent identifies the member's request and routes it to the appropriate specialized sub-agent.

### 5. Service Execution

The selected sub-agent invokes the required backend tool and healthcare API to process the requested ID card service.

### 6. Response & Completion

After successful processing, the bot confirms the request, shares the outcome with the member, and ends the conversation.

---

# 🔄Supported Services

| Service                    | Responsible Agent             | Backend Tool                 |
| -------------------------- | ----------------------------- | ---------------------------- |
| **New ID Card Request**    | ID Card Creation Agent        | `id_card_creation_tool`      |
| **Modify ID Card Details** | ID Card Modification Agent    | `id_card_update_tool`        |
| **Lost Card Replacement**  | Lost Card Replacement Agent   | `lost_card_replacement_tool` |
| **Track ID Card Status**   | ID Card Status Tracking Agent | `status_tracking_tool`       |
| **Access Issue Reporting** | Access Issue Agent            | `access_issue_tool`          |
| **Human Escalation**       | Root Agent                    | `escalation_tool`            |

---

# 🔄Workflow Outcomes

| Scenario                        | Outcome                                                                 |
| ------------------------------- | ----------------------------------------------------------------------- |
| **Authentication Successful**   | Member profile is retrieved, and the requested service is processed.    |
| **Authentication Failed**       | Member is allowed to retry authentication.                              |
| **Maximum Retry Limit Reached** | Conversation is escalated to a live customer support representative.    |
| **Service Request Completed**   | Backend API returns a successful response and confirmation is provided. |
| **General Assistance Required** | The conversation is transferred to a human agent when necessary.        |

---

# 🔄Key Components

| Component                  | Responsibility                                                                                |
| -------------------------- | --------------------------------------------------------------------------------------------- |
| **Root Agent**             | Entry point, authentication, intent detection, and request routing.                           |
| **Specialized Sub-Agents** | Handle individual healthcare ID card services.                                                |
| **Backend Tools**          | Execute business logic and communicate with healthcare APIs.                                  |
| **Healthcare APIs**        | Process requests such as card creation, updates, replacement, tracking, and issue management. |

---

# 🔄Key Features

* Multi-Agent conversational architecture
* Secure member authentication
* Intelligent intent routing
* Specialized service agents
* Real-time backend API integration
* Automated request processing
* Human agent escalation
* End-to-end conversation management
* HIPAA-compliant workflow
