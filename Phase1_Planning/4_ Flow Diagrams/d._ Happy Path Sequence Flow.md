# 🤖Happy Path Sequence Flow

The Happy Path Sequence Flow illustrates the successful interaction between the **Customer**, **Healthcare ID Card Voice Bot**, and **Backend APIs** during a new ID card request. It demonstrates how the bot authenticates the member, collects the required information, invokes the appropriate API, and confirms the successful completion of the request.

<img width="975" height="650" alt="image" src="https://github.com/user-attachments/assets/26db66d6-89b9-4120-bfe0-68e2ccd52205" />



## 🤖Sequence Workflow

### 1. Request Initiation

The customer initiates the conversation by requesting a new healthcare ID card.

### 2. Member Authentication

The bot requests the **Member ID** and **Date of Birth (DOB)** and validates the member using the **Member Validation API**.

### 3. Card Type Selection

After successful authentication, the bot asks the customer to choose between a **Physical** or **Digital** ID card.

### 4. API Processing

The bot invokes the **create_id_card()** API to submit the new ID card request based on the customer's selection.

### 5. Request Confirmation

The backend returns a successful response with the estimated delivery date, and the bot confirms the request before ending the conversation.

---

# 🤖Sequence Summary

| Step                 | Action                                                                   |
| -------------------- | ------------------------------------------------------------------------ |
| **Customer Request** | Customer requests a new healthcare ID card.                              |
| **Authentication**   | Bot verifies the member using Member ID and DOB.                         |
| **Card Selection**   | Customer selects the preferred ID card type.                             |
| **API Execution**    | Bot calls the `create_id_card()` API to create the request.              |
| **Confirmation**     | Bot shares the delivery date and confirms successful request submission. |

---

# 🤖Sequence Outcomes

| Scenario                           | Outcome                                                 |
| ---------------------------------- | ------------------------------------------------------- |
| **Authentication Successful**      | Member identity is verified successfully.               |
| **ID Card Request Submitted**      | New healthcare ID card request is created successfully. |
| **Delivery Information Generated** | Estimated delivery date is returned to the customer.    |
| **Conversation Completed**         | Bot confirms the request and concludes the interaction. |

---

# 🤖Key Features

* Secure member authentication
* Guided conversational interaction
* Real-time backend API integration
* Automated ID card request creation
* Delivery date confirmation
* Seamless end-to-end customer experience
