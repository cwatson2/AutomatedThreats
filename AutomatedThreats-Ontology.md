# Automated Threats to Web Applications - Handbook

DRAFT, 12th June 2015

## Covers

### Front

The Automated Threat Handbook
Web Applications

Version 1.0

### Back

This document is an output of the OWASP Automated Threats to Web Applications Project . The project creates information and other resources for architects, developers, testers, and others to help defend against automated threats.

[https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications](https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications)


(ISBN Code)

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

### Objectives

The initial objectives were:

* Provide definition of "automated threat" 
* Create a common vocabulary, and relationships, of automated threats which maintains consistency with existing literature 

MOVE Any inconsistencies with existing literature should be accompanied with rationale


### Scope

The aim is to create a listing of vendor-neutral and technology agnostic terms that describe real-world automated threats to web applications, at a level of abstraction that application owners can relate to. These terms are threat events to web applications undertaken using automated actions.

The focus is on abuse of functionality - misuse of inherent functionality and related design flaws, some of which are also referred to as business logic flaws. There is almost no focus on implementation bugs. It is not that the latter are not the target for attacks, but there is much more knowledge published in that area with a greater agreement on terminology. All the scenarios identified must require the web to exist for the threat to be materialised. Many of the scenarios have impacts upon the organisation that owns or operates web applications, but some scenarios have impacts more focused on individuals or other bodies. An attack that can be achieved without the web is out of scope.

Threat events to web applications undertaken using automated actions.

An attack that can be achieved without the web is out of scope.

Focus for threat events are scenarios which are seen commonly by real operating web applications, and are multi-step and/or highly iterative and/or multiple weaknesses involved, and not primarily about events that relate to the tool-based exploitation of single-issue vulnerabilities of individual web applications.


### Use cases

The ontology and supporting materials are expected to be useful for:

* Defining application security requirements* Sharing intelligence within a sector* Exchanging threat data between CERTs* Labelling penetration test findings* Documenting service acquisition needs* Characterising vendor services.

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

OWASP Top 10 Risks

OWASP Top Ten Controls


## The Ontology

### Introduction

The research and analysis and discussions with peers, completed over three months, whittled down the threat actions to a smaller core list.

The names used, combibed with their definining characteristics, are taken from existing usage where possible. However, terminology is not used consistently within the literature sources reviewed, and also in some cases it bwas necessary to use a more generic term that caputures the wider idea instaed of an individual common name. Furthermore, the intended outcomes of the threat action are usually known at the time of the action taking place. For example, is the creation of a fake account intended for distributing malware in user-generated content, or to manipulate search engine scoring, or to influnce other users, or to explore the authenticated parts of the application.

The ontology is a list of threat event scenarios (when a threat agent acts against an asset, partially ordered in time) by software, causing a divergence from accepted behavior producing one or more undesirable effects on a web application, and which excludes tool-based exploitation of single-issue vulnerabilities.

### The list

* ???
* 




Full details of each threat action are shown in Appendix A, with mappings to other dictionaries and lists in Appendix B.

To enable internal cross-referencing and reference from elsewhere, each threat event has been given an idententivation (ID) value. This is a three digit number prefixed by a hyphen and an abbreviation for OWASP Automated Threat (OAT) e.g. OAT-015. The IDs were randomly assigned in an attempt to stop the ontoloy being seen as an ordered list, and also to ensure that neighbouring items are not necessarily related. Other cross-referencing is provided. Currently IDs 001 to 019 are used, and it is expected the total number should be <<50, unless in the future many sub-items are added. Three digits, rather than two, were alloted in case the first dogit is used for sometingbelse in future e.g. perhaps mobile application automated threat events could be 1xx, and 2xx for embedded software, etc. 

(add some text from Appendix A Key to describe others parts of these pages)

### Notes on the names

In all cases, "automated web application" could be used as a prefix to each name. Thus ,for example, **OAT-012 Cashing Out** is concerned only with using web applications to obtain cash or goods. The ontology's scope excludes cashing out using ATMs for example. When referencing the terms in other contexts it may be useful to ensure this scope is identified.

Whenever possible an existing term already used in literature or industry usage was preferred. But in many cases it was difficult to identify this, and in some cases a more generic version had to be used. Some ontology names are much more specific than others, where the threat is cross-sector and it is reported to occur frequently. Others are larger buckets which cannot be broken down easily without sharding the threat actions into a multitude of sector-specific and function-specific examples.

### Mappings

tables in appendix???

### Timing, duration and frequency



### Magnitude of impact

Events related to automated threats can have impacts on more than just the application owner. Individuals, third parties and even society can be adversely affected. This ontology does not attempt to rank the threat events in terms of impact since it will be organisation, data, threat actor and victim-perspective specific.

### The perpetrators

During the early stateges of the ontology's creation, it was believed it would be possible to suggest which threat actors might be most likely to initiate the threat event. These threat agents might be groups like competitors, journalists, petty criminals, organised crime, nation states, etc and of course users such as citizens, clients, customers and employees. However, on further inspection the threat agents appear to be more closely related to the type of data, and thus sector, rather than the particular threat event. Consequently, it is believes threat agent should be re-considered in future sector-specific views of the ontology.

Furthermore, some threat events may be undertaken by, or with the knowledge or implicit support of, by application opwners. For example, search engine indexing is generally encouraged due to the benefit of increased user traffic, or automated monitoring of web applications may be commissioned, or excessive account creation might contribute to enhanced market reputation when promoting the size of its customer base, or the application owner with hosted advertisements could receive additional income for Ad Fraud.

### Fraud and legality 

In general the ontology tries to avoid the use of judgmental words like fraud. But in one case, the industry accepted term for the three event includes this word. 

In legal terms, whether an action is fraudulent depends on legislation and this jurisdiction. Some of the events in this ontology may be illegal actions in some jurisdictions. This will also depend upon the types of data handled, regulation of the application and its owner and application specific mandates like terms of use.







### Near misses (appendix?)

A small number of threat actions were removed from the final ontology during review based on discussions with peers and website owners. Others may have alternative views, so they are listed below.

#### Account aggregation

"Account Aggregation" was initially defined as user account aggregation where credentials from multiple individual user accounts are centralised into another application, with each user's permission. The aggregating application may be used by one user to merge information from multiple applications, or alternatively merge information of many users of a single application. This is commonly used for aggregating social media accounts, email accounts and financial accounts in order to obtain a consolidated overview, provide integrated reporting/analysis, and simplify usage and consumption by the user and/or their professional advisors. The aggreagting application may include making changes to account properties and interacting with the aggregated application's functionality. Some terms used elsewhere include password manager, financial account aggregator, client aggregator, or simply data aggregator.

On consideration, it was felt that the provision of user credentials to the aggregator was not in itself an automated threat, and the resultant effects were indistinguishable from other information harvesting. The effects on the ability for the web application owner to interact with the end user may be enhanced or reduced depending upon the circumstances, and thius may or may not be desirable. Therefore, it was decided to incorporate "Account Aggregation" together with other types of data collection, along with data aggregation where information is republished on the web elsewhere, in a single threat action "Scraping".

#### Application consumption

This threat action with a temporary name invloves the misuse of the application to perform calculations, or process data, or perform other actions against other applications, hosts, or in the physical world i.e. unauthorised real-time consumption of a normal application as if it were an API. Unlike data harvesting, where information is gathered once or periodically, in processs  consumption the application is used on-demand by another system to provide calculated output, send requests to another application, or possibly affect physical assets the application provides direct control over. For example the application might be used to generate images or other files based on user input. In the second case, the application checks user submitted data (e.g. hostname, email address) by undertaking a reverse lookup, ping back or a reputation service check, contributing to a denial of service attack against that other host.

In all of these, there seemed to be a close similarlity with "Account Aggregation" above and thus was eventually concluded to be another example of "Data Aggregation".

#### Application worms

"Application Worms", also called cross-site scripting worms, are purely a combination of two different implementation flaws – cross-site request forgery (CSRF) and cross-site scripting (XSS). Additionally, the automation is undertaken by the web application itself inconjunction with often normal usage by innocent users. This did not fdall within the defined scope.

#### Asset stripping

"Asset Stripping" was thought of as the removal of application stored non-data assets using compromised accounts and sessions, including data theft, collecting micro deposits, and collecting refunds. However this asset removal, extraction or copying from applications used as repositories is no different from other data harvesting at the time of extraction. The only difference is the assets have value in other non-application contexts and may include fiat money, credit, refunds, financial instruments, reputation, virtual assets (e.g. status, score, virtual currency, identity), awards and points, and possible physical assets the application provides contol over. But this value is often very subjective.

Since these are data, it was considered this threeat action was actually part of Scraping. The objectives of the attacker and consequences are data and application specific. It was therefore not included as a separate term.

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

#### Amplification of DoS????

???

#### Attack platform???

???

## Usage of the ontology


The author hopes this ontology with its industry cross-referencing may be of help in contributing to Mitre's Common Weakness Risk Analysis Framework (CWRAF) and Common Attack Pattern Enumeration and Classification (CAPEC).



## Forward plan

Sector-specific guides:

* Highest risk threat events
* Attacker motivations

Pages 2s:

* Mitigations
* Symptoms
* For builders
* For defenders
* Metrics

Automated Threat Cheat Sheet

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

## Project outputs

The wiki page for OWASP Automated Threats to Web Applications Project is:

[https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications](https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications)

The project's mailing list is:

[https://lists.owasp.org/mailman/listinfo/automated_threats_to_web_applications](https://lists.owasp.org/mailman/listinfo/automated_threats_to_web_applications)

The original versions of this handbook are maintained at these locations:

* PDF
  * Print ready high resolution [TBD]()
  * Low resolution [TBD]()
* Adobe InDesign [TBD]()

Other working materials and outputs are:

* Overview, 2 page PDF []()
* Survey sheet used at Appsec EU 2015, PDF [https://www.owasp.org/index.php/File:Automation-questionnaire-1v0.pdf](https://www.owasp.org/index.php/File:Automation-questionnaire-1v0.pdf)
* Summary threats and attacks extracted during the research phase, large scale PDF [https://www.owasp.org/index.php/File:Automated-threats.pdf](https://www.owasp.org/index.php/File:Automated-threats.pdf)




## Appendix A - Use Case Scenarios

### Defining application development security requirements

Cinnaminta SpA intends to build and launch a new multi-lingual and multi-currency ecommerce website. The development will be outsourced and Cinnaminta has been working on the functional design document. Amongst many other requirements, the application security specification requires that the website must not include any vulnerabilities identified in PCI DSS v3.1 Requirement 6.5, nor any other vulnerabilities that could affect the protection of payment cardholder data. Cinnaminta specifies that the website's payment functions must not be susceptiple to the threat events **OAT-001 Carding** or **OAT-010 Card Cracking** defined in the **OWASP Automated Threat Handbook**. In addition the application must interact with the company's existing fraud detection system to counter **OAT-012 Cashing Out**. Development houses responding to the Invitation To Tender (ITT) use the ontology to focus their bid responses to these aspects appropriately.
### Sharing intelligence within a sector

Unlimited Innovations Inc provides ecommerce solutions to a range of international retailers and participates in the Retail Cyber Intelligence Sharing Center (R-CISC). Unlimited already builds into its software continuous monitoring capabilities and decides to provide an optional enhancement so that participating retailers could choose to share their misuse event data between each other, to benefit from the combined threat intelligence. Rather than sharing large quantities of low-level data, Unlimited Innovations aggregate information and broadcast validated and categorised threat data amongst the participating companies. Automation attacks are classified according to the threat events defined in the **OWASP Automated Threat Handbook** so that each receiving party understands the nature of the threat. Even for retailers that do not want to take part of this information sharing can benefit, since the classified information is made available to internal business management in the form of an easy-to-comprehend monitoring dashboard. The information gathered is also used by the retailers to feed into their business information management systems.
### Exchanging threat data between CERTs

National Computer Emergency Response Teams (CERTs) recognise that sharing of information from local detection can contribute to worldwide prevention of cyber attacks. Despite advances in cooperation between CERTs, anything to increase continuity and interoperatbility such as standards for data exchange is encourage. CERT Zog is concerned about the sparsity of application-specific data it receives, and also the classification of that data. It has a particular concern about attacks and breaches that affect sectors defined in Zog's 2015 national cyber security strategy. CERT Zog and its adjoining neighbour CERT Tarset agree to use threat events defined in the **OWASP Automated Threat Handbook** to add greater context to existing solutions being used for threat data exchange between the CERTs. The programme also collects sector meta data, so that all organisations within these can benefit from the centralised intelligence.
### Enhancing application penetration test findings

Specialist application security penetration testing firm Cherak Industries Pte Ltd works primarily for financial services companies in the banking and insurance sectors, and is looking to expand its business throughout Asia. Cherak has some innovative pen test result reporting systems which integrate with client software fault and vulnerability tracking systems, and it actively looks for methods to provide additional value to its clients. Cherak has identified that pen test clients would benefit from help to understand the effects of combinations of vulnerabilities, especially design flaws, and has decided to utilise the **OWASP Automated Threat Handbook** to define and explain the automation-related threats. The individual vulnerabilities were scored as normal using CVSSv2 and v3, the matching CWEs identified, and mitigations in place documented. In addition Cherak use the threat events **OAT-001 Carding** or **OAT-010 Card Cracking** defined in the **OWASP Automated Threat Handbook** to help create a new section in the executive summary that explains how combinations of the issues found could lead to automation threats and the possible technical and business impacts. For example, an assessment for one client had identified weaknesses in authentication so that there is a risk of **OAT-008 Credential Stuffing**. The defined This identifier was provided to the client so its technical staff could refer to additional information on the OWASP website.
### Specifying service acquisition needs

Falstone Paradise Inc is concerned about malicious use of their portfolio of hotel and resort websites. The majority of the websites use a shared application platform, but there are some unique applications and a large number of other micro-sites, some of which use generic content management systems such as Wordpress and Drupal. Falstone Paradise has identified that its IT operations team are spending too much time dealing with the effects of automated misuse, such as cleaning up data, resetting customer accounts and providing extra capacity during attacks. Furthermore, the unwanted automation is also causing some instabilities leading to negative feedback from customers. Therefore Falstone Paradise has decided to go out to the security marketplace to identify, assesses and select products or services that might help address these automation issues for all its websites. The buying team worked with their colleagues in information technology to write the detailed requirements in an Invitation to Tender (ITT) document. This described the types of attacks its web applications are receiving, the frequency of occurrence and magnitudes. These are defined according to the **OWASP Automated Threat Handbook** so that vendors do not misunderstand the requirements, and so that each vendor's offering could be assessed against the particular automation threat events of concern.
### Characterising vendor services

Better Best Ltd has developed an innovative tecehnology to help gaming companies defend against a range of automated threats that can otherwise permit cheating and distortion of the game, leading to disruption to normal players. The solution can be deployed on premises, but is also available in the cloud as a service. But Better Best is finding difficulty explaining its solution in the market place, especillay since it does not fit into any conventional product category. Better Best decide to use the terminology and threat events lisyed in the **OWASP Automated Threat Handbook** to define their product's capabilities. They hope this will provide some clarity to their offering, and also demonstrate how their product can be used to replace more than one other conventional security device. Better Best document how thor product is used to protect against **OAT-006 Expediting**, **OAT-005 Scalping**, **OAT-016 Skewing** and **OAT-013 Sniping**. The requirements are specified in terms of the threat events, rather than in terms of particular products and service categories.


## Appendix B - Ontology List and Mappings

TODO



## Ontology Reference

This section contains the full details of each threat event in the ontology.

### Key

Categorisations:

* Sectors Targeted - Sectors that are targted more commonly than others for the specific threat event, are highlighted in amber. This is currently just the author's opionion, but the project is seeking information to define this aspect more accurately.
* Parties Affected - Whether individuals, groups of people, the application owner and other parties are most often affected adversely by the threat event. The threat event may affect other parties depending upon the application and its data. The parties affected, exclude subsequent further misuse.
* Data Commonly Misused - The types of data are web application specific. However some threat events are more likely to occur for certain data types.

Cross-references:

* CAPEC - Best full and/or partial match CAPEC category IDs and/or attack pattern IDs.

The best match is often the category CAPEC-210 Abuse of Functionality. Only Credential Cracking, Denial of Service and Scraping map to multiple more detailed CAPEC attack pattern IDs, and in these case the most general ones are listed only. The best example of good coverage by both this ontologfy and CAPEC is Credential Cracking, where the latter has three attack patterns defined that completely cover the automated threat event. Based on this comparison it was found that CAPEC categories are often too broad, or the attack patterns are missing or much more detailed than this ontology.

* WASC - 


* OWASP - 



### OAT-001 CardingMultiple payment authorisation attempts used to verify the validity of bulk stolen payment card data.

#### Description

Lists of full credit and/or debit card data are tested against a merchant's payment processes to identify valid card details. The quality of stolen data is often unknown, and Carding is used to identify good data of higher value. Payment cardholder data may have been stolen from another application, stolen from a different payment channel, or acquired from a criminal marketplace.

When partial cardholder data is available, and the expiry date and/or security code are not known, the process is **OAT-010 Card Cracking** instead. The use of stolen cards to obtain cash or goods is **OAT-012 Cashing Out**.

#### Other Names and Examples

Card stuffing; Credit card stuffing; Card verification

#### See Also

* **OAT-010 Card Cracking**
* **OAT-012 Cashing Out**


### OAT-002 Token Code CrackingMass enumeration of coupon numbers, voucher codes, discount tokens, etc.

#### Description

Identification of valid token codes providing some form of user benefit within the application. The benefit may be a cash alternative, a non-cash credit, a discount, or an opportunity such as access to a limited offer.

For cracking of usernames, see **OAT-007 Credential Cracking** instead.

#### Other Names and Examples

Coupon guessing; Voucher, gift card and discount enumeration

#### See Also

* **OAT-007 Credential Cracking**
* **OAT-011 Scraping**
* **OAT-012 Cashing Out**

### OAT-003 Ad FraudFalse clicks and fraudulent display of web-placed advertisements.

#### Description

Falsification of the number of times an item such as an advert is clicked on, or the number of times an advertisement is displayed. Performed by owners of web sites displaying ads, competitors and vandals.

See **OAT-016 Skewing** instead for similar activity that does not involve web-placed advertisements.

#### Other Names and Examples

Advert fraud; Adware traffic; Click bot; Click fraud; Hit fraud; Impression fraud; Pay per click advertising abuse; Phoney ad traffic

#### See Also

* **OAT-016 Skewing**


### OAT-004 FingerprintingElicit information from the web, application and database servers about the supporting software and framework types and versions.

#### Description

Specific requests are sent to the application eliciting information in order to profile the application. This probing typically examine HTTP header names and values, session identifier names and formats, contents of error page messages, URL path case sensitivity, URL path patterns, file extensions, and whether software-specific files and directories exist. Fingerprinting is often reliant on information leakage and this profiling may also reveal some network architecture/topology. The fingerprinting may be undertaken without any direct usage of the application e.g. by quering a store of exposed application properties such as held in a search engine's index.

Fingerprinting seeks to identity application components, whereas **OAT-018 Footprinting** is a more detailed analysis of how the application works.

For data extraction, see **OAT-011 Scraping** instead.

#### Other Names and Examples

Google dorking; Google hacking; Shodaning; Target acquisition; Target scanning; Finding potentially vulnerable applications; Reconnaissance; URL harvesting; Web application fingerprinting

#### See Also

* **OAT-011 Scraping**
* **OAT-018 Footprinting**


### OAT-005 ScalpingObtain limited-availability and/or preferred goods/services by unfair methods.

#### Description

Mass acquisition of goods or services using the application in a manner that a normal user would be unable to undertake manually.

Although Scalping may include monitoring awaiting availability of the goods or services, and then rapid action to beat normal users to obtain these, Scalping is not a "last minute" action like **OAT-013 Sniping**, nor just related to automation on behalf of the user such as in **OAT-006 Expediting**. This is because Scalping includes the additional concept of limited availability of sought-after goods or services, and is most well known in the ticketing business where the tickets acquired are then resold later at a profit by the scalpers/touts. This can also lead to a type of user denial of service since the goods or services become unavailable rapidly.

#### Other Names and Examples

Bulk purchase; Purchase automaton; Purchase bot; Restaurant table/hotel room reservation speed-booking; Queue jumping; Sale stampede; Ticket resale; Ticket scalping; Ticket touting

#### See Also

* **OAT-006 Expediting**
* **OAT-013 Sniping**
* **OAT-015 Denial of Service**


### OAT-006 ExpeditingPerform actions to hasten progress of usually slow, tedious or time-consuming actions on behalf of a person.

#### Description

Using speed to violate explicit or implicit assumptions about the application's normal use to achieve unfair individual gain, often associated with deceit and loss to some other party.

In contrast to **OAT-016 Skewing** which affects metrics, Expediting is purely related to faster progression through a series of application processes. And **OAT-017 Spamming** is different to Expediting, since the focus of spam is to add information, and may not involve the concept of process progression.

#### Other Names and Examples

Algorithmic trading; Automated stock trading; Betting automation; Game playing automation; Gaming bot; Gold farming; *Financial instrument dealing;* High frequency trading; Purchasing automation; Travel ticketing automation; Trading automation; Virtual wealth generation bot

#### See Also

* **OAT-005 Scalping**
* **OAT-013 Sniping**
* **OAT-016 Skewing**
* **OAT-017 Spamming**


### OAT-007 Credential CrackingIdentify valid log in credentials by trying different values for usernames and/or passwords.

#### Description

Brute force, dictionary (word list) and guessing attacks used against authentication processes of the application to identify valid account credentials. This may utilise common usernames or passwords, or involve initial username evaluation. 

The use of stolen credential sets (paired username and passwords) is **OAT-008 Credential Stuffing**.

#### Other Names and Examples

Brute force, dictionary and guessing attacks; Brute-force attacks against sign-in; Brute forcing log-in credentials; Brute-force password cracking; Cracking login credentials; Password brute-forcing; Password cracking; Reverse brute force attack; Username cracking; Username enumeration

#### See Also

* **OAT-002 Token Code Cracking**
* **OAT-008 Credential Stuffing**
* **OAT-019 Account Creation**


### OAT-008 Credential StuffingMass log in attempts used to verify the validity of stolen username/password pairs.

#### Description

Lists of authentication credentials stolen from elsewhere are tested against the application's authentication mechanisms to identify whether users have re-used the same log in credentials. The stolen usernames (often email addresses) and password pairs could have been sourced directly from another application by the attacker, purchased in a criminal marketplace, or obtained from publicly available breach data dumps.

Unlike **OAT-007 Credential Cracking**, Credential Stuffing does not involve any brute-forcing or guessing of values; instead credentials sets used in other applications are being tested for validity.

#### Other Names and Examples

Account checker attack; Account checking; Account takeover; Account takeover attack; Login Stuffing; Password list attack; Password re-use; Stolen credentials; Use of stolen credentials

#### See Also

* **OAT-007 Credential Cracking**
* **OAT-019 Account Creation**


### OAT-009 CAPTCHA BypassSolve anti-automation tests.

#### Description

Completely Automated Public Turing test to tell Computers and Humans Apart (CAPTCHA) challenges are used to distinguish normal users from bots. Automation is used in an attempt to analysis and determination the answer to visual and/or aural CAPTCHA tests and related puzzles. Apart from conventional visual and aural CAPTCHA, puzzle solving mini games or arithmetical exercises are sometimes used. Some of these may include context-specific challenges.

The process that determines the answer may utilise tools to perform optical character recognition, or matching against a prepared database of pre-generated images, or using other machine reading, or human farms.

#### Other Names and Examples

Breaking CAPTCHA; CAPTCHA breaker; CAPTCHA breaking; CAPTCHA decoding; CAPTCHA solver; CAPTCHA solving; Puzzle solving

#### See Also

* **OAT-006 Expediting**
* **OAT-011 Scraping**


### OAT-010 Card CrackingIdentify missing expiry dates and security codes for stolen payment card data by trying different values.

#### Description

Brute force attack agsinst application payment card process to identify the missing values for start date, expiry date and card security code (CSC), referred to in many ways including card validation number 2 (CVN2), card validation code (CVC), card verification value (CV2) card identification number (CID).

When these values are known as well as the Primary Account Number (PAN), **OAT-001 Carding** is used to validate the details, and **OAT-012 Cashing Out** to obtain goods or cash.

#### Other Names and Examples

Brute forcing credit card information; Card brute forcing; Credit card cracking

#### See Also

* **OAT-001 Carding**
* **OAT-012 Cashing Out**


### OAT-011 ScrapingCollect application content and/or other data for use elsewhere.

#### Description

Collecting accessible data and/or processed output from the application. Some scraping may use fake or compromised accounts, or the information may be accessible without authentication. The scraper may attempt to read all accessible paths and parameter values for web site pages and web APIs, collecting the responses and extracting data from them. In some forms of Scraping like account aggregation, part of the Scraping may occur in real time, and part may be more periodic in nature.

Commonly collected data is page content and data such as account credentials, biometric data, business information, copies of physical documents, email addresses, facial photographs, identities, intellectual property, payment cardholder data, security secrets, trade secrets, usernames, and other personal data. Some of these may be considered of standalone value such as reputation, virtual assets (e.g. status, score, virtual currency, identity), awards and points.

Some Scraping may be to exercise an application, or part of an application, with the intent to gain insight how it is constructed and operates - perhaps for cryptanalysis, reverse engineering, or session analysis.

Where the intent is to obtain cash or goods, see **OAT-012 Cashing Out** instead. Where the application is being enumerated see **OAT-018 Footprinting** instead.

#### Other Names and Examples

Account aggregation; Aggregator; API provisioning; Asset stripping; Bargain hunting; Change monitoring; Comparative shopping; Data aggregation;  Data mining; Database scaping; Duplicate site; Extraction; Harvesting; Indexing; Media scraping; Memory scraping; Meta search scraper; Mirroring; Pagejacking; Price harvesting; Powering APIs; Product page scraper; Report mining; Ripping; Sanctioned scraping; Scraper bot; Screen scraping; Search engine bot; Social media bot

#### See Also

* **OAT-012 Cashing Out**
* **OAT-018 Footprinting**


### OAT-012 Cashing OutBuy goods or obtain cash utilising validated stolen payment card *or other user account* data.

#### Description

Obtaining currency or higher-value merchandise via the application using stolen previously validated payment cards or *other account log in credentials*. Cashing Out is sometimes may be undertaken in conjunction with product return fraud. * For financial transactions, this is usually a transfer of funds to a mule's account.* For payment cards, this activity may occur following **OAT-001 Carding** of bulk stolen data, or **OAT-010 Card Cracking**, and the goods are dropped at a reshipper's address. *The refunding of payments via non-financial applications (e.g. tax refunds, claims payment) is also included in Cashing Out.* 

Obtaining other information of value from the application is **OAT-011 Scraping** instead.

#### Other Names and Examples

Cashing out; *Man-in-the-Browser (MitB);???* Money laundering; Online credit card fraud; Online payment card fraud; *Refund fraud; Stolen identity refund fraud (SIRF)*

#### See Also

* **OAT-001 Carding**
* **OAT-011 Scraping**
* **OAT-010 Card Cracking**


### OAT-013 SnipingLast minute bid or offer, for goods or services.

#### Description

The defining characteristic of Sniping is an action undertaken at the latest opportunity to achieve a particular objective, leaving insufficient time for another user to bid/offer. Sniping can also be the automated exploitation of system latencies in the form of timing attacks. Careful timing and prompt action are necessary parts. It is most well known as auction sniping, but the same threat event can be used in other types of application. Sniping normally leads to some disbenefit for other users, and sometimes that might be a form of denial of service.

In contrast **OAT-005 Scalping** is the acquisition of limited availability of sought-after goods or services.

#### Other Names and Examples

Auction sniping; Bid sniper; *Front-running; Last look;* Last minute bet; Timing attack

#### See Also

* **OAT-005 Scalping**
* **OAT-006 Expediting**
* **OAT-015 Denial of Service**


### OAT-014 Vulnerability ScanningCrawl and fuzz application to identify weaknesses and possible vulnerabilities.

#### Description

Systematic enumeration and examination of identifiable, guessable and unknown content locations, paths, file names, parameters, in order to find weaknesses and points where a security vulnerability might exist. Vulnerability Scanning includes both malicious scanning and friendly scanning by an authorised vulnerability scanning engine. It differs from **OAT-011 Scraping** in that its aim is to identify potential vulnerabilities.

The exploitation of individual vulnerabilities is not included in the scope of this ontology, but this process of scanning. Vulnerability Scanning, along with **OAT-018 Footprinting**, **OAT-004 Fingerprinting** and **OAT-011 Scraping** often form part of application penetration testing.

Vulnerability Scanning has sometimes been mistakenly called penetration testing, or application security assessment, or vulnerability exploitation.

#### Other Names and Examples

Active/Passive vulnerability scanning; Application-specific vulnerability discovery by site-crawling botnet; Automated vulnerability scanning; Identifying vulnerable content management systems (CMS) and CMS components; Known vulnerability scanning; Malicious crawling; Scanning; Vulnerability reconnaissance, Vulnerability scanner; Vulnerability scanning

#### See Also

* **OAT-004 Fingerprinting**
* **OAT-011 Scraping**
* **OAT-018 Footprinting**


### OAT-015 Denial of ServiceTarget resources of the application and database servers, or individual user accounts, to achieve denial of service (DoS).

#### Description

These attacks often resemble legitimate application usage, but lead to exhaustion of resources such as file system, memory, processes, threads, CPU, human or financial resources. The resources might be related to web, application or databases servers or other services supporting the application such as third party APIs, included third-party hosted content, or content delivery networks (CDNs).

The application may be affected as a whole, or the attack may be against individual users such as account lockout. This user-specific application DoS may also be the result of application message, email or SMS spam floods.

This ontology's scope excludes other forms of denial of service that affect web applications, namely HTTP Flood DoS (GET, POST, Header with/without TLS), HTTP Slow DoS, IP layer 3 DoS, and TCP layer 4 DoS. Those protocol and lower layer aspects are covered adequately in other taxonomies and lists.

#### Other Names and Examples

Abuse of shopping carts; Account lockout; App layer DDoS; Asymmetric application-level DoS attacks; Asymmetric resource consumption (amplification); Bad configuration DoS; Business logic DDoS; Cash overflow; Cloud service provider credit DoS; Cost escalation; Disable/delete user accounts; Excessive allocation; Excessive anti-fraud measures; Forced deadlock; Hash DoS; Inefficient code; Indexer DoS; Large files DoS; Poorly designed web application DoS; Resource depletion; Resource locking; Regular expression exponential blowup; Resource exhaustion; Resource leak exposure; Self-inflicted DoS; SOAP array blowup; Spam receipt DoS; Sustained client engagement; The Great Firewall of China DoS; User DoS; XML attribute blowup; XML DoS; XML entity blowup; XML entity expansion; XML quadratic expansion

#### See Also

* **OAT-005 Scalping**
* **OAT-013 Sniping**
* **OAT-019 Account Creation**


### OAT-016 SkewingRepeated link clicks, page requests or form submissions intended to alter some metric.

#### Description
Automated repeated clicking or requesting or submitting content, affecting application-based metrics such as counts, and measures of frequency and/or rate. The metric or measurement may be visible to users (e.g. betting odds, likes, market pricing, visitor count, poll results, reviews) or hidden (e.g. application usage statistics, business performance indicators). Metrics may affect individuals as well as application-owner e.g. user reputation, influence others, gain fame, or undermine someone else’s reputation.
For malicious alteration of digital advertisement metrics, see **OAT-003 Ad Fraud** instead

#### Other Names and Examples
Biasing KPIs; Boosting friends, visitors, and likes; Click fraud; Complaint boosting; Election fraud; Hit count fraud; Market distortion; Metric and statistic skewing; Page impression fraud; Poll fraud; Poll skewing; Poll/voting subversion; Rating/review skewing; Search engine ranking skewing; Skewing consultations, elections, polls, rankings and votes; Stock manipulation; Survey skewing

#### See Also
* **OAT-003 Ad Fraud*** **OAT-017 Spamming*** **OAT-019 Account Creation**


### OAT-017 SpammingMalicious and/or more benign information addition, that appears in public or private content, databases or user messages.

#### Description

Malicious content can include malware, Iframe distribution, photographs & videos, advertisements, referrer spam and tracking/surveillance code. The content might be less overtly malicious but be an attempt to cause mischief, undertake search engine optimisation (SEO) or to dilute/hide other posts.
The mass abuse of broken form-to-email and form-to-SMS functions to send messages to unintended recipients is not included in this threat event, or any other in this ontology, since those are considered to be the exploitation of implementation flaws alone.
For multiple use that distorts metrics, see **OAT-016 Skewing** instead.

#### Other Names and Examples

Blog spam; Bulletin board spam; Comment spam; Complaint spam; Content spam; Content spoofing; Email field spam; Enquiry spam; Form spam; Forum spam; Guest book spam; Profile spam; Referrer spam; Response form spam; Review spam; SEO referral spam; Spam crawlers; Spammer bot; Spam 2.0; Web spambot; Wiki spam; Third-party component compromise; Twitter spam

#### See Also

* **OAT-015 Denial of Service*** **OAT-016 Skewing*** **OAT-019 Account Creation**


### OAT-018 FootprintingProbe and explore application to identify its constituents and properties.

#### Description

Information gathering with the objective of learning as much as possible about the composition, configuration and security mechanisms of the application. Unlike Scraping, Footprinting is an enumeration of the application itself, rather than the data. It is used to identify all the URL paths, parameters and values and process sequences (i.e. to determine entry points, also called the attack surface). As the application is explored, additional paths will be identified which in turn need to be examined.

Some aspects of **OAT-004 Fingerprinting** together with **OAT-011 Scraping** would be used to perform reverse engineering which is more focused on understanding all the detailed underlying logic. Footprinting can also include brute force, dictionary and guessing of file and directory names. Fuzzing may also be used to identify further application resources and capabilities.

Footprinting is much more comprehensive than **OAT-004 Fingerprinting** which only looks for key indicators. Footprinting attempts to enumerate the whole application scope. Foot printing does not include attempts to exploit weaknesses.

#### Other Names and Examples

Application analysis; API discovery; Application enumeration; Automated scanning; CGI scanning; Crawler; Crawling; Excavation; Forced browsing; Forceful browsing; Fuzzing; Micro service discovery; Scanning; Spidering; WSDL scanning

#### See Also

* **OAT-004 Fingerprinting**
* **OAT-011 Scraping**


### OAT-019 Account CreationCreate multiple accounts for subsequent misuse.

#### Description

Bulk account creation, and sometimes profile population, by using the application's account signup processes. The accounts are used subsequently for misuse such as generating content spam, laundering cash and goods, spreading malware, affecting reputation, causing mischief, and skewing search engine optimisation (SEO), reviews and surveys.

Account Creation generates new accounts, rather than attempting to use existing accounts - see **OAT-007 Credential Cracking** and **OAT-008 Credential Stuffing**.

#### Other Names and Examples

Account pharming; Fake account; Fake social media account creation; Impersonator bot; Massive account registration; New account creation; Registering many user accounts

#### See Also

* **OAT-007 Credential Cracking**
* **OAT-008 Credential Stuffing**
	