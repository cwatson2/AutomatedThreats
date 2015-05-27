# Automated Threats to Web Applications - Ontology

DRAFT, May 2015

## Covers

### Front

A New Ontlogy of Automated Threats to Web Applications

### Back

The OWASP Automated Threats to Web Applications Project creates information and other resources for architects, developers, testers, and others to help web application owners defend against automated threats.

https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications

## Preface

Most applications are not under a constant state of compromise, whether or not there are weaknesses and unpatched vulnerabilities present. However, attackers are still using the software in a manner that causes significant pain to both the owners/operators, and sometimes also the users. 

Previous work on [OWASP AppSensor](https://www.owasp.org/index.php/OWASP_AppSensor_Project) (application-specific attack detection and response) has identified 50 or so types of [detection points](https://www.owasp.org/index.php/OWASP_AppSensor_Project#tab=Detection_Points), and I had speculated about which detection points would be most beneficial to implement first. All AppSensor detection points should have an extremely low false positive attack detection rate so that normal usage is never flagged as malicious, but I wondered which detection points might identify attackers sooner than others - before they targeted some potential vulnerability. What I needed was a list of threats, and probably automated threats, which are not attempting to exploit individual vulnerabilities (typically implementation bugs or misconfigurations). In other words, what are attackers doing if there are not common vulnerabilities like injection and access control flaws?

And here I came across a blocker - there did not seem to be a clear categorisation and quantification of these actual automated threats most web application owners have to deal with day-to-day. These are also not included in "breach" statistics and discussions, even though there are breaches of security occurring. Instead there is a greater focus on individual types of weaknesses and vulnerabilities, root cause analysis of breaches, and much from vendors about product/service capabilities. But some business owners are submerged in technical details leading to a lack of comprehension the link from security requirements, security issues during development, deployment and operation, and the impact. In my consulting work I had also observed too great a focus on individual weaknesses/vulnerabilities in technical assurance activities, especially where the severity rating of each issue in isolation fails to provide the overall picture. For example, it is common for a number of individual, low or medium severity issues to contribute to a much more significant business impact.

I was also concered about misuse of valid functionality, as this is an aspect where early design decisions have a significant effect on operational risk.

In order to quantify the threats, it is necessary to be able to name them, and that did not seem to exist in the usual dictionaries and classifications. Therefore I decided to produce an ontology of automated threats from the perspective of  defenders. I was aware of the magnitude of task of creating identifers, and had read advice from contributors to Mitre and First documents. Consequently to contain the scope somewhat, I decided to focus soley upon web applications.

The first output - an ontology - is provided in this document. And now I am moving on to produce other materials for web application defenders.

Colin Watson
May 2015

## Introduction

### Background

There is a significant body of knowledge about application vulnerability types, and some general consensus about identification and naming. But issues relating to the misuse of valid functionality, which may be related to design flaws rather than implementation bugs, are less well defined. Yet these problems are seen day-in, day-out, by web application owners.
Excessive abuse of functionality is commonly mistakenly reported as application denial-of-service (DoS) attacks such as HTTP-flooding or application resource exhaustion, when in fact the DoS is a side-effect. Some examples are blog & comment spam, fake account creation, password cracking, web scraping, etc. Most of these problems seen regularly by web application owners are not listed in any OWASP Top Ten or other top issue list or dictionary.

This has contributed to inadequate visibility, and an inconsistency in naming such threats, with a consequent lack of clarity in attempts to address the issues.

The OWASP Automated Threats to Web Applications Project has completed a review of reports, academic and other papers, news stories and vulnerability taxonomies/listings to identify, name and classify these attacks – threat events to web applications that are undertaken using automated actions. The initial aim is to produce an ontology providing a common language for developers, architects, operators, business owners, security engineers, purchasers and suppliers/vendors, to facilitate clear communication and help tackling the issues.
The project also intends to identify symptoms, mitigations and controls in this problem area. Like all OWASP outputs, everything is free and published using an open source license. 

### Requirement
Web applications are subjected to unwanted automated usage – day in, day out. Often these events relate to misuse of inherent valid functionality, rather than the attempted exploitation of unmitigated vulnerabilities. Also, excessive misuse is commonly mistakenly reported as application denial-of-service (DoS) like HTTP-flooding, when in fact the DoS is a side-effect instead of the primary intent. Some examples commonly referred to are:

* Account enumeration
* Click fraud
* Comment spam
* Content scraping
* etc.

Frequently these have sector-specific names. Most of these problems seen regularly by web application owners are not listed in any OWASP Top Ten or other top issue list. Furthermore, they are not enumerated or defined adequately in existing dictionaries. These factors have contributed to inadequate visibility, and an inconsistency in naming such threats, with a consequent lack of clarity in attempts to address the issues.

Without sharing a common language between devops, architects, business owners, security engineers, purchasers and suppliers/vendors, everyone has to make extra effort to communicate clearly. Misunderstandings can be costly. The adverse impacts affect the privacy and security of individuals as well as the security of the applications and related system components.

### Scope

The aim is to create a listing of vendor-neutral and technology agnostic terms that describe real-world automated threats to web applications, at a level of abstraction that application owners can relate to. These terms are threat events to web applications undertaken using automated actions.

The focus is on abuse of functionality - misuse of inherent functionality and related design flaws, some of which are also referred to as business logic flaws. There is almost no focus on implementation bugs. It is not that the latter are not the target for attacks, but there is much more knowledge published in that area with a greater agreement on terminology. All the scenarios identified must require the web to exist for the threat to be materialised. Many of the scenarios have impacts upon the organisation that owns or operates web applications, but some scenarios have impacts more focused on individuals or other bodies. An attack that can be achieved without the web is out of scope.

Threat events to web applications undertaken using automated actions.

An attack that can be achieved without the web is out of scope.

### Use cases

The ontology and supporting materials are expected to be useful for:

* Defining application security requirements* Sharing intelligence within a sector* Exchanging threat data between CERTs* Labelling penetration test findings* Documenting service acquisition needs* Characterising vendor services.

These are expanded upon in Appendix C.

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

OWASP Top 10 Risks

OWASP Top Ten Controls


## The Ontology

### Introduction

The research and analysis and discussions with peers, completed over three months, whittled down the threat actions to a smaller core list.

The names used, combibed with their definining characteristics, are taken from existing usage where possible. However, terminology is not used consistently within the literature sources reviewed, and also in some cases it bwas necessary to use a more generic term that caputures the wider idea instaed of an individual common name. Furthermore, the intended outcomes of the threat action are usually known at the time of the action taking place. For example, is the creation of a fake account intended for distributing malware in user-generated content, or to manipulate search engine scoring, or to influnce other users, or to explore the authenticated parts of the application.



### The list

* ???
* 




Full details of each threat action are shown in Appendix A, with mappings to other dictionaries and lists in Appendix B.


### Notes on some names

Some ontology names are much more specific than others, where the threat is cross-sector and it is reported to occur frequently. Others are larger buckets which cannot be broken down easily without sharding the threat actions into a multitude of sector-specific and function-specific examples.







### Near misses (appendix?)

A small number of threat actions were removed from the final ontology during review based on discussions with peers and website owners. Others may have alternative views, so they are listed below.

#### Account aggregation

"Account Aggregation" was initially defined as user account aggregation where credentials from multiple individual user accounts are centralised into another application, with each user's permission. The aggregating application may be used by one user to merge information from multiple applications, or alternatively merge information of many users of a single application. This is commonly used for aggregating social media accounts, email accounts and financial accounts in order to obtain a consolidated overview, provide integrated reporting/analysis, and simplify usage and consumption by the user and/or their professional advisors. The aggreagting application may include making changes to account properties and interacting with the aggregated application's functionality. Some terms used elsewhere include password manager, financial account aggregator, client aggregator, or simply data aggregator.

On consideration, it was felt that the provision of user credentials to the aggregator was not in itself an automated threat, and the resultant effects were indistinguishable from other information aggregation. The effects on the ability for the web application owner to interact with the end user may be enhanced or reduced depending upon the circumstances, and thius may or may not be desirable. Therefore, it was decided to incorporate "Account Aggregation" together with other types of data collection, along with data aggregation where information is republished on the web elsewhere, in a single threat action "Scraping", as the.

#### Application consumption

This threat action with a temporary name invloves the misuse of the application to perform calculations, or process data, or perform other actions against other applications, hosts, or in the physical world i.e. unauthorised real-time consumption of a normal application as if it were an API. Unlike data harvesting, where information is gathered once or periodically, in processs  consumption the application is used on-demand by another system to provide calculated output, send requests to another application, or possibly affect physical assets the application provides direct control over. For example the application might be used to generate images or other files based on user input. In the second case, the application checks user submitted data (e.g. hostname, email address) by undertaking a reverse lookup, ping back or a reputation service check, contributing to a denial of service attack against that other host.

In all of these, there seemed to be a close similarlity with "Account Aggregation" above and thus was eventually concluded to be another example of "Data Aggregation".

#### Application worms

"Application Worms", also called cross-site scripting worms, are purely a combination of two different implementation flaws – cross-site request forgery (CSRF) and cross-site scripting (XSS). Additionally, the automation is undertaken by the web application itself inconjunction with often normal usage by innocent users. This did not fdall within the defined scope.

#### Asset stripping

"Asset Stripping" was thought of as the removal of application stored non-data assets using compromised accounts and sessions, including data theft, collecting micro deposits, and collecting refunds. However this asset removal, extraction or copying from applications used as repositories is no different from other data harvesting at the time of extraction. The only difference is the assets have value in other non-application contexts and may include fiat money, credit, refunds, financial instruments, reputation, virtual assets (e.g. status, score, virtual currency, identity), awards and points, and possible physical assets the application provides contol over. But this value is often very subjective.

Since these are data, it was considered this threeat action was actually part of scraping. The objectives of the attacker and consequences are data and application specific. It was therefore not included as a separate term.

#### Code modification

"Code Modification" is when the application logic is changed by modification of the source code, or the executing code, or the configuration, or combinations of these. The kinds of attacks included are malicious software download, malicious software update, advert injection, DOM modification, web browser tools, form tampering, malicious software implanted, backdoor addition, shared data manipulation, use of untrusted code, memory modification, Angular JS attack, configuration data modification, exposed reflection, reflection injection, autobinding, and Rich Internet Application (RIA) attacks.

The issue is made more significant with the growing use of client side code. But it was felt these threats were related to lack of integrity checks, particularly during development and distribution, rather than being typical automated threats, and therefore not included in this ontology.

#### Form hijacking

At the start it was thought "Form Hijacking", such as email spam, form to Email spam, SMS spam, use as a spam relay, and unsolicited bulk email, would be an ideal candidate for the threat action ontology. But again it was realsied this is an implementation flaw that leverages vulnerabilities produced when an web server fails to validate input, and thus does not fit into this ontology.

#### Man in the Browser

"Man in the Browser" (MitB) where the attacker controls the user's web browser, so that information being transferred can be observed, intercepted and manipulated. The most well-known use case is to undertake financial fraud, and are the result of compromise of the user's device by a banking trojan, such as URLzone, Torpig, and Zeus. However, MitB can alos be used for advert injection. Some less ****elaborate*** versions have been labelled Boy in the Browser (BitB).

#### Reverse engineering

"Reverse Engineering", exercising an application or part of an application with the intent to gain insight how it is constructed and operates, was decided to be an intended outcome of a combination of other threat acrtions - typically "Scraping" and "Footprinting". These two existing threat actions already include the testing and collection of evidence to determine the underlying logic, structures, algorithms, functions, methods and secrets of the application. 

The purpose is understand the inner workings, and may be used to detemine business logic such as pricing models, reproduce the application elsewhere, or to assist with vulnerability exploitation and data compromise. Thus, as an outcome it is not valid part of the ontology.

## Usage of the ontology



## Forward plan





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


## Appendix A - Ontology

TODO (being drafted in different format)


## Appendix B - Mappings

TODO




## Appendix C - Use Case Scenarios

### Defining application security requirements

### Sharing intelligence within a sector

Unlimited Innovations Inc provides ecommerce solutions to a range of international retailers and participates in the Retail Cyber Intelligence Sharing Center (R-CISC). Unlimited already builds into its software continuous monitoring capabilities and decides to provide an optional enhancement so that participating retailers could choose to share their misuse event data between each other, to benefit from the combined threat intelligence. Rather than sharing large quantities of  low-level data, Unlimited aggregate information and broadcast validated and categorised threat data amongst the participating companies. Automation attacks are classified according to the [ONTOLOGY] so that each receiving party understands the nature of the threat. Even for retailers that do not want to take part of this information sharing can benefit, since the classified information is made available to internal business management in the form of an easy-to-comprehend monitoring dashboard. The information gathered is also used by the retailers to feed into their business information management systems.
### Exchanging threat data between CERTs

TODO
### Labelling penetration test findings

Specialist application security penetration testing firm Cherak Industries Pte Ltd works primarily for financial services companies in the banking and insurance sector and is looking to expand its business throughout Asia. Cherak has some innovative pen test result reporting systems which integrate with client software fault and vulnerability tracking systems, and it is always on the look out for methods to provide additional value to its clients. Cherak has identified that pen test clients would benefit from help with understanding the effects of combinations of vulnerabilities and has decided to utilise the [ONTOLOGY] to define and explain the automation-related threats. The individual vulnerabilities were scored as normal using CVSSv2 and v3, the matching CWEs identified, and mitigations in place documented. In addition Cherak used the [ONTOLOGY] to help create a new section in the executive summary to explain how combinations of the issues found could lead to automation threats and the possible technical and business impacts. For example, an assessment for one client had identified weaknesses in authentication so that [CREDENTIAL STUFFING] is an automation threat. The defined [ONTOLOGY] entry name and ID were provided so that the client's technical staff could refer to additional information on the OWASP website.
### Documenting service acquisition needs

Falstone Paradise Inc is concerned about malicious use of their portfolio of hotel and resort websites. The majority of the websites use a shared application platform, but there are some unique applications and a large number of other micro-sites, some of which use generic content management systems such as Wordpress and Drupal. Falstone Paradise has identified that its IT operations team are spending too much time dealing with the effects of automated misuse, such as cleaning up data, resetting customer accounts and providing extra capacity during attacks. Furthermore, the unwanted automation is also causing some instabilities leading to negative feedback from customers. Therefore Falstone Paradise has decided to go out to the security marketplace to identify, assesses and select products or services that might help address these automation issues for all its websites. Its buying team worked with their colleagues in information technology to write the detailed requirements in an Invitation to Tender (ITT) document. This described the types of attacks its web applications are receiving, the frequency of occurrence and magnitudes. These are defined according to the [ONTOLOGY] so that vendors do not misunderstand the requirements, and so that each vendor's offering could be assessed against each individual type of automation threat. 
### Characterising vendor services

TODO

## Appendix D - Attack Descriptions and Test Cases

TODO

## Appendix E - Automated Attack Defense Cheat Sheet

TODO: (being drafted as separate document)



