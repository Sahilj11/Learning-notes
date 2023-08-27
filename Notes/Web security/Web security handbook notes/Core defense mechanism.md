- The defense mechanisms employed by web applications comprise the following core elements:
	- Handling user access to the application’s data and functionality to prevent  users from gaining unauthorized access
	- Handling user input to the application’s functions to prevent malformed input from causing undesirable behavior
	- Handling attackers to ensure that the application behaves appropriately when being directly targeted, taking suitable defensive and offensive measures to frustrate the attacker
	- Managing the application itself by enabling administrators to monitor its activities and configure its functionality

## Handling User Access
- Most web applications handle access using a trio of interrelated security mechanisms:
	- Authentication
	- Session management
	- Access control
- Because of their interdependencies, the overall security provided by the mechanisms is only as strong as the weakest link in the chain. A defect in any single component may enable an attacker to gain unrestricted access to the application’s functionality and data.
#### Authentication
- Authenticating a user involves establishing that the user is in fact who he claims to be.
- The majority of today’s web applications employ the conventional authentication model, in which the user submits a username and password, which the application checks for validity.
- other authentication models may be used, based on 
	- client certificates, 
	- smartcards, 
	- challenge-response tokens.
- In addition to the core login process, authentication mechanisms often employ a range of other supporting functionality, such as self-registration, account recovery, and a password change facility.
- When you are attacking a web application, you should invest a signifi cant amount of attention to the various authentication-related functions it contains. Surprisingly frequently, defects in this functionality enable you to gain unauthorized access to sensitive data and functionality

#### Session Management
- The session itself is a set of data structures held on the server that track the state of the user’s interaction with the application
- When a user receives a token, the browser automatically submits it back to the server in each subsequent HTTP request, enabling the application to associate the request with that user.
- HTTP cookies are the standard method for transmitting session tokens, although many applications use hidden form fi elds or the URL query string for this purpose.
- In terms of attack surface, the session management mechanism is highly dependent on the security of its tokens. The majority of attacks against it seek to compromise the tokens issued to other users. If this is possible, an attacker can masquerade as the victim user and use the application just as if he had actually authenticated as that user. The principal areas of vulnerability arise from defects in how tokens are generated, enabling an attacker to guess the tokens issued to other users, and defects in how tokens are subsequently handled, enabling an attacker to capture other users’ tokens.
- A small number of applications dispense with the need for session tokens by using other means of reidentifying users across multiple requests. If HTTP’s built-in authentication mechanism is used, the browser automatically resubmits the user’s credentials with each request, enabling the application to identify the user directly from these. In other cases, the application stores the state information on the client side rather than the server, usually in encrypted form to prevent tampering

#### Access Control
- to make and enforce correct decisions about whether each individual request should be permitted or denied. If the mechanisms just described are functioning correctly, the application knows the identity of the user from whom each request is received. On this basis, it needs to decide whether that user is authorized to perform the action, or access the data, that he is requesting,
- Probing for these vulnerabilities is often laborious, because essentially the same checks need to be repeated for each item of functionality. Because of the prevalence of access control flaws, however, this effort is always a worthwhile investment when you are attacking a web application

## Handling User Input

#### Varieties of Input
- typical application receives numerous items of data that began their life on the server and that are sent to the client so that the client can transmit them back to the server on subsequent requests. This includes items such as cookies and hidden form fi elds, which are not seen by ordinary users of the application but which an attacker can of course view and modify

#### Approaches to Input Handling

##### Semantic Checks
- The defenses described so far all address the need to defend the application against various kinds of malformed data whose content has been crafted to interfere with the application’s processing. However, with some vulnerabilities the input supplied by the attacker is identical to the input that an ordinary, nonmalicious user may submit. What makes it malicious is the different circumstances under which it is submitted. For example, an attacker might seek to gain access to another user’s bank account by changing an account number transmitted in a hidden form fi eld. No amount of syntactic validation will distinguish between the user’s data and the attacker’s. To prevent unauthorized access, the application needs to validate that the account number submitted belongs to the user who has submitted it.
- 
##### Safe Data Handling
- Many web application vulnerabilities arise because user-supplied data is processed in unsafe ways. Vulnerabilities often can be avoided not by validating the input itself but by ensuring that the processing that is performed on it is inherently safe. 
- In some situations, safe programming methods are available that avoid common problems. For example, SQL injection attacks can be prevented through the correct use of parameterized queries for database access (see Chapter 9). In other situations, application functionality can be designed in such a way that inherently unsafe practices, such as passing user input to an operating system command interpreter, are avoided. This approach cannot be applied to every kind of task that web applications need to perform. But where it is available, it is an effective general approach to handling potentially malicious input

##### “Reject Known Bad”
- This approach typically employs a blacklist containing a set of literal strings or patterns that are known to be used in attacks. The validation mechanism blocks any data that matches the blacklist and allows everything else.
- First, a typical vulnerability in a web application can be exploited using a wide variety of input, which may be encoded or represented in various ways. Except in the simplest of cases, it is likely that a blacklist will omit some patterns of input that can be used to attack the application.
- Many blacklist-based fi lters can be bypassed with almost embarrassing ease by making trivial adjustments to the input that is being blocked. For example:
	- If SELECT is blocked, try  SeLeCt
	- If  1=1-- is blocked, try 2=2--
	- If alert(‘xss’) is blocked,   prompt(‘xss’)
- In other cases, fi lters designed to block specifi c keywords can be bypassed by using nonstandard characters between expressions to disrupt the tokenizing performed by the application. For example: 
	- `SELECT/*foo*/username,password/*foo*/FROM/*foo*/users <img%09onerror=alert(1) src=a>`
- Finally, numerous blacklist-based filters, particularly those implemented in web application firewalls, have been vulnerable to NULL byte attacks.
- nserting a NULL byte anywhere before a blocked expression can cause some fi lters to stop processing the input and therefore not identify the expression. For example: `%00<script>alert(1)</script>`
- remember in C we learnt that to known end of string null character is used
- Null byte injection
	- Null byte is a bypass technique for sending data that would be filtered otherwise. It relies on injecting the null byte characters (`%00`, `\x00`) in the supplied data. Its role is to terminate a string.
	- Practice: File access restriction by extension
		- Accessing a file in an application that appends an extension.
			- Example:
				- 1.An attacker wants to retrieve the file`/etc/passwd` but an extension `.php` is appended automatically such as `/etc/passwd.php`.
				- 2. The attacker uses the null byte to terminate the string and throw away the `.php` extension: `/etc/passwd%00`
	- File upload restriction by extension: Uploading a file that is filtered by its extension.
		- Example:
			- 1.An attacker wants to upload a `malicious.php`, but the only extension allowed is `.pdf`.			    			
			- 2. The attacker constructs the file name such as `malicious.php%00.pdf` and uploads the file.		    			
			- 3 The application reads the `.pdf` extension, validate the upload, and later throws the end of the string due to the null byte.					
			- 4. The file `malicious.php` is then put in the server.
- In contexts where NULL bytes are tolerated and ignored (for example, within HTML in some browsers), arbitrary NULL bytes can be inserted within blocked expressions to defeat some blacklist-based filters. Attacks of this kind are discussed in detail in later chapters.

##### “Accept Known Good”
- This approach employs a whitelist containing a set of literal strings or patterns, or a set of criteria, that is known to match only benign input. The validation mechanism allows data that matches the whitelist and blocks everything else
- in numerous situations an application must accept data for processing that does not meet any reasonable criteria for what is known to be “good.” For example, some people’s names contain an apostrophe or hyphen. These can be used in attacks against databases, but it may be a requirement that the application should permit anyone to register under his or her real name. Hence, although it is often extremely effective, the whitelist-based approach does not represent an all-purpose solution to the problem of handling user input

##### Sanitization
- Instead of rejecting this input, the application sanitizes it in various ways to prevent it from having any adverse effects. Potentially malicious characters may be removed from the data, leaving only what is known to be safe, or they may be suitably encoded or “escaped” before further processing is performed
- For example, the usual defense against cross-site scripting attacks is to **HTML-encode** dangerous characters before these are embedded into pages of the application (see Chapter 12). However, effective sanitization may be difficult to achieve if several kinds of potentially malicious data need to be accommodated within one item of input. In this situation, a boundary validation approach is desirable, as described later
	- HTML encoding 
		- HTML encoding, also known as HTML escaping or character entity encoding, is the process of converting special characters and symbols in an HTML document into their corresponding HTML entities. HTML entities are special sequences of characters that represent specific characters or symbols within HTML code.
		- HTML encoding is used to ensure that the content of an HTML document is properly displayed and interpreted by web browsers, regardless of any special characters or symbols that may be present. It helps prevent these characters from being misinterpreted as HTML markup or affecting the structure and rendering of the web page.
		- For example, the less-than symbol "<" is encoded as "<", the greater-than symbol ">" is encoded as ">", and the ampersand "&" is encoded as "&". By encoding these characters, they are displayed as literal text and not interpreted as part of HTML tags or entities.
		- HTML encoding is particularly important when displaying user-generated content on a website to prevent cross-site scripting (XSS) attacks. By encoding user input, any potentially malicious code or script embedded within the input will be treated as literal text and not executed by the browser.
		- There are various ways to perform HTML encoding, such as using specific functions or libraries provided by programming languages, or manually replacing characters with their corresponding HTML entities.
##### Boundary validation
- each individual component or functional unit of the server-side application treats its inputs as coming from a potentially malicious source. Data validation is performed at each of these trust boundaries, in addition to the external frontier between the client and server.
- validation checks can be performed against whatever value the data has as a result of previous transformations. And because the various validation checks are implemented at different stages of processing, they are unlikely to come into confl ict with one another.
##### Multistep Validation and Canonicalization
- an application may attempt to defend against some cross-site scripting attacks by stripping the expression:
```
<script>
from any user-supplied data. However, an attacker may be able to bypass the
filter by supplying the following input: <scr<script>ipt>When the blocked expression is removed, the surrounding data contracts to restore the malicious payload, because the filter is not being applied
recursively.
```
- 
```
Similarly, if more than one validation step is performed on user input, an
attacker may be able to exploit the ordering of these steps to bypass the fi lter.
For example, if the application fi rst removes ../ recursively and then removes
..\ recursively, the following input can be used to defeat the validation:
....\/
```
- Canonicalization the process of converting or decoding data into a common character set. If any canonicalization is carried out after input filters have been applied, an attacker may be able to use a suitable encoding scheme to bypass the validation mechanism.
	- what does converting or decoding data means 
		-   Converting or decoding data into a common character set refers to the process of ensuring that data is represented using a standardized set of characters or symbols. It involves transforming the data from one character encoding scheme to another to achieve consistency and compatibility.
		- Character encoding defines how characters are represented and stored in computer systems. Different character encoding schemes, such as ASCII, UTF-8, ISO-8859-1, and many others, use different methods to assign numeric values to characters.
		- When data is received or processed by a system, it is essential to ensure that the characters are correctly interpreted and understood. Converting or decoding data into a common character set helps achieve this goal by translating the data from its original encoding scheme to a standardized or widely supported encoding scheme.
		- For example, let's say you have data encoded using ISO-8859-1, which represents characters using 8 bits. However, the system you are working with expects data to be encoded using UTF-8, a more comprehensive character encoding that supports a wider range of characters. In this case, you would need to convert or decode the data from ISO-8859-1 to UTF-8, ensuring that the characters are represented correctly and can be interpreted by the system.
		- The process of converting or decoding data into a common character set typically involves analyzing the current encoding scheme, mapping the characters to their corresponding representations in the target encoding scheme, and performing the necessary transformations to achieve consistency. This ensures that the data can be accurately interpreted, displayed, and processed across different systems, applications, or platforms that support the common character set.
		- By converting or decoding data into a common character set, interoperability is enhanced, as data can be seamlessly exchanged and understood between systems regardless of the encoding schemes they use. It helps prevent data corruption, loss of information, or misinterpretation that can occur when incompatible character encodings are encountered.
- For example, an application may attempt to defend against some SQL injection attacks by blocking input containing the apostrophe character. However, if the input is subsequently canonicalized, an attacker may be able to use double URL encoding to defeat the filter. For example:%2527 (here the value of %25 is %)
	- What is double URL encoding
		- Using double URL encoding is a technique employed by attackers to bypass filters that are designed to detect and prevent certain types of malicious input or characters. Double URL encoding involves encoding data multiple times using URL encoding, which is a method of representing special characters within a URL.
		- URL encoding replaces reserved or special characters with a percent sign (%) followed by their hexadecimal representation. For example, the space character ( ) is encoded as "%20", the equals sign (=) is encoded as "%3D", and so on.
		- When a web application applies URL decoding to incoming data, it interprets the encoded characters and converts them back to their original form. However, if an attacker employs double URL encoding, the application may mistakenly interpret the encoded characters as harmless and fail to detect the intended malicious input.
		- Here's an example to illustrate the technique:
			1. Original input: `admin`
			2. First URL encoding: `%61%64%6D%69%6E`
			3. Second URL encoding (each `%` is encoded as `%25`): `%2561%2564%256D%2569%256E`
		- When the web application applies URL decoding to the double-encoded input, it may decode `%2561` as `%61`, which corresponds to the letter `a`. This results in the application interpreting the input as `admin`, allowing the attacker to bypass filters that were specifically looking for the term "admin."
		- By using double URL encoding, attackers attempt to obfuscate malicious input and deceive the input filters into treating it as harmless or non-malicious data. This technique can potentially bypass security mechanisms that rely on specific patterns or keywords to detect and prevent attacks.
		- To protect against such attacks, web applications should implement robust input validation and filtering mechanisms that take into account various encoding schemes, including double URL encoding. It's important to validate and sanitize input data thoroughly, applying context-aware filtering and employing secure coding practices to mitigate the risk of attacks attempting to exploit encoding vulnerabilities
- When this input is received, the application server performs its normal URL decode, so the input becomes: %27
- This does not contain an apostrophe, so it is permitted by the application’s filters. But when the application performs a further URL decode, the input is converted into an apostrophe, thereby bypassing the filter.
- It is worth noting that the multiple validation and canonicalization steps in these cases need not all take place on the server side of the application. For example, in the following input several characters have been HTML-encoded:
``<iframe src=j&#x61;vasc&#x72ipt&#x3a;alert&#x28;1&#x29; >
- If the server-side application uses an input fi lter to block certain JavaScript expressions and characters, the encoded input may succeed in bypassing the filter. However, if the input is then copied into the application’s response, some browsers perform an HTML decode of the src parameter value, and the embedded JavaScript executes.
	- The excerpt highlights the importance of performing validation and canonicalization not only on the server side but also on the client side of an application to prevent potential security vulnerabilities. It emphasizes a scenario where multiple steps of validation and canonicalization are involved and demonstrates how the absence of such measures can lead to an exploitable situation.
	- In the given example, the input provided is a string that includes HTML-encoded characters. HTML encoding is a method of representing special characters using their corresponding HTML entities. For instance, the less-than symbol (<) is encoded as "<", the greater-than symbol (>) is encoded as ">", and so on.
	- The input in the example contains an HTML-encoded string that represents an iframe element with a JavaScript code as the source (src) parameter. The JavaScript code embedded in the src parameter is an alert(1) function call, which typically displays an alert dialog box with the message "1".
	- Now, if the server-side application utilizes an input filter to block certain JavaScript expressions or characters, it may analyze the encoded input and determine it as safe or not malicious. However, the issue arises when the input is then copied into the application's response, which is sent to the client-side (browsers).
	- Some web browsers automatically perform an HTML decode of certain HTML-encoded characters, such as the src parameter value in this case. This decoding process translates the encoded characters back into their original form. As a consequence, the JavaScript code embedded in the src parameter is executed by the browser, leading to the execution of the alert(1) function and the display of an alert dialog box with the message "1".
	- This scenario highlights the need for both server-side and client-side validation and canonicalization. While server-side filters can help detect and prevent certain malicious inputs, it is essential to consider the behavior of client-side components, such as browsers, that may interpret or decode HTML-encoded data.
	- By performing validation and canonicalization on both the server side and the client side, potential vulnerabilities can be addressed more comprehensively, reducing the risk of attacks and ensuring the security and integrity of the application.
- some technologies perform a “best fi t” mapping of characters based on similarities in their printed glyphs. Here, the characters « and » may be converted into < and >, respectively, and Ÿ and Â are converted into Y and A. This behavior can often be leveraged to smuggle blocked characters or keywords past an application’s input filters.
- One approach is to perform sanitization steps recursively, continuing until no further modifications have been made on an item of input. However, where the desired sanitization involves escaping a problematic character, this may result in an infinite loop. Often, the problem can be addressed only on a case-by-case basis, based on the types of validation being performed. Where feasible, it may be preferable to avoid attempting to clean some kinds of bad input, and simply reject it altogether.
	- The excerpt suggests one possible approach to sanitization, which is to perform the sanitization steps recursively until no further modifications are made to an input item. Sanitization refers to the process of cleansing or filtering input data to remove or neutralize potentially harmful or malicious content.
	- In many cases, the sanitization process involves identifying problematic characters or sequences that could pose a security risk and applying appropriate modifications to mitigate those risks. For example, escaping certain characters by adding escape characters or **encoding them in a specific format is a common sanitization technique.**
		- **Escaping certain characters by adding escape characters** is a common technique used in input sanitization to neutralize the special meaning of those characters and prevent them from being interpreted in unintended ways. The process involves inserting escape characters before specific characters or sequences to indicate that they should be treated as literal characters rather than having their usual interpretation or functionality.
		- Here's an example to illustrate the concept:
		- Consider a web application that allows users to submit text input that will be displayed on a webpage. To prevent users from injecting malicious HTML or JavaScript code that could be executed by browsers, the application needs to escape certain characters.
		- One common approach is to escape the following characters:
			1. Less-than symbol (<): It is escaped by replacing it with "<". This prevents the browser from interpreting it as the opening tag of an HTML element.	    
			2. Greater-than symbol (>): It is escaped by replacing it with ">". This prevents the browser from interpreting it as the closing tag of an HTML element.		    
			3. Ampersand (&): It is escaped by replacing it with "&". This prevents the browser from interpreting it as the start of an HTML entity.
		- By applying these escape sequences, the characters are treated as plain text rather than having their special meaning in HTML or other contexts. For example, if a user submits the following input:
		- **Encoding characters in a specific format is another commonly used technique** in input sanitization to ensure that potentially harmful characters or sequences are safely represented without their original meaning or functionality. This technique involves transforming the characters into a different format that preserves their integrity but renders them inert in terms of executing code or causing unintended behavior.
		- Here are a few examples of encoding techniques used in sanitization:
			1. URL Encoding: URL encoding replaces special characters with a percent sign (%) followed by their hexadecimal representation. This encoding ensures that the characters are represented in a URL-safe format and can be safely transmitted. For example, the space character ( ) is encoded as "%20", the equals sign (=) is encoded as "%3D", and so on. URL encoding is typically used to sanitize input that will be included in URLs or used in HTTP requests.	    
			2. HTML Entity Encoding: HTML entity encoding replaces special characters with their corresponding HTML entity representation. For instance, the less-than symbol (<) is encoded as "<", the greater-than symbol (>) is encoded as ">", and the ampersand (&) is encoded as "&". HTML entity encoding is commonly used to sanitize user input that will be displayed as part of an HTML document, preventing any interpretation of the input as HTML tags or entities.		    
			3. Base64 Encoding: Base64 encoding represents binary data using a set of 64 characters that are safe for transmission over text-based protocols. This encoding is often used to sanitize input that contains binary or non-printable characters. Base64 encoding converts the data into a string of alphanumeric characters, making it safe for storage or transmission in systems that only accept text-based input.
		- By encoding characters in a specific format, the original meaning or functionality of the characters is effectively neutralized. This ensures that the input data is treated as inert text rather than potentially executable code or commands.
		- It is important to note that when applying encoding as a sanitization technique, the corresponding decoding process must be implemented when the sanitized data is used. The encoded data needs to be properly decoded to restore its original form and meaning in the appropriate context.
		- Encoding characters in a specific format is a reliable way to prevent various types of injection attacks, code execution vulnerabilities, and data corruption issues caused by untrusted input. Proper implementation of encoding and decoding processes in the sanitization workflow enhances the security and integrity of the application.
	- However, the excerpt also raises a potential challenge with this approach. In situations where the desired sanitization process involves escaping a problematic character, it's possible to encounter an infinite loop. This means that the recursive sanitization process may continuously modify the input without reaching a point where no further modifications are needed.
	- For instance, consider a scenario where the sanitization process aims to escape the character "<" by replacing it with "<". If the recursive sanitization process is not carefully implemented, it may repeatedly detect the occurrence of "<" and replace it with "<" in an endless loop, never reaching a state where the input is considered fully sanitized.
	- To address this challenge, proper control structures and conditions need to be in place to prevent infinite loops during the sanitization process. This could involve checking for specific conditions or patterns that indicate the completion of sanitization, or setting a maximum limit on the number of recursive iterations.
	- It's important to carefully design and test the sanitization logic to ensure it effectively removes or neutralizes potentially harmful content without causing unintended consequences or performance issues. By considering the specific requirements and constraints of the sanitization process, including potential risks of infinite loops, developers can implement robust and secure sanitization mechanisms in their applications
	
## Handling Attackers

### Handing error
- A key defense mechanism is for the application to handle unexpected errors gracefully, and either recover from them or present a suitable error message to the user. In a production context, the application should never return any system-generated messages or other debug information in its responses. As you will see throughout this book, overly verbose error messages can greatly assist malicious users in furthering their attacks against the application. In some situations, an attacker can leverage defective error handling to retrieve sensitive information within the error messages themselves, providing a valuable channel for stealing data from the application. Figure 2-6 shows an example of an unhandled error resulting in a verbose error message.
- most application servers can be configured to deal with unhandled application errors in customized ways, such as by presenting an uninformative error message

### Maintaining Audit Logs
- In any application for which security is important, key events should be logged as a matter of course. At a minimum, these typically include the following:
	- All events relating to the authentication functionality, such as successful
	and failed login, and change of password
	- Key transactions, such as credit card payments and funds transfers
	- Access attempts that are blocked by the access control mechanisms
	- Any requests containing known attack strings that indicate overtly malicious intentions
- Effective audit logs typically record the time of each event, the IP address from which the request was received, and the user’s account (if authenticated). Such logs need to be strongly protected against unauthorized read or write access. An effective approach is to store audit logs on an autonomous system that accepts only update messages from the main application. In some situations, logs may be flushed to write-once media to ensure their integrity in the event of a successful attack.
- In terms of attack surface, poorly protected audit logs can provide a gold mine of information to an attacker, disclosing a host of sensitive information such as session tokens and request parameters. This information may enable the attacker to immediately compromise the entire application, as shown in Figure 2-7.
- ![[Pasted image 20230614171021.png]]
### Alerting Administrators
- Anomalous events monitored by alerting mechanisms often include the following:
	- Usage anomalies, such as large numbers of requests being received from
	a single IP address or user, indicating a scripted attack
	- Business anomalies, such as an unusual number of funds transfers being made to or from a single bank account
	- Requests containing known attack strings
	- Requests where data that is hidden from ordinary users has been modified
- Some of these functions can be provided reasonably well by off-the-shelf application firewalls and intrusion detection products
- However, their effectiveness usually is limited by the fact that each web application is different, so the rules employed are inevitably generic to some extent. Web application firewalls usually are good at identifying the most obvious attacks, where an attacker submits standard attack strings in each request parameter. However, many attacks are more subtle than this. For example, perhaps they modify the account number in a hidden fi eld to access another user’s data, or submit requests out of sequence to exploit defects in the application’s logic
- In any security-critical application, the most effective way to implement real time alerting is to integrate this tightly with the application’s input validation mechanisms and other controls. For example, if a cookie is expected to have one of a specific set of values, any violation of this indicates that its value has been modified in a way that is not possible for ordinary users of the application.
- Similarly, if a user changes an account number in a hidden field to identify a different user’s account, this strongly indicates malicious intent. The application should already be checking for these attacks as part of its primary defenses, and these protective mechanisms can easily hook into the application’s alerting mechanism to provide fully customized indicators of malicious activity. Because these checks have been tailored to the application’s actual logic, with a fi ne-grained knowledge of how ordinary users should be behaving, they are much less prone to false positives than any off-the-shelf solution, however configurable or easy-to-learn that solution may be
### Reacting to Attacks
- For example, they might respond increasingly slowly to the attacker’s requests or terminate the attacker’s session, requiring him to log in or perform other steps before continuing the attack. Although these measures will not defeat the most patient and determined attacker, they will deter many more casual attackers and will buy additional time for administrators to monitor the situation and take more drastic action if desired.

## Managing the Application
- In many applications, administrative functions are implemented within the application itself, accessible through the same web interface as its core nonsecurity functionality, as shown in Figure 2-8. Where this is the case, the administrative mechanism represents a critical part of the application’s attack surface. Its primary attraction for an attacker is as a vehicle for privilege escalation
- ![[Pasted image 20230614172452.png]]
	- Weaknesses in the authentication mechanism may enable an attacker to gain administrative access, effectively compromising the entire application.
	- Many applications do not implement effective access control of some of their administrative functions. An attacker may find a means of creating a new user account with powerful privileges.
	- Administrative functionality often involves displaying data that originated from ordinary users. Any cross-site scripting flaws within the administrative interface can lead to compromise of a user session that is guaranteed to have powerful privileges.
	- Administrative functionality is often subjected to less rigorous security testing, because its users are deemed to be trusted, or because penetration testers are given access to only low-privileged accounts. Furthermore, the functionality often needs to perform inherently dangerous operations, involving access to fi les on disk or operating system commands. If an attacker can compromise the administrative function, he can often leverage it to take control of the entire server.

"<script>alert("foo")</script>