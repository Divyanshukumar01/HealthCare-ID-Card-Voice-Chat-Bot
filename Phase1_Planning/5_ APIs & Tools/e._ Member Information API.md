# 📊 Member Information API:

Retrieves member profile information after successful authentication.


# 📊 Purpose:

\* Personalize conversations

\* Verify mailing details

\* Support ID card operations



# 📊 API Function:

get\_member\_details(member\_id)



# 📊 Sample Request:

{

"member\_id": "M001"

}


# 📊 Sample Response:

{

"memberId": "M001",

"name": "Rahul Sharma",

"address": "123 Main Street",

"email": "\[rahul@example.com](mailto:rahul@example.com)",

"phone": "+91XXXXXXXXXX"

}


# 📊 Business Logic:

1. Fetch profile data.

2. Validate account status.

3. Return current member information.

4. Enable downstream agent operations.



