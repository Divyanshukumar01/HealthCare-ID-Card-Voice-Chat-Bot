# 🚀 Intent


The Healthcare ID Card Voice Bot leverages Natural Language Understanding (NLU) to identify the purpose of a member's request from natural language conversations. After successful authentication, the Root Agent analyzes the user's utterance, determines the appropriate intent, and routes the conversation to the corresponding specialized sub-agent for fulfillment.

Each intent represents a specific healthcare ID card service and is mapped to dedicated conversational workflows and backend APIs.

---

# 🚀 Intent Routing Architecture

```text
Member Call
      │
      ▼
 Root Agent
      │
      ▼
Authenticate Member
      │
      ▼
Intent Detection
      │
      ├──────────────► New ID Card Request
      ├──────────────► Modify ID Card Details
      ├──────────────► Replace Lost ID Card
      ├──────────────► Track ID Card Status
      ├──────────────► Report Access Issue
      └──────────────► Escalate to Live Agent
```

---

# 🚀Supported Intents

## 1. New ID Card Request

### Intent Name

`new_id_card_request`

### Description

Triggered when a member requests a new healthcare ID card, either in physical or digital format.

### Sample User Utterances

* I need a new ID card.
* Can I request a new member card?
* I want a digital ID card.
* Please issue me a healthcare ID card.

### Routed Agent

**ID Card Creation Agent**

### Backend Tool

`id_card_creation_tool`

### API Invoked

```text
create_id_card(member_id)
```

---

## 2. Modify ID Card Details

### Intent Name

`modify_id_card_details`

### Description

Triggered when a member wants to update personal information associated with their healthcare ID card.

### Sample User Utterances

* Change my address.
* Update my phone number.
* I want to modify my ID card details.
* My contact information has changed.

### Routed Agent

**ID Card Modification Agent**

### Backend Tool

`id_card_update_tool`

### API Invoked

```text
update_id_card_details(member_id, new_details)
```

---

## 3. Replace Lost ID Card

### Intent Name

`replace_lost_card`

### Description

Triggered when a member reports a lost, stolen, or damaged healthcare ID card and requests a replacement.

### Sample User Utterances

* I lost my ID card.
* My healthcare card was stolen.
* Replace my member card.
* I need a replacement card.

### Routed Agent

**Lost Card Replacement Agent**

### Backend Tool

`lost_card_replacement_tool`

### API Invoked

```text
replace_lost_card(member_id)
```

---

## 4. Track ID Card Status

### Intent Name

`track_card_status`

# Description:

Triggered when a member wants to know the current processing or delivery status of an ID card request.

# Sample User Utterances:

* Track my ID card.
* Where is my healthcare card?
* Has my ID card been shipped?
* Check my card status.

# Routed Agent:

**Status Tracking Agent**

# Backend Tool:

`status_tracking_tool`

# API Invoked:


track_id_card_status(member_id)


---

## 5. Report Access Issue

## Intent Name

`report_access_issue`

## Description

Triggered when a member experiences problems accessing healthcare services or encounters issues using their healthcare ID card.

## Sample User Utterances

* I cannot access my account.
* My ID card isn't working.
* I'm having access issues.
* My healthcare portal is not accessible.

## Routed Agent

**Access Issue Agent**

## Backend Tool

`access_issue_tool`

## API Invoked


raise_access_issue(member_id)


---

## 6. Human Agent Escalation

## Intent Name

`request_human_agent`

## Description

Triggered when a member explicitly requests assistance from a live representative or when automated processing cannot resolve the issue.

## Sample User Utterances

* I want to speak with an agent.
* Connect me to customer support.
* Transfer me to a representative.
* I need human assistance.

## Routed Agent

**Root Agent**

## Backend Tool

`escalation_tool`

## API Invoked

```text
escalate_to_agent(member_id, conversation_summary)
```

---

# Intent Detection Workflow

Every member interaction follows the same intent recognition process:

1. The Root Agent greets the member.
2. Member authentication is completed using the Member Card ID and Date of Birth.
3. The Root Agent analyzes the member's request using Natural Language Understanding (NLU).
4. The detected intent is matched with the corresponding business workflow.
5. The conversation is routed to the appropriate specialized sub-agent.
6. The selected sub-agent invokes the required backend API to fulfill the request.
7. A confirmation or status update is returned to the member.

---


# 🚀Intent-to-Agent Mapping

| **Intent**             | **Agent**                   | **Backend Tool**             |
| ---------------------- | --------------------------- | ---------------------------- |
| New ID Card Request    | ID Card Creation Agent      | `id_card_creation_tool`      |
| Modify ID Card Details | ID Card Modification Agent  | `id_card_update_tool`        |
| Replace Lost ID Card   | Lost Card Replacement Agent | `lost_card_replacement_tool` |
| Track ID Card Status   | Status Tracking Agent       | `status_tracking_tool`       |
| Report Access Issue    | Access Issue Agent          | `access_issue_tool`          |
| Human Agent Escalation | Root Agent                  | `escalation_tool`            |

---

# 🚀Key Features

* Intelligent Natural Language Understanding (NLU)
* Secure Member Authentication
* Dynamic Intent Recognition
* Multi-Agent Intent Routing
* Backend API Integration
* Context-Aware Conversations
* Human Agent Escalation
* HIPAA-Compliant Interaction Flow
