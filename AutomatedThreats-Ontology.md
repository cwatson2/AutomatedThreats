# Automated Threats to Web Applications - Ontology

DRAFT, May 2015

## Covers

### Front

A New Ontlogy of Automated Threats to Web Applications

### Back

The OWASP Automated Threats to Web Applications Project creates information and other resources for architects, developers, testers, and others to help web application owners defend against automated threats.

https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications

## Preface

The work on OWASP AppSensor had identified 50 or so types of detection points, and we had speculated on which detection points would be most beneficial to an organsation to implemented first. These were based on ensuring an extremely low false positive detection rate so that normal usage was not flagged, and using some estimatation of technical impact i.e. the atacker was really trying to do something serious.

However, I was also interested in what the best detecton points would be for the most common threats to web applications. And here I came across a blocker - there did not seem to be a clear categorisation and quantification of the actual threats most web application owners have to deal with day-to-day. There is a focus on individual types of weaknesses and vulnerabilities, root cause analysis of breaches, and much from vendors about product/service capabilities. Fortunately most applications are not running in a constant state of breach. Business owners cannot always understand the link from security requirements, security issues during development, deployment and oprtaion, and the impact. A focus on individual weaknesses/vulnerabilities in  technical assurance activities, especially where too much emphassis is placed on severity rating of each issue in isolation, fails to provide the overall picture. It is common for a number of individual, low or mediuym severity issues to contribute to a much more significant business impact.

I was particularly concered about misuse of valid functionality as well, as this seemed to be an area where early design decisions had a significant effect on operational risk. In order to quantify the threats, it is necessary to be able to name them, and that did not exist in the usual dictionaries and classifications. This was therefore the first taks - to produce an ontology of automated threats from the perspective of website defenders. I was aware of the magnitude of task of creating identifers, had read advice from contributors to Metrie and First documents. To contain the scope somewhat, I decided to focus soley upon web applications.

The first output - an ontology - is provided in this document. And now we need to move on to producing other materials for web application defenders.

Colin Watson
May 2015

## Introduction

### Background

There is a significant body of knowledge about application vulnerability types, and some general consensus about identification and naming. But issues relating to the misuse of valid functionality, which may be related to design flaws rather than implementation bugs, are less well defined. Yet these problems are seen day-in, day-out, by web application owners.Excessive abuse of functionality is commonly mistakenly reported as application denial-of-service (DoS) attacks such as HTTP-flooding or application resource exhaustion, when in fact the DoS is a side-effect. Some examples are blog & comment spam, fake account creation, password cracking, web scraping, etc. Most of these problems seen regularly by web application owners are not listed in any OWASP Top Ten or other top issue list or dictionary.

This has contributed to inadequate visibility, and an inconsistency in naming such threats, with a consequent lack of clarity in attempts to address the issues.

The OWASP Automated Threats to Web Applications Project has completed a review of reports, academic and other papers, news stories and vulnerability taxonomies/listings to identify, name and classify these attacks – threat events to web applications that are undertaken using automated actions. The initial aim is to produce an ontology providing a common language for developers, architects, operators, business owners, security engineers, purchasers and suppliers/vendors, to facilitate clear communication and help tackling the issues.
The project also intends to identify symptoms, mitigations and controls in this problem area. Like all OWASP outputs, everything is free and published using an open source license. 

### Requirement
Web applications are subjected to unwanted automated usage – day in, day out. Often these events relate to misuse of inherent valid functionality, rather than the attempted exploitation of unmitigated vulnerabilities. Also, excessive misuse is commonly mistakenly reported as application denial-of-service (DoS) like HTTP-flooding, when in fact the DoS is a side-effect instead of the primary intent. Some examples commonly referred to are:

* Account enumeration
* Click fraud
* Comment spam
* Content scraping
* etc

Frequently these have sector-specific names. Most of these problems seen regularly by web application owners are not listed in any OWASP Top Ten or other top issue list. Furthermore, they are not enumerated or defined adequately in existing dictionaries. These factors have contributed to inadequate visibility, and an inconsistency in naming such threats, with a consequent lack of clarity in attempts to address the issues.

Without sharing a common language between devops, architects, business owners, security engineers, purchasers and suppliers/vendors, everyone has to make extra effort to communicate clearly. Misunderstandings can be costly. The adverse impacts affect the privacy and security of individuals as well as the security of the applications and related system components.

### Scope

The aim is to create a listing of vendor-neutral and technology agnostic terms that describe real-world automated threats to web applications, at a level of abstraction that application owners can relate to. These terms are threat events to web applications undertaken using automated actions.

The focus is on abuse of functionality - misuse of inherent functionality and related design flaws, some of which are also referred to as business logic flaws. There is almost no focus on implementation bugs. It is not that the latter are not the target for attacks, but there is much more knowledge published in that area with a greater agreement on terminology. All the scenarios identified must require the web to exist for the threat to be materialised. Many of the scenarios have impacts upon the organisation that owns or operates web applications, but some scenarios have impacts more focused on individuals or other bodies. An attack that can be achieved without the web is out of scope.

Threat events to web applications undertaken using automated actions.

An attack that can be achieved without the web is out of scope.

### Use cases

The ontology and supporting materials are expected to be useful for:

* Defining application security requirements* Sharing intelligence within a sector* Exchanging threat data between CERTs* Labelling penetration test findings* Documenting service acquisition needs* Characterising vendor services

These are expanded upon in Appendix A.

## Research


### Literature review

### Analysis

### Comparison with other dictionaries, taxonomies and lists

OWASP WASC Web Hacking Incidents Database Project (WHID)
WHID classifies publicly known incidents using:

attack methods e.g. ARP spoofing, abuse of functionality, account compromise, administration error, automation, backdoor, banking trojan, brute force, clickjacking, code injection, content injection, content spoofing, credential/session prediction, cross site request forgery (CSRF), cross-site scripting (XSS), denial of service, directory traversal, domain hijacking, DNS hijacking, forceful browsing, HTTP response splitting, hidden parameter manipulation, hosting malicious code, information leakage, insufficient authentication, known vulnerability, local file inclusion (LFI), malvertising, malware, malware injection, mass assignment, misconfiguration, OS commanding, parameter manipulation, path traversal, phishing, predictable resource location, process automation, redirection, remote file inclusion (RFI), rogue 3rd party app, scaping, search engine poisoning, shell injection, social engineering, stolen credentials, SQL injection, unintentional information disclosure, weak password recovery validation, worm
weakness e.g. abuse of functionality, application misconfiguration, directory indexing, improper filesystem permissions, improper input handling, improper output handling, information leakage, insecure indexing, insufficient anti-automation, insufficient authentication, insufficient authorization, insufficient entropy, insufficient password recovery, insufficient process validation, insufficient session expiration, insufficient transport layer protection, misconfiguration, predictable resource location, weak password
outcome account hijacking, account takeover, botnet participation, chaos, credit card leakage, data loss, defacement, DDoS attacks, DNS hijacking, DNS redirection, disinformation, disclosure only, downtime, extortion, fraud, information warfare, leakage of information, link spam, loss of sales, malware distribution, monetary loss, phishing, planting of malware, service disruption, session hijacking, spam, spam links, stolen credentials, worm
Plus other/various/unknown.

Common Attack Pattern Enumeration and Classification (CAPEC)
CAPEC is a dictionary and classification taxonomy of known attacks on software. Its primary classification structures are:

Domains of attack (3000) - Social Engineering (403), Supply Chain (437), Communications (512), Software (513), Physical Security (514), Hardware (515)
Mechanism of Attack (1000) - Gather Information (118), Deplete Resources (119), Injection (152), Deceptive Interactions (156), Manipulate Timing and State (172), Abuse of Functionality (210), Probabilistic Techniques (223), Exploitation of Authentication (225), Exploitation of Authorization (232), Manipulate Data Structures (255), Manipulate Resources (262), Analyze Target (281), Gain Physical Access (436), Malicious Code Execution (525), Alter System Components (526), Manipulate System Users (527)


## The Ontology


### Near Misses


## Glossary

References:

1. [Risk Taxonomy, Technical Standard, The Open Group, 2009](http://pubs.opengroup.org/onlinepubs/9699919899/toc.pdf)
1. [NISTIR 7298 rev 2, NIST](http://nvlpubs.nist.gov/nistpubs/ir/2013/NIST.IR.7298r2.pdf)
1. [OSI model, Wikipedia](http://en.wikipedia.org/wiki/OSI_model)
1. [TCP/IP model, Wikipedia](http://en.wikipedia.org/wiki/Internet_protocol_suite)
1. [Architecture of the World Wide Web, Volume One, W3C](http://www.w3.org/TR/webarch/)
1. [Help and FAQ, W3C](http://www.w3.org/Help/)

### Action
An act taken against an asset by a threat agent. Requires first that contact occurs between the asset and threat agent (Ref 1)
### Application
Software that performs a business process i.e. not system software
A software program hosted by an information system (Ref 2)
### Application layer
"Layer 7” in the OSI model (Ref 3) and “application layer” in the TCP/IP model (Ref 4)
### Threat
Anything that is capable of acting in a manner resulting in harm to an asset and/or organization; for example, acts of God (weather, geological events, etc.); malicious actors; errors; failures (Ref 1)
### Threat Agent
Any agent (e.g., object, substance, human, etc.) that is capable of acting against an asset in a manner that can result in harm (Ref 1)
### Threat Event
Occurs when a threat agent acts against an asset (Ref 1)
### Web
The World Wide Web (WWW, or simply Web) is an information space in which the items of interest, referred to as resources, are identified by global identifiers called Uniform Resource Identifiers (URI) (Ref 5)
The first three specifications for Web technologies defined URLs, HTTP, and HTML (Ref 6)
### Web application
An application delivered over the web

## Appendix A - Use Case Scenarios

### Defining application security requirements

### Sharing intelligence within a sector

Unlimited Innovations Inc provides ecommerce solutions to a range of international retailers and participates in the Retail Cyber Intelligence Sharing Center (R-CISC). Unlimited already builds into its software continuous monitoring capabilities and decides to provide an optional enhancement so that participating retailers could choose to share their misuse event data between each other, to benefit from the combined threat intelligence. Rather than sharing large quantities of  low-level data, Unlimited aggregate information and broadcast validated and categorised threat data amongst the participating companies. Automation attacks are classified according to the [ONTOLOGY] so that each receiving party understands the nature of the threat. Even for retailers that do not want to take part of this information sharing can benefit, since the classified information is made available to internal business management in the form of an easy-to-comprehend monitoring dashboard. The information gathered is also used by the retailers to feed into their business information management systems.
### Exchanging threat data between CERTs

### Labelling penetration test findings

Specialist application security penetration testing firm Cherak Industries Pte Ltd works primarily for financial services companies in the banking and insurance sector and is looking to expand its business throughout Asia. Cherak has some innovative pen test result reporting systems which integrate with client software fault and vulnerability tracking systems, and it is always on the look out for methods to provide additional value to its clients. Cherak has identified that pen test clients would benefit from help with understanding the effects of combinations of vulnerabilities and has decided to utilise the [ONTOLOGY] to define and explain the automation-related threats. The individual vulnerabilities were scored as normal using CVSSv2 and v3, the matching CWEs identified, and mitigations in place documented. In addition Cherak used the [ONTOLOGY] to help create a new section in the executive summary to explain how combinations of the issues found could lead to automation threats and the possible technical and business impacts. For example, an assessment for one client had identified weaknesses in authentication so that [CREDENTIAL STUFFING] is an automation threat. The defined [ONTOLOGY] entry name and ID were provided so that the client's technical staff could refer to additional information on the OWASP website.
### Documenting service acquisition needs

Falstone Paradise Inc is concerned about malicious use of their portfolio of hotel and resort websites. The majority of the websites use a shared application platform, but there are some unique applications and a large number of other micro-sites, some of which use generic content management systems such as Wordpress and Drupal. Falstone Paradise has identified that its IT operations team are spending too much time dealing with the effects of automated misuse, such as cleaning up data, resetting customer accounts and providing extra capacity during attacks. Furthermore, the unwanted automation is also causing some instabilities leading to negative feedback from customers. Therefore Falstone Paradise has decided to go out to the security marketplace to identify, assesses and select products or services that might help address these automation issues for all its websites. Its buying team worked with their colleagues in information technology to write the detailed requirements in an Invitation to Tender (ITT) document. This described the types of attacks its web applications are receiving, the frequency of occurrence and magnitudes. These are defined according to the [ONTOLOGY] so that vendors do not misunderstand the requirements, and so that each vendor's offering could be assessed against each individual type of automation threat. 
### Characterising vendor services




