# 1 - Teorico

![](../../.gitbook/assets/imagen%20%28722%29.png)

#### Vertical access controls <a id="vertical-access-controls"></a>

 Acceso vertical es



Vertical access controls are mechanisms that restrict access to sensitive functionality that is not available to other types of users.

 With vertical access controls, different types of users have access to different application functions. For example, an administrator might be able to modify or delete any user's account, while an ordinary user has no access to these actions. Vertical access controls can be more fine-grained implementations of security models designed to enforce business policies such as separation of duties and least privilege.

#### Horizontal access controls <a id="horizontal-access-controls"></a>

 Horizontal access controls are mechanisms that restrict access to resources to the users who are specifically allowed to access those resources.

 With horizontal access controls, different users have access to a subset of resources of the same type. For example, a banking application will allow a user to view transactions and make payments from their own accounts, but not the accounts of any other user.

#### Context-dependent access controls <a id="context-dependent-access-controls"></a>

 Context-dependent access controls restrict access to functionality and resources based upon the state of the application or the user's interaction with it.

 Context-dependent access controls prevent a user performing actions in the wrong order. For example, a retail website might prevent users from modifying the contents of their shopping cart after they have made payment.

### Examples of broken access controls <a id="examples-of-broken-access-controls"></a>

 Broken access control vulnerabilities exist when a user can in fact access some resource or perform some action that they are not supposed to be able to access.

#### Vertical privilege escalation <a id="vertical-privilege-escalation"></a>

 If a user can gain access to functionality that they are not permitted to access then this is vertical privilege escalation. For example, if a non-administrative user can in fact gain access to an admin page where they can delete user accounts, then this is vertical privilege escalation.

**Unprotected functionality**

 At its most basic, vertical privilege escalation arises where an application does not enforce any protection over sensitive functionality. For example, administrative functions might be linked from an administrator's welcome page but not from a user's welcome page. However, a user might simply be able to access the administrative functions by browsing directly to the relevant admin URL.

 For example, a website might host sensitive functionality at the following URL:

 `https://insecure-website.com/admin`

 This might in fact be accessible by any user, not only administrative users who have a link to the functionality in their user interface. In some cases, the administrative URL might be disclosed in other locations, such as the `robots.txt` file:

 `https://insecure-website.com/robots.txt`

 Even if the URL isn't disclosed anywhere, an attacker may be able to use a wordlist to brute-force the location of the sensitive functionality.

