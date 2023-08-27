## Client side validation
```
<input required>
```
- Client-side validation refers to the process of validating user input or data on the client side, typically using JavaScript, before sending it to the server. It is an important aspect of web development that helps ensure data integrity and improve user experience.
- Here are some key points about client-side validation:
	1. Validation on the user's device: Client-side validation occurs directly on the user's device, typically in a web browser. This means that the validation logic is executed on the client side without involving the server.
	2. Instant feedback to users: By validating data on the client side, users can receive immediate feedback on their input without waiting for a round trip to the server. This can improve the user experience by providing real-time validation errors and helping users correct their input before submitting the form.
	3. Prevent unnecessary server requests: Client-side validation can help prevent unnecessary server requests by identifying and rejecting invalid or incomplete data before it is sent to the server. This can reduce the load on the server and improve overall application performance.
	4. Basic data validation: Client-side validation often involves basic checks such as verifying required fields, validating data formats (e.g., email addresses, phone numbers), checking for minimum and maximum lengths, and ensuring numeric values are within specific ranges. These checks help enforce data integrity and improve the accuracy of submitted data.
	5. Enhanced user experience: Client-side validation allows developers to provide a more interactive and user-friendly experience by validating data in real time. For example, it can highlight input fields with validation errors, display error messages near the corresponding fields, or dynamically update the UI based on the validity of user input.
	6. Complementary to server-side validation: While client-side validation offers immediate feedback and helps improve user experience, it should always be complemented with server-side validation. Client-side validation can be bypassed or manipulated, so server-side validation is crucial for ensuring data integrity and security. Server-side validation acts as a safety net to re-validate data on the server and protect against malicious or incorrect data that may bypass the client-side checks
- In conclusion, client-side validation is a valuable technique for improving user experience, reducing unnecessary server requests, and ensuring basic data integrity. However, it should always be combined with server-side validation to provide robust and secure data validation.
### techniques
- Client-side validation techniques typically involve using JavaScript to validate user input directly on the client's device before submitting the data to the server. Here are some common techniques used for client-side validation:
	1. Required Fields Validation:
	    - Check if required fields are filled in by the user before submitting the form.
	    - Validate that mandatory fields are not left empty or contain only whitespace characters.
	2. Data Format Validation:
	    - Validate specific data formats, such as email addresses, phone numbers, dates, or URLs.
	    - Regular expressions (RegEx) can be used to match and validate patterns.
	3. Length and Size Validation:
	    - Validate that input lengths or sizes are within acceptable ranges.
	    - Check minimum and maximum lengths for text inputs or limits for file uploads.
	4. Numeric Value Validation:
	    - Validate numeric input fields to ensure they are within specified ranges or constraints.
	    - Verify if the input is a valid number and falls within a certain minimum and maximum value.
	5. Password Strength Validation:
	    - Implement validation rules to ensure password strength, such as minimum length, requiring a combination of letters, numbers, and special characters.
	6. Confirmation Fields Validation:
	    - Validate fields where the user is asked to enter information twice for confirmation, such as password confirmation or email confirmation fields.
	7. Checkbox and Radio Button Validation:
	    - Ensure that checkboxes or radio buttons that require selection are not left unchecked.
	8. File Upload Validation:
	    - Validate file uploads for specific file types, sizes, or dimensions.
	    - Check the file extension or MIME type to ensure it matches the expected format.
	9. Real-Time Validation:
	    - Provide instant feedback to users while they are entering data.
	    - Perform validation on specific fields as the user types, highlighting errors or showing validation messages dynamically.
	10. Custom Validation Rules:
	    - Implement custom validation rules based on specific business requirements.
	    - Check for specific conditions or combinations of values that need to be validated.
- It's important to note that client-side validation should always be accompanied by server-side validation. Client-side validation can be bypassed or manipulated, so server-side validation is necessary to ensure data integrity and security. Server-side validation acts as a final line of defense to validate the data before processing or storing it.

## Server side validation
```
REGISTRANTS = {}

SPORTS =[

    'Basketball',

    'Badminton',

    'Football'

]

@app.route('/register', methods=['POST'])
def register():
    name= request.form.get('name')
    if not name:
        return render_template('faliure.html')
    sport= request.form.get('sport')
    if sport not in SPORTS:
        return render_template('faliure.html')
    REGISTRANTS[name] = sport
    return render_template('success.html')
```
- Server-side validation refers to the process of validating user input or data on the server-side, typically after the data is submitted by the client. It is an essential step in ensuring data integrity, security, and consistency in web applications. Unlike client-side validation, server-side validation is performed on the server, independent of the client device.
- Here are some techniques that can be used to ensure server-side validation:
	1. Input Sanitization:
	    - Validate and sanitize user input to remove or escape potentially harmful characters or scripts that could lead to security vulnerabilities, such as SQL injection or cross-site scripting (XSS) attacks.
	    - Techniques like parameterized queries or prepared statements can be used to mitigate SQL injection vulnerabilities.
	2. Data Type Validation:
	    - Validate that the submitted data is of the expected data type.
	    - Ensure that numeric fields are actually numbers, dates are valid, and text inputs do not contain unexpected characters.
	3. Range and Constraint Validation:
	    - Validate that submitted values fall within acceptable ranges or meet predefined constraints.
	    - Check if numeric values are within specified minimum and maximum limits.
	    - Verify that text inputs do not exceed the allowed character limits.
	4. Business Rule Validation:
	    - Implement validation rules specific to your application's business logic and requirements.
	    - Check for complex conditions, dependencies, or combinations of values to ensure data consistency and integrity.
	    - Verify if the submitted data adheres to the business rules defined by your application.
	5. Database Integrity Validation:
	    - Validate submitted data against the integrity constraints defined in the database schema.
	    - Check for uniqueness, referential integrity, or other constraints specified in the database design.
	    - Ensure that the submitted data does not violate the integrity of the database.
	6. File Upload Validation:
	    - Validate file uploads to ensure they meet specific criteria, such as file type, size, or format requirements.
	    - Check the file extension, MIME type, or perform virus/malware scanning on uploaded files.
	7. Authentication and Authorization Validation:
	    - Validate user credentials during authentication to ensure the entered username and password are correct.
	    - Verify if the user has the necessary permissions and privileges to perform certain actions or access specific resources.
	8. Error Handling and Messaging:
	    - Properly handle validation errors by providing meaningful error messages to the user.
	    - Display error messages that clearly indicate the cause of the validation failure and guide the user in correcting their input.
	9. Localization and Internationalization:
	    - Consider language and cultural differences during validation.
	    - Ensure that validation messages and error handling are localized to the user's preferred language or locale.

# Scalibility
- can be tackled 
	- vertical scaling :- making server large
	- horizontal scaling:- getting one more server
	- load balancer:- request sent to load balancer and see which server to sent the request
		- session aware balancing
			- stick session (storing session in server)
			- session in database (storing session in database)
			- client side session (cookie)
# Caching
- using ETag after cache expire to see if value of ETag same then no need to request whole page
- 
# HTTPS
- works on public key encryption
- there are two type of key involved a public key and private key,
- public key is used to encrypt data and private key for decrypting