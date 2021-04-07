# Chapter 3: The Texas Prison Hack

This story makes clear that many computer attacks can’t be protected against just by securing the perimeter. When the villain isn’t some teen hacker or computer-skilled thief but an insider — a disgruntled employee, a bitter former worker recently fired, or, as in this case, some other type of insiders like William and Danny. 

Insiders often pose a greater threat than the attackers we read about in the newspapers. While the majority of security controls are focused on protecting the perimeter against the outside attacker, **it’s the insider who has access to physical and electronic equipment, cabling, telephone closets, workstations, and network jacks.** They also know who in the organization handles sensitive information and what computer systems the information is stored on, as well as how to bypass any checks put in place to reduce theft and fraud. 

Not just in a prison but everywhere, we all need to be careful and discreet about whom we give sensitive information to. In my own case, the United States Marshal Service created a high level of paranoia about my capabilities. They placed a warning in my file cautioning prison officials not to disclose any personal information to me — not even giving me their names, since they believed a wild rumor that I could tap into the government’s plethora of secret databases and erase the identity of anyone, even a Federal Marshal. I think they had watched “The Net” one too many times.

## COUNTERMEASURES

Detecting insider abuse: 

* **Accountability**. Two common practices raise accountability issues: the use of so-called role-based accounts — accounts shared by multiple users; and the practice of sharing account information or passwords to permit access when an employee is out of the office or unavailable. Both create an environment of plausible deniability when things go seriously wrong. **Very simply, sharing account information should be discouraged if not altogether prohibited**. This includes allowing one worker to use his/her workstation when this requires providing sign-on information.



* **Target-rich environment**. In most businesses, an attacker who can find a way of getting into the work areas of the facility can easily find a way to gain access to systems. Few workers lock their computers when leaving their work area or use screensaver or start-up passwords. It only takes seconds for a malicious person to install stealth monitoring software on an unprotected workstation. In a bank, tellers always lock their cash drawer before walking away. Unfortunately, it’s rare to see this practice being used at other types of institutions. **Consider implementing a policy that requires the use of a screensaver password or other program to electronically lock the machine**. Ensure that the IT department enforces this policy through configuration management.



* **Password management**. My girlfriend was recently employed by a Fortune 50 company that uses a predictable pattern in assigning passwords for outside web-based intranet access: the user’s name followed by a random three-digit number. This password is set when the person is hired and cannot ever be changed by the employee. This makes it possible for any employee to write a simple script that can determine the password in no more than 1,000 tries — a matter of a few seconds. **Employee passwords, whether set by the company or selected by the employees, must not have a pattern that makes them easily predictable.**

\*\*\*\*

* **Physical access**. Knowledgeable employees familiar with the company’s network can easily use their physical access to compromise systems when no one is around. At one point I was an employee of GTE of California, the telecommunications company. Having physical access to the building was like having the keys to the kingdom — everything was wide open. Anyone could walk up to a workstation in an employee’s cubicle or office and gain access to sensitive systems. If employees would properly secure their desktops, workstations, laptops, and PDA devices, by using secure BIOS passwords and logging out, or locking their computer, the bad guy on the inside will need more time to accomplish his objectives. **Train employees to feel comfortable challenging people whose identity is uncertain, especially in sensitive areas**. Use physical security controls like cameras and/or badge access systems to control entry, surveillance, and movement within the facility. Consider periodically auditing physical entry and exit logs to identify unusual patterns of behavior, especially when a security incident arises.



* “**Dead” cubicles and other access points.** When an employee leaves the company or is transferred to a different position, leaving a cubicle empty, a malicious insider can connect via the live network jacks in the cubicle to probe the network while protecting his/her identity. Or worse, a workstation often remains behind in the cubicle, plugged into the network ready for anyone to use, including the malicious insider \(and, as well, any unauthorized visitor who discovers the abandoned cubicle\). Other access points in places like conference rooms also offer easy access to the insider bent on doing damage. Consider disabling all unused network jacks to prevent anonymous or unauthorized access. Ensure that any computer systems in vacant cubicles are secured against unauthorized access.



* **Exiting personnel**. Any worker who has given notice of termination should be considered a potential risk. Such employees should be monitored for any access to confidential business information, especially copying or downloading a significant amount of data. With tiny USB flash drives now readily available that can hold a gigabyte or more of data, it can be a matter of minutes to load up large amounts of sensitive information and walk out the door with **it. It should be routine practice to put restrictions on an employee’s access prior to his/her being notified of a termination, demotion, or undesirable transfer.** Also, consider monitoring the employee’s computer usage to determine any unauthorized or potentially harmful activities. 



* **Installation of unauthorized hardware**. The malicious insider can easily access another employee’s cubicle and install a hardware or software keystroke logger to capture passwords and other confidential information. Again, a flash drive makes stealing data easy. A security policy that prohibits any introduction of hardware devices without written permission, while justified in some circumstances, is admittedly difficult to police; benign employees will be inconvenienced, while the malicious have no incentive for paying attention to the rule. In certain organizations that work with extremely sensitive information, removing or disabling the USB port on workstations may be a necessary control.



* **Circumventing processes**. As employees learn about critical business processes within the organization, they’re in a good position to identify any weaknesses with the checks and balances used to detect fraud or theft. A dishonest worker is in a position to steal or cause other significant harm based on their knowledge of how the business operates. Insiders usually have unfettered access to offices, file cabinets, internal mailing systems, and have knowledge of the day-today business procedures. Consider analyzing sensitive and critical business processes to identify any weaknesses so countermeasures can be implemented. In certain situations, developing separation of duties requirement in the process, where a sensitive operation performed by one person is checked independently by another, can reduce the security risk.



* **On-site visitor policies.** Establish a security policy for outside visitors, including workers from other office locations. An effective security control is to require visitors to present State-issued identification prior to being allowed into the facility, and recording the information in a security log. If a security incident should arise, it may be possible to identify the perpetrator. 



* **Software inventory and auditing**. Maintain an inventory of all authorized software installed or licensed for each system and periodically audit these systems for compliance. This inventory process not only ensures legal compliance with software licensing regulations, but also may be used to identify any unauthorized software installations that could negatively affect security. Unauthorized installation of malicious software like keystroke loggers, adware, or others type of spyware are hard to detect, depending on how clever the developers were at hiding the program within the operating system.  Consider using third-party commercial software to identify these malicious types of programs



* **Audit systems for software integrity**. Employees or malicious insiders could replace critical operating system files or applications that could be used by bypass security controls. In this story, the inmate hackers had changed the PC Anywhere application to run without displaying an icon in the system tray so they would not be detected. The prison officials in this story never realized that their every move was periodically being monitored while Danny and William virtually looked over their shoulders. In some circumstances, it may be appropriate to conduct an integrity audit, and to use a third-party application that notifies the appropriate staff when any changes are made to system files and applications on the “watch list.” 



* **Excessive privileges**. In Windows-based environments, many endusers are logged into accounts with local administrator rights on their own machines. This practice, while more convenient, makes it very easy for a disgruntled insider to install a keystroke logger or networking monitoring \(sniffer\) on any systems where he has local administrator privileges. Remote attackers also may send malicious programs hidden within an email attachment that may be opened by the unsuspecting user. The threat posed by these attachments can be minimized by using the “least privilege” rule, which means that users and programs should run with the fewest privileges necessary to perform their required tasks.













\*\*\*\*

