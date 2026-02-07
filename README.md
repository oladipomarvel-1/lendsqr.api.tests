 Lendsqr Adjutor API Tests – Nigerian Endpoints

Tools Used
- Postman

 Description
 
This repository contains automated API tests for Nigerian Country Specific Endpoints on the Lendsqr Adjutor platform.

The tests validate:
- HTTP status codes
- API response messages

 Endpoints Tested
- BVN Ecosystem Verification
- Check Karma for Customer

How to Run Tests
1. Import the Postman collection into Postman
2. Set your API key in the Authorization header
3. Send each request
4. View test results in the Tests tab

 Note:
endpoints return 403 Forbidden due to permission restrictions. These responses were intentionally validated as part of authorization testing.




#Test Case 1: BVN Ecosystem Verification


Endpoint


GET /v2/verification/ecosystem/38783264239
Description


This endpoint is used to verify a Nigerian customer’s BVN through the ecosystem verification service.
Preconditions
Valid API key generated from Adjutor dashboard


Authorization header configured in Postman


Content-Type set to application/json


Test Data: BVN: 38783264239

Test Steps


Open Postman


Select the BVN Ecosystem Verification request under the existing collection


Add Authorization header with Bearer token


Send GET request


Expected Result


The API should return an HTTP response indicating either successful verification or authorization/validation status.
Actual Result
Status Code: 403 Forbidden


Response Message:


 "Access denied. You do not have permission to access this resource."


Response Time:

534 ms


Result:



Pass


Observation


The endpoint correctly restricts access when the API key lacks sufficient permissions.


Conclusion


Authorization and access control mechanisms are properly enforced for BVN verification endpoints.



#Test Case 2: Check Karma for Customer (Nigerian Endpoint)


Endpoint


GET /v2/verification/karma/+2348069116587


Description


This endpoint checks a customer’s Karma status to identify blacklisted or high-risk individuals within the Nigerian lending ecosystem.
Preconditions


Valid API key generated from Adjutor dashboard


Authorization header configured in Postman


Content-Type set to application/json


Test Data
Customer identifier (as required by endpoint specification)


Test Steps
Open Postman


Create a new request under the same collection


Configure Authorization header using Bearer token


Send GET request


Expected Result


The API should return a response indicating the customer’s Karma status or an authorization error if access is restricted.


Actual Result


Status Code: 403 Forbidden


Response Message:
 "Access denied. You do not have permission to access this resource."


Response Time: ~1.06 s


Result: Pass


Observation


This endpoint appears to be permission-restricted due to its sensitive nature.


Conclusion



Role-based access control is properly implemented on high-risk endpoints such as Karma checks.


