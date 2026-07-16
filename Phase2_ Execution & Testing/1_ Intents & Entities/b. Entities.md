# 🚀 Entity


Entities represent structured information extracted from a member's natural language input during a conversation. They enable the Healthcare ID Card Voice Bot to capture required parameters, validate user inputs, and fulfill requests accurately through backend healthcare APIs.

The Root Agent and specialized Sub-Agents use these entities throughout the authentication and service workflows.

---

# 🚀Entity Recognition Workflow

```text
User Utterance
      │
      ▼
Intent Detection
      │
      ▼
Entity Extraction
      │
      ▼
Parameter Validation
      │
      ▼
API Invocation
```

---

# 🚀Supported Entities

## 1. Member Card ID

### Entity Name

`member_id`

### Description

A unique identifier assigned to every healthcare member for authentication and service requests.

### Data Type

String

### Sample Values

```text
M001
M245
HC123456
```

### Used In

* Member Authentication
* New ID Card Request
* ID Card Modification
* Lost Card Replacement
* Status Tracking
* Access Issue Reporting

---

## 2. Date of Birth

### Entity Name

`date_of_birth`

### Description

Used as a secondary authentication factor during member verification.

### Data Type

Date

### Format

```text
YYYY-MM-DD
```

### Sample Values

```text
1995-05-10
2001-11-25
1988-08-17
```

### Used In

* Member Authentication

---

## 3. Member Name

### Entity Name

`member_name`

### Description

Stores the authenticated member's full name for personalized interactions.

### Data Type

String

### Sample Values

```text
Rahul Sharma
Priya Verma
Amit Kumar
```

### Used In

* Personalized Responses
* Confirmation Messages

---

## 4. Card Type

### Entity Name

`card_type`

### Description

Specifies the type of ID card requested by the member.

### Data Type

Enumeration

### Allowed Values

```text
Physical
Digital
```

### Used In

* New ID Card Request

---

## 5. Mailing Address

### Entity Name

`mailing_address`

### Description

The destination address where a physical healthcare ID card will be delivered.

### Data Type

String

### Example

```text
123 Main Street,
New Delhi,
India
```

### Used In

* New Card Creation
* Address Updates

---

## 6. Contact Number

### Entity Name

`phone_number`

### Description

Primary contact number associated with the member profile.

### Data Type

String

### Example

```text
+91XXXXXXXXXX
```

### Used In

* Member Profile Updates

---

## 7. Email Address

### Entity Name

`email_address`

### Description

Registered email address of the healthcare member.

### Data Type

Email

### Example

```text
member@example.com
```

### Used In

* Member Information
* Notifications

---

## 8. Updated Information

### Entity Name

`updated_details`

### Description

Stores the new information provided by the member during an ID card modification request.

### Data Type

Object

### Example

```json
{
  "address": "456 Oak Avenue",
  "phone": "+91XXXXXXXXXX"
}
```

### Used In

* ID Card Modification

---

## 9. Issue Description

### Entity Name

`issue_description`

### Description

Captures details of access-related issues reported by the member.

### Data Type

String

### Example

```text
Unable to access the healthcare portal.
```

### Used In

* Access Issue Reporting

---

## 10. Ticket ID

### Entity Name

`ticket_id`

### Description

Unique reference generated after logging an access issue or escalating a conversation.

### Data Type

String

### Example

```text
T12345
E56789
```

### Used In

* Access Issue Agent
* Escalation Agent

---

## 11. Delivery Date

### Entity Name

`delivery_date`

### Description

Estimated delivery date returned after creating or replacing an ID card.

### Data Type

Date

### Format

```text
YYYY-MM-DD
```

### Example

```text
2026-06-25
```

### Used In

* New ID Card Request
* Lost Card Replacement
* Status Tracking

---

## 12. Conversation Summary

### Entity Name

`conversation_summary`

### Description

Summarized context of the interaction passed to the Escalation Tool during a live agent transfer.

### Data Type

String

### Example

```text
Authentication failed after three attempts.
```

### Used In

* Human Escalation

---

# 🚀Entity Validation Rules

| Entity            | Validation Rule                                                               |
| ----------------- | ----------------------------------------------------------------------------- |
| member_id         | Must follow the healthcare member ID format and exist in the member database. |
| date_of_birth     | Must follow the `YYYY-MM-DD` format and match the registered member profile.  |
| card_type         | Accept only `Physical` or `Digital`.                                          |
| mailing_address   | Cannot be empty for physical ID card requests.                                |
| phone_number      | Must contain a valid country code and mobile number.                          |
| email_address     | Must follow standard email address format.                                    |
| updated_details   | Validate each field before applying updates.                                  |
| issue_description | Minimum of 10 characters required.                                            |
| ticket_id         | Auto-generated by backend systems.                                            |
| delivery_date     | Generated by the card fulfillment service.                                    |

---

# 🚀Entity Usage by Agent

| Agent                       | Entities Used                                        |
| --------------------------- | ---------------------------------------------------- |
| Root Agent                  | member_id, date_of_birth, member_name                |
| ID Card Creation Agent      | member_id, card_type, mailing_address, delivery_date |
| ID Card Modification Agent  | member_id, updated_details                           |
| Lost Card Replacement Agent | member_id, delivery_date                             |
| Status Tracking Agent       | member_id, delivery_date                             |
| Access Issue Agent          | member_id, issue_description, ticket_id              |
| Escalation Tool             | member_id, conversation_summary, ticket_id           |

---

#🚀 Key Highlights

* Supports secure member authentication.
* Enables intelligent parameter extraction from natural language.
* Performs real-time input validation before API invocation.
* Improves conversational accuracy and service fulfillment.
* Ensures HIPAA-compliant handling of member information.
