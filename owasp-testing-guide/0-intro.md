# 0 - Intro

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

