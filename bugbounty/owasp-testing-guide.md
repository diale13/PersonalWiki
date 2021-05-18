# OWASP testing guide

{% embed url="https://owasp.org/www-project-web-security-testing-guide/stable/" %}

## Web Application Security Testing <a id="web-application-security-testing"></a>

### [Introduction and Objectives](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/00-Introduction_and_Objectives/README.html)

During passive testing, a tester tries to understand the application’s logic and explores the application as a user. Tools can be used for information gathering. For example, an HTTP proxy can be used to observe all the HTTP requests and responses. At the end of this phase, the tester should generally understand all the access points and functionality of the system \(e.g., HTTP headers, parameters, cookies, APIs, technology usage/patterns, etc\). The [Information Gathering](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/README.html) section explains how to perform passive testing.

For example, a tester may find a page at the following URL: `https://www.example.com/login/auth_form`

This may indicate an authentication form where the application requests a username and password.

The following parameters represent two access points to the application: `https://www.example.com/appx?a=1&b=1`

In this case, the application shows two access points \(parameters `a` and `b`\). All the input points found in this phase represent a target for testing. Keeping track of the directory or call tree of the application and all the access points may be useful during active testing.

#### Active Testing <a id="active-testing"></a>

During active testing, a tester begins to use the methodologies described in the follow sections.

The set of active tests have been split into 12 categories:

* Information Gathering
* Configuration and Deployment Management Testing
* Identity Management Testing
* Authentication Testing
* Authorization Testing
* Session Management Testing
* Input Validation Testing
* Error Handling
* Cryptography
* Business Logic Testing
* Client-side Testing
* API Testing

### [Information Gathering](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/README.html)

#### [Conduct Search Engine Discovery Reconnaissance for Information Leakage](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/01-Conduct_Search_Engine_Discovery_Reconnaissance_for_Information_Leakage.html)

#### 



### 4.1.2 [Fingerprint Web Server](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/02-Fingerprint_Web_Server.html)

4.1.3 [Review Webserver Metafiles for Information Leakage](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/03-Review_Webserver_Metafiles_for_Information_Leakage.html)

4.1.4 [Enumerate Applications on Webserver](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/04-Enumerate_Applications_on_Webserver.html)

4.1.5 [Review Webpage Content for Information Leakage](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/05-Review_Webpage_Content_for_Information_Leakage.html)

4.1.6 [Identify Application Entry Points](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/06-Identify_Application_Entry_Points.html)

4.1.7 [Map Execution Paths Through Application](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/07-Map_Execution_Paths_Through_Application.html)

4.1.8 [Fingerprint Web Application Framework](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/08-Fingerprint_Web_Application_Framework.html)

4.1.9 [Fingerprint Web Application](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/09-Fingerprint_Web_Application.html)

4.1.10 [Map Application Architecture](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/01-Information_Gathering/10-Map_Application_Architecture.html)

## 

4.2 [Configuration and Deployment Management Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/02-Configuration_and_Deployment_Management_Testing/README.html)

4.3 [Identity Management Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/03-Identity_Management_Testing/README.html)

4.4 [Authentication Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/04-Authentication_Testing/README.html)

4.5 [Authorization Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/05-Authorization_Testing/README.html)

4.6 [Session Management Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/06-Session_Management_Testing/README.html)

4.7 [Input Validation Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/07-Input_Validation_Testing/README.html)

4.8 [Testing for Error Handling](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/08-Testing_for_Error_Handling/README.html)

4.9 [Testing for Weak Cryptography](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/09-Testing_for_Weak_Cryptography/README.html)

4.10 [Business Logic Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/10-Business_Logic_Testing/README.html)

4.11 [Client-side Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/11-Client-side_Testing/README.html)

