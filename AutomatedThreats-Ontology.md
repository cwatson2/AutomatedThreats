# Automated Threat Handbook

DRAFT, 12th June 2015

## Covers

### Front

The Automated Threat Handbook

Web Applications

Version 1.0

?? ???? 2015

### Back

This document is an output of the OWASP Automated Threats to Web Applications Project. The project creates information and other resources for architects, developers, testers, and others to help defend against automated threats.

[https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications](https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications)

All OWASP materials are free to use. This document is licensed under the Creative Commons Attribution-ShareAlike 3.0 license, so you can copy, distribute and transmit the work, and you can adapt it, and use it commercially, but all provided that you attribute the work and if you alter, transform, or build upon this work, you may distribute the resulting work only under the same or similar license to this one.

© 2015 OWASP Foundation

(ISBN Code)

## Title page

The Automated Threat Handbook

Web Applications

The Automated Threat Handbook provides actionable information and resources to help web application owners defend against automated threats to web applications

Author: Colin Watson

Other Project Contributors and Reviewers: 

Version 1.0 published ?? ???? 2015

© 2015 OWASP Foundation

This document is licensed under the Creative Commons Attribution-ShareAlike 3.0 license


## Contents

* Preface
* Introduction
* Research
* The Ontology
* Use and Forward Plan
* Glossary
* Project Details and Outputs
* Appendices
  * A: Use Case Scenarios
  * B: Ontology Views and Mappings
* Ontology Reference

## Preface

Most web applications are not under a constant state of compromise, regardless of whether there are weaknesses and vulnerabilities present. However, attackers are still using the software in a manner that causes significant pain to the owners/operators, and sometimes also the users. 

Previous work on [OWASP AppSensor](https://www.owasp.org/index.php/OWASP_AppSensor_Project) (application-specific attack detection and response) has identified 50 or so types of [detection points](https://www.owasp.org/index.php/OWASP_AppSensor_Project#tab=Detection_Points), and I had speculated about which detection points would be most beneficial to implement first. All AppSensor detection points should have an extremely low false positive attack detection rate so that normal usage is never flagged as malicious, but I wondered which detection points might identify attackers sooner than others - before they targeted some potential vulnerability. What I needed was a list of threats (and probably automated threats) which are not just attempting to exploit individual implementation bugs or misconfigurations. In other words, what are attackers actually doing most of the time?

And here I came across a blocker - there did not seem to be a clear categorisation or quantification of these actual automated threats most web application owners have to deal with day-to-day. These are also mostly not included in "breach" statistics and discussions, even though there are breaches of security occurring. Instead there is a greater focus on individual types of weaknesses and vulnerabilities, root cause analysis of data confidentiality breaches, and much from vendors about product/service capabilities. Some business owners are submerged in technical details leading to a lack of comprehension about the relationships between security requirements, security activities during development, deployment and operation, and the operational impact of attacks. It also seems to be the case there is too great a focus on individual weaknesses/vulnerabilities in technical assurance activities, especially where the severity rating of each issue in isolation fails to provide the overall picture. For example, it is common for a number of individual, low or medium severity issues to contribute to a much more significant business impact.

I was also concerned about misuse of valid functionality, as this is an aspect where early design decisions have a significant effect on operational risk.

In order to quantify the threats, it is necessary to be able to name them, and that did not seem to exist in the usual dictionaries and classifications. Therefore I decided to produce an ontology of automated threats from the perspective of  defenders. I was aware of the magnitude of task of creating identifiers, and had read advice from contributors to Mitre and First documents. Consequently, to contain the scope somewhat, I decided to focus solely upon web applications.

The first output - an ontology - is provided in this document. And now I am moving on to produce other materials for web application defenders.

Colin Watson
12th June 2015

## Introduction

### Background

There is a significant body of knowledge about application vulnerability types, and some general consensus about identification and naming. But issues relating to the misuse of valid functionality, which may be related to design flaws rather than implementation bugs, are less well defined. Yet these problems are seen day-in, day-out, by web application owners. Some examples commonly referred to are:

* Account enumeration
* Aggregation
* Click fraud
* Comment spam
* Content scraping
* etc.
Excessive abuse of functionality is commonly mistakenly reported as application denial-of-service (DoS) attacks such as HTTP-flooding or application resource exhaustion, when in fact the DoS is a side-effect. Most of these problems seen regularly by web application owners are not listed in any OWASP Top Ten or other top issue list or dictionary.

This has contributed to inadequate visibility, and an inconsistency in naming such threats, with a consequent lack of clarity in attempts to address the issues.

### Requirements

The initial aim was to produce an ontology providing a common language for developers, architects, operators, business owners, security engineers, purchasers and suppliers/vendors, to facilitate clear communication and help tackling the issues. The project also intends to identify symptoms, mitigations and controls in this problem area. Like all OWASP outputs, everything is free and published using an open source licence. 

### Objectives

The initial objectives defined in early 2015 were:

* Provide a definition of "automated threat" 
* Create a common vocabulary, and relationships, of automated threats which maintains consistency with existing literature.

This would involve creating a listing of vendor-neutral and technology agnostic terms that describe real-world automated threats to web applications, at a level of abstraction suitable for application owners. The ontology and other supporting materials need to be practical and useful for a range of activities throughout a secure software development lifecycle (S-SDLC).

### Scope

The focus for the project is the abuse of functionality - misuse of inherent functionality and related design flaws, some of which are also referred to as business logic flaws. There is no coverage of implementation bugs. It is neither the case that implementation bugs are not the target of attacks, nor that their exploitation cannot be automated, but there is much more knowledge published in that area with a greater agreement on terminology. The intention was that all the threats must require the web to exist for the threat to be materialised; thus attacks that can be achieved without the web are out of scope. 

The threat events are scenarios which are seen commonly by real operating web applications, and are multi-step and/or highly iterative and/or multiple weaknesses involved, and not primarily about events that relate to the tool-based exploitation of single-issue vulnerabilities of individual web applications. Essentially the ontology needs to be a list of concise answers to the oprtaional question "what is happening right now?".

The summary definition created to describe this is:

* Threat events to web applications undertaken using automated actions.

The terms threat, threat event, web, applications and automated are defined in the glossary towards the end of this main text.

Some examples that are out of scope for this ontology are:

* Native mobile apps (but web application end point threats are in scope)
* Threats pre deployment (e.g. design, development, testing, deployment)
* Threats that affect web application businesses, but that are not undertaken using the web (e.g. in ecommerce: return fraud, wear & return fraud, not delivered fraud, price arbitrage, nearby address fraud, cross-merchant no-receipt returns, friendly fraud)
* Other layer 7 protocols including e.g. FTP, SMTP
* Host addressing and identification
* Attacks targeting network infrastructure 
* Network, HTTP and SSL/TLS denial of service
* Physical and environmental attacks against components supporting web applications.

Therefore, attacks like phishing, pharming, and trojan distribution are excluded.

## Research

### Literature review

Work began on the project in late January 2015. Over 150 sources of information were identified, read and relevant threat information extracted. The full list of academic papers, blog posts, briefings, conference presentations, dictionaries, news stories, reports, technical papers and white papers is too long to include in this handbook but is published on the OWASP wiki:

* [https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications#tab=Bibliography](https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications#tab=Bibliography)

This created over 600 data points describing a mixture of threats, attacks and some vulnerabilities. Updates were periodically posted to the project pages on the OWASP wiki.

### Analysis

In order to distil the data points to a more manageable scope, the information was first converted into a large-scale diagram. This attempted to remove duplication and highlight inter-relationships. The diagram can be found on the OWASP wiki:

* [https://www.owasp.org/index.php/File:Automated-threats.pdf](https://www.owasp.org/index.php/File:Automated-threats.pdf)

Anything relating to exploitation of implementation bugs was excluded. Forty or so clusters of threats were extracted from this diagram, and this was reduced further to a slightly smaller number of candid threat event names. Work then began to identify inter-relationships, similarities, overlaps and unique aspects. This process was undertaken over 1-2 months and reduced the number of recommended threat event names to just over twenty. Further de-duplication reduced the final count to nineteen. See below for a discussion of some of the candidate names that did not make the list.

### Peer review

The project was announced in the OWASP Foundation's Connector newsletter sent to 60,000+ recipients in April 2015. It was also highlighted in a two-side colour flyer included in every delegate's bag at AppSec EU 2015 in Amsterdam.

A limited amount of peer review has been undertaken over about a month with:

* Professional colleagues
* Web application owners
* Web application developers
* Delegates at AppSec EU 2015 via an online and printed survey form
* One-to-one interviews with participants of the OWASP Project Summit 2015 in Amsterdam
* Others who found the project by search, or from coverage relating to a presentation to be given at AppSec USA in San Francisco in September 2015.

The peer review led to clearer scope, suggestions for additional threats, and changes to both the names and descriptions of the threat events. Further peer review would be welcome.

### Comparison with other dictionaries, taxonomies and lists

Three OWASP projects were reviewed at an early stage:

* The OWASP Top 10 [Web Application] Risks is the most well known OWASP output, but is a high-level awareness document with the aim to educate developers, designers, architects, managers, and organisations about the consequences of the most important web application security weaknesses; it highlights common and higher impact risks caused by both design flaws and implementation bugs; abuse of functionality is not a current top 10 item; no names from the OWASP Top 10 are included in the ontology
* The OWASP Top Ten [Web Application] Proactive Controls is a list of security techniques that should be included in every software development project; it is focused on reducing the incidence of weaknesses and vulnerabilities, but does not particularly address automated threats
* The OWASP WASC Web Hacking Incidents Database Project (WHID) classifies publicly known incidents using attack methods, weaknesses and outcomes. As such it excludes incidents that are not reported, and thus is lacking in data relating to misuse of functionality. Some of the application denial of service incidents may include data that relates to other threat events described in the ontology.

The OWASP wiki includes many categorisations, and one of which is [attack](https://www.owasp.org/index.php/Category:Attack). The named items point to some automated threats, and were reviewed in the research stage. 

During the literature review and subsequent analysis and finalisation of the ontology, two of the reference sources were referred to again and again:

* Common Attack Pattern Enumeration and Classification (CAPEC) is a dictionary and classification taxonomy of known attacks on software. Its primary classification structures are Domains of attack (3000)  and Mechanism of Attack (1000). While CAPEC includes many closely related threat events, and many detailed description of attacks, the dictionary does not provide coverage of all the automated threats identified in this ontology; the best match is often the category CAPEC-210 Abuse of Functionality; see Appendix B for a mapping of CAPEC category and attack pattern IDs to the ontology
* The WASC Threat Classification classifies weaknesses and attacks that can lead to the compromise of a website, its data, or its users; this was a useful source of automated threat information, but apart from authentication threats, most of the relevant concerned fall within a single classification (WASC-42 Abuse of Functionality).

None of the above lists, nor Mitre's Common Weakness Enumeration (CWE) which is the most comprehensive dictionary of software weaknesses, provide the coverage and owner-viewpoint which this project aimed to create.

## The Ontology

### Introduction

The research and analysis and discussions with peers, completed over five months, whittled down the threat actions to a smaller core list of nineteen as described above.

The names used, combined with their defining characteristics, are taken from existing usage where possible. However, terminology is not used consistently within the literature sources reviewed, and also in some cases it was necessary to use a more generic term that captures the wider idea instead of an individual common name. Furthermore, the intended outcomes of the threat action are usually unknown at the time of the action taking place, and thus outcome-related names were generally rejected. For example, is the creation of a fake account intended for distributing malware in user-generated content, or to manipulate search engine scoring, or to influence other users, or to explore the authenticated parts of the application.

The ontology is a list of threat event scenarios (when a threat agent acts against an asset, partially ordered in time) by software, causing a divergence from accepted behavior producing one or more undesirable effects on a web application, and which excludes tool-based exploitation of single-issue vulnerabilities.

### The list

Full details of the finalised ontology threat events are provided in the cream coloured pages at the end of this handbook. A summary, ordered by identity ascending, is provided below:

Identity | Name | Defining characteristics
--------|-------|------
OAT-001 | Carding | Multiple payment authorisation attempts used to verify the validity of bulk stolen payment card data
OAT-002 | Token Code Cracking | Mass enumeration of coupon numbers, voucher codes, discount tokens, etc
OAT-003 | Ad Fraud | False clicks and fraudulent display of web-placed advertisements
OAT-004 | Fingerprinting | Elicit information from the web, application and database servers about the supporting software and framework types and versions
OAT-005 | Scalping | Obtain limited-availability and/or preferred goods/services by unfair methods
OAT-006 | Expediting | Perform actions to hasten progress of usually slow, tedious or time-consuming actions on behalf of a person.
OAT-007 | Credential Cracking | Identify valid log in credentials by trying different values for usernames and/or passwords
OAT-008 | Credential Stuffing | Mass log in attempts used to verify the validity of stolen username/password pairs
OAT-009 | CAPTCHA Bypass | Solve anti-automation tests
OAT-010 | Card Cracking | Identify missing expiry dates and security codes for stolen payment card data by trying different values
OAT-011 | Scraping | Collect application content and/or other data for use elsewhere
OAT-012 | Cashing Out | Buy goods or obtain cash utilising validated stolen payment card or other user account data
OAT-013 | Sniping | Last minute bid or offer, for goods or services
OAT-014 | Vulnerability Scanning | Crawl and fuzz application to identify weaknesses and possible vulnerabilities
OAT-015 | Denial of Service | Target resources of the application and database servers, or individual user accounts, to achieve denial of service (DoS)
OAT-016 | Skewing | Repeated link clicks, page requests or form submissions intended to alter some metric
OAT-017 | Spamming | Malicious and/or more benign information addition, that appears in public or private content, databases or user messages
OAT-018 | Footprinting | Probe and explore application to identify its constituents and properties
OAT-019 | Account Creation | Create multiple accounts for subsequent misuse


The detailed at the end of this handbook categorise the threat events by:

* Sectors Targeted - Sectors that are targeted more commonly than others for the specific threat event, are highlighted in amber; this is currently just the author's opinion, but the project is seeking information to define this aspect more accurately
* Parties Affected - Whether individuals, groups of people, the application owner and other parties are most often affected adversely by the threat event; the threat event may affect other parties depending upon the application and its data; the parties affected, exclude subsequent further misuse
* Data Commonly Misused - The types of data are web application specific; however some threat events are more likely to occur for certain data types.

Each threat event is also cross-referenced with:

* Mitre CAPEC - Best full and/or partial match CAPEC category IDs and/or attack pattern IDs
* WASC Threat Classification - Best match to threat IDs
* Mitre Common Weakness Enumeration - Closely related base, class and variant weakness IDs
* Matching pages classified as attacks on the OWASP wiki.


### Notes 

#### Threat event names

In all cases, "automated web application" could be used as a prefix to each name. Thus, for example, **OAT-012 Cashing Out** is concerned only with using web applications to obtain cash or goods and the ontology's scope excludes cashing out using ATMs. And **OAT-015 Denial of Service** is web application denial of service, and not network, SSL/TLS or network DoS. When referencing the terms in other contexts it may be useful to ensure the web application scope is identified.

Whenever possible an existing term already used in literature or industry usage was preferred. But in many cases it was difficult to identify this, and in some cases a more generic version had to be used. A good example of this is **OAT-013 Sniping** where auction sniping is the most commonly cited case; it was determined that the characteristics of sniping also occur in threat events against other types of application, and the selected name was thus made more general. 

A handful of threat event names in the ontology are very specific since they are reported to occur frequently (e.g. **OAT-001 Carding**, **OAT-019 Account Creation**). Others are larger buckets (e.g. **OAT-011 Scraping**, **OAT-017 Spamming**, **OAT-014 Vulnerability Scanning**) which cannot be broken down easily without sharding the threat events into a multitude of sector-specific and function-specific examples.

The only name newly created is **OAT-006 Expediting** as there appeared to be a large number of sector-specific threats involving increased multi-step velocity that could otherwise not be aggregated together under a single name.

#### Threat event identity values

To enable internal cross-referencing and reference from elsewhere, each threat event has been given an identification (ID) number. This is a three digit number prefixed by a hyphen and an abbreviation for OWASP Automated Threat (OAT) e.g. OAT-015. The IDs were randomly assigned in an attempt to stop the ontology being seen as an ordered list, and also to ensure that neighbouring items are not necessarily related. Other cross-referencing is provided. Currently IDs 001 to 019 are used, and it is expected the total number should be many fewer than fifty, unless many sub-items are ever added. Three digits, rather than two, were allotted in case the first digit is used for some other aspect in future e.g. perhaps mobile application automated threat events could be 1xx, and 2xx for embedded software, etc. 

#### Timing, duration and frequency

The scope focuses on threat events that involve multi-step and/or highly iterative interactions with the application. But by their nature, the identified threat events vary significantly in scale, and their timing, duration and frequency can all vary considerably. This is an area that could be explored further in future work.

#### Magnitude of impact

Events related to automated threats can have impacts on more than just the application owner. Individuals, third parties and even society can be adversely affected. This ontology does not attempt to provide information on, or rank the threat events in terms of, impact since it will be organisation, data, threat actor and victim-perspective specific. An organisation may choose to use its own risk assessment processes to rank these threats for each operational entity, or each market, or even by individual application.

#### The perpetrators

During the early stages of the ontology's creation, it was believed it would be possible to suggest which threat actors might be most likely to initiate the threat event. These threat agents might be groups like competitors, journalists, petty criminals, organised crime, nation states, etc and of course users such as citizens, clients, customers and employees. However, on further inspection the threat agents appear to be more closely related to the type of data, and thus sector, rather than the particular threat event. Consequently, it is believed threat agent should be re-considered in future sector-specific views of the ontology.

Furthermore, some threat events may be undertaken by, or with the knowledge or implicit support of, application owners. For example, search engine indexing is generally encouraged due to the benefit of increased user traffic (**OAT-011 Scraping**); automated monitoring of web applications may be commissioned (**OAT-011 Scraping**); excessive account creation might contribute to enhanced market reputation when promoting the size of its customer base (**OAT-019 Account Creation**); the application owner with hosted advertisements could receive additional income for false impressions (**OAT-003 Ad Fraud**).

#### Fraud, legality and cheating

In general the ontology tries to avoid the use of judgmental words like fraud. But in one case, the industry accepted term for the threat event includes this word: **OAT-003 Ad Fraud**.

In legal terms, whether an action is fraudulent depends on legislation and this jurisdiction. Some of the events in this ontology may be illegal actions in some jurisdictions. This will also depend upon the types of data handled, regulation of the application and its owner and application specific mandates like terms of use.

Rather than being illegal, some threat events will be considered cheating by other normal users, including **OAT-006 Expediting**, **OAT-005 Scalping**, **OAT-016 Skewing** and **OAT-013 Sniping**. These will be sector, applicationa dn culturally specific views, but can undermine user trust and the reputation of the application and its owner.

### Terms excluded

A small number of threat events were removed during analysis and review based on discussions with peers and website owners. The primary reason for removal was either being out of scope, or because the term could not be adequately distinguished from another. Other people may have alternative views on these, so the discarded temporary working names and justifications are provided below alphabetically.

*Account Aggregation* was initially defined as user account aggregation where credentials from multiple individual user accounts are centralised into another application, with each user's permission. The aggregating application may be used by one user to merge information from multiple applications, or alternatively merge information of many users of a single application. This is commonly used for aggregating social media accounts, email accounts and financial accounts in order to obtain a consolidated overview, provide integrated reporting/analysis, and simplify usage and consumption by the user and/or their professional advisors. The aggregating application may include making changes to account properties and interacting with the aggregated application's functionality. Some terms used elsewhere include password manager, financial account aggregator, client aggregator, or simply data aggregator. On consideration, it was felt that the provision of user credentials to the aggregator was not in itself an automated threat, and the resultant effects were indistinguishable from other information harvesting. The effects on the ability for the web application owner to interact with the end user may be enhanced or reduced depending upon the circumstances, and thus may or may not be desirable. Therefore, it was decided to incorporate Account Aggregation together with other types of data collection, along with data aggregation where information is republished on the web elsewhere, in a single threat action **OAT-011 Scraping**.

*Application Consumption* was a temporary working name given the misuse of the application to perform calculations, or process data, or perform other actions against other applications, hosts, or in the physical world i.e. unauthorised real-time consumption of a normal application as if it were an API. Unlike data harvesting, where information is gathered once or periodically, in consumption the thought was the application is used on-demand by another system to provide calculated output, send requests to another application, or possibly affect physical assets the application provides direct control over. For example the application might be used to generate images or other files based on user input. In the second case, the application checks user submitted data (e.g. hostname, email address) by undertaking a reverse lookup, ping back or a reputation service check, contributing to a denial of service attack against that other host. In all of these, there seemed to be a close similarity with Account Aggregation above and thus was eventually concluded to be another example of **OAT-011 Scraping**.

*Application Worms*, also called cross-site scripting worms, are a combination of two different implementation flaws – cross-site request forgery (CSRF) and cross-site scripting (XSS). Additionally, the automation is undertaken by the web application itself in conjunction with often normal usage by innocent users. Therefore it was decided this did not fall within the defined scope.

*Asset Stripping* was considered to encompass the removal of application stored non-data assets using compromised accounts and sessions, including data theft, collecting micro deposits, and collecting refunds. However this asset removal, extraction or copying from applications used as repositories is no different from other data harvesting at the time of extraction. The only difference is the assets have value in other non-application contexts and may include fiat money, credit, refunds, financial instruments, reputation, virtual assets (e.g. status, score, virtual currency, identity), awards and points, and possible physical assets the application provides control over. But this value is often very subjective. Since these are data, it was considered this threat event was actually part of **OAT-011 Scraping**. The objectives of the attacker and consequences are data and application specific. Additionally the transfer of money was included within **OAT-012 Cashing Out**. Consequently, Asset Stripping was not included as a separate term.

*Attack Platform* was at first used to describe the misuse of an application to mount automated attacks against another application or other external information system component. This would include reflected DoS, anti-spam check DoS, amplification DoS, and numerous HTML5 attacks. For example the application checks user submitted data (e.g. hostname, email address) by undertaking a reverse lookup, ping back or a reputation service check, contributing to a denial of service attack against that host. Or an HTML application is compromised to undertake attacks against local and other remote systems. The affected host is not the application itself; instead the application performs the attack on some other system. Ultimately, like the somewhat related Code Modification below, this was dropped from the ontology

*Code Modification* relates to when the application logic is changed by modification of the source code, or the executing code, or the configuration, or combinations of these. The kinds of attacks included are malicious software download, malicious software update, advert injection, DOM modification, web browser tools, form tampering, malicious software implanted, backdoor addition, shared data manipulation, use of untrusted code, memory modification, Angular JS attack, configuration data modification, exposed reflection, reflection injection, autobinding, and Rich Internet Application (RIA) attacks. The issue is made more significant with the growing use of client side code. But it was felt these threats were related to lack of integrity checks, particularly during development and distribution, rather than being typical automated threats, and therefore Code Modification not included in this ontology.

*Form Hijacking* (e.g. email spam, form to Email spam, SMS spam, use as a spam relay, and unsolicited bulk email) was initially thought to be a core threat event and would be an ideal candidate for the threat action ontology. But again it was realised this is an implementation flaw that leverages vulnerabilities produced when an web server fails to validate input, and thus does not fit into this ontology.

*Man in the Browser* (MitB) where the attacker controls the user's web browser, so that information being transferred can be observed, intercepted and manipulated, was another threat event that was thought at the start of the project would be in the final ontology. The most well-known use case is to undertake financial fraud, and are the result of compromise of the user's device by a banking trojan, such as URLzone, Torpig, and Zeus. However, MitB can also be used for advert injection, and some simpler variants have been labelled Boy in the Browser (BitB). MitB/BitB are believed to be out-of-scope since the trojan distribution, and the interception/change of information, are both occurring outside the web application's boundaries.

*Reverse Engineering*, exercising an application or part of an application with the intent to gain insight how it is constructed and operates. The purpose may be to understand the inner workings, and may be used to determine business logic such as pricing models, reproduce the application elsewhere, or to assist with vulnerability exploitation and data compromise. was decided to be an intended outcome of a combination of other threat actions - typically **OAT-011 Scraping** and **OAT-018 Footprinting** which include the testing and collection of evidence to determine the underlying logic, structures, algorithms, functions, methods and secrets of the application. Thus, as an outcome it was decided that Reverse Engineering is not valid part of the ontology.

## Use and Forward Plan

### Use cases

Example use case scenarios have been created to illustrate usage in S-SDLC activities:

* Defining application security requirements* Sharing intelligence within a sector* Exchanging threat data between CERTs* Enhancing application penetration test findings* Specifying service acquisition needs* Characterising vendor services.

These are defined fully in Appendix A.

### Ongoing improvement

It is hoped the production of the ontology and handbook, will lead to further discussion and debate, and encourage additional project participants (see Project details and outputs below). A key area where help is required is to gather data on the prevalence of these threats, where some form of data collection initiative is required. 

People can contribute by joining and posting ideas, suggestions, and other inputs to the project's public mailing list (see Project Details and Outputs).

### Project road map

It is also intended to develop sector-specific guides that include:

* Highest risk threat events
* Attacker motivations

Retail, and financial service sectors appear to be good candidates to begin with.

Currently each threat event is defined on a single page (see the listing at the end of this handbook). It is intended to augment the current information with the following details on the reverse sides of the threat event pages:

* Symptoms
* Mitigations
* For builders
* For defenders
* Threat identification metrics.

It would also be useful to summarise the developer-relevant information into a new Automated Threat Cheat Sheet, and contribute that to the OWASP Cheat Sheet Series.

The author also hopes this ontology with its industry cross-referencing may be of help in contributing to Mitre's Common Weakness Risk Analysis Framework (CWRAF) and Common Attack Pattern Enumeration and Classification (CAPEC). Also in the future the terms might be useful for helping to describe some application events in the Mitre/DHS Structured Threat Information eXpression (STIX).

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

## Project Details and Outputs

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

The following scenarios and organisation names are completely fictitious.

### Defining application development security requirements

Cinnaminta SpA intends to build and launch a new multi-lingual and multi-currency ecommerce website. The development will be outsourced and Cinnaminta has been working on the functional design document. Amongst many other requirements, the application security specification requires that the website must not include any vulnerabilities identified in PCI DSS v3.1 Requirement 6.5, nor any other vulnerabilities that could affect the protection of payment cardholder data. Cinnaminta specifies that the website's payment functions must not be susceptible to the threat events **OAT-001 Carding** or **OAT-010 Card Cracking** defined in the **OWASP Automated Threat Handbook**. In addition the application must interact with the company's existing fraud detection system to counter **OAT-012 Cashing Out**. The requirements are specified in terms of these threat events, rather particular product and service categories. Development houses responding to the call for bids use the ontology to focus their answers to these aspects appropriately.
### Sharing intelligence within a sector

Unlimited Innovations Inc develops and supports patient-facing software solutions to a range of healthcare providers, many of which participate in the National Health Service Cyber Intelligence Sharing Center (NHS-CISC). Unlimited Innovations already builds continuous monitoring capabilities into its software and decides to provide an optional enhancement so that customers could choose to share their misuse event data with each other, to benefit from the combined threat intelligence. Rather than sharing large quantities of low-level data, Unlimited Innovations aggregates information and broadcasts validated and categorised threat data amongst the participating organisations. Automation attacks are classified according to the threat events defined in the **OWASP Automated Threat Handbook** so that each receiving party understands the nature of the threat. Even organisations that do not want to take part in this information sharing can benefit, since their own categorised information is made available to internal business management in the form of an easy-to-comprehend monitoring dashboard. The information gathered can also be fed into their other business information management systems to help improve patient service.
### Exchanging threat data between CERTs

National Computer Emergency Response Teams (CERTs) recognise that sharing of local information can contribute to worldwide prevention of cyber attacks. Despite advances in cooperation between CERTs, anything to increase continuity and interoperability such as standards for data exchange is encouraged. CERT Zog is concerned about the sparsity of application-specific data it receives, and also the classification of that data. It has a particular concern about attacks and breaches that affect sectors defined in Zog's 2015 national cyber security strategy. CERT Zog and its neighbour CERT Tarset agree to tag threat events using the **OWASP Automated Threat Handbook** to add greater context to existing solutions being used for threat data exchange between them. The programme also collects sector meta data, so that all organisations within these can benefit from the centralised intelligence.
### Enhancing application penetration test findings

Specialist application security penetration testing firm Cherak Industries Pte Ltd works primarily for financial services companies in the banking and insurance sectors, and is looking to expand its business throughout Asia. Cherak has some innovative pen test result reporting systems which integrate with client software fault and vulnerability tracking systems, and it actively looks for methods to provide additional value to its clients. Cherak has identified that pen test clients would benefit from help to understand the effects of combinations of vulnerabilities, especially design flaws, and has decided to utilise the **OWASP Automated Threat Handbook** to define and explain the automation-related threats. The individual vulnerabilities were scored as normal using CVSSv2 and v3, the matching CWEs identified, and mitigations in place documented. In addition Cherak uses the threat events defined in the **OWASP Automated Threat Handbook** to help create a new section in the executive summary that explains how combinations of the issues found could lead to automation threats and the possible technical and business impacts. For example, an assessment for one client had identified weaknesses in authentication so that there is a risk of **OAT-008 Credential Stuffing**. The defined identifier was provided to the client so its technical staff could refer to additional information on the OWASP website.
### Specifying service acquisition needs

Falstone Paradise Inc is concerned about malicious use of their portfolio of hotel and resort websites. The majority of the websites use a shared application platform, but there are some unique applications and a large number of other micro-sites, some of which use generic content management systems such as Wordpress and Drupal. Falstone Paradise has identified that its IT operations team are spending too much time dealing with the effects of automated misuse, such as cleaning up data, resetting customer accounts and providing extra capacity during attacks. Furthermore, the unwanted automation is also causing some instabilities leading to negative feedback from customers. Therefore Falstone Paradise decides to go out to the security marketplace to identify, assesses and select products or services that might help address these automation issues for all its websites. Their buying team work with their information technology colleagues to write the detailed requirements in an Invitation to Tender (ITT) document. This describes the types of attacks its web applications are receiving, the frequency of occurrence and magnitudes. These are defined according to the **OWASP Automated Threat Handbook** so that vendors do not misunderstand the requirements, each vendor's offering can be assessed against the particular automation threat events of concern.
### Characterising vendor services

Better Best Ltd has developed an innovative technology to help gaming companies defend against a range of automated threats that can otherwise permit cheating and distortion of the game, leading to disruption for normal players. The solution can be deployed on premises, but is also available in the cloud as a service. But Better Best is finding difficulty explaining its solution in the market place, especially since it does not fit into any conventional product category. Better Best decide to use the terminology and threat events listed in the **OWASP Automated Threat Handbook** to define their product's capabilities. They hope this will provide some clarity about their offering, and also demonstrate how their product can be used to replace more than one other conventional security device. Additionally, Better Best writes a white paper describing how their product has been successfully used by one of their reference customers Hollybush Challenge Games to protect against **OAT-006 Expediting**, **OAT-005 Scalping**, **OAT-016 Skewing** and **OAT-013 Sniping**.

## Appendix B - Ontology Views and Mappings

### Full list of threat events, ordered by OAT number

Identity | Name | Defining characteristics
--------|-------|------
OAT-001 | Carding | Multiple payment authorisation attempts used to verify the validity of bulk stolen payment card data
OAT-002 | Token Code Cracking | Mass enumeration of coupon numbers, voucher codes, discount tokens, etc
OAT-003 | Ad Fraud | False clicks and fraudulent display of web-placed advertisements
OAT-004 | Fingerprinting | Elicit information from the web, application and database servers about the supporting software and framework types and versions
OAT-005 | Scalping | Obtain limited-availability and/or preferred goods/services by unfair methods
OAT-006 | Expediting | Perform actions to hasten progress of usually slow, tedious or time-consuming actions on behalf of a person.
OAT-007 | Credential Cracking | Identify valid log in credentials by trying different values for usernames and/or passwords
OAT-008 | Credential Stuffing | Mass log in attempts used to verify the validity of stolen username/password pairs
OAT-009 | CAPTCHA Bypass | Solve anti-automation tests
OAT-010 | Card Cracking | Identify missing expiry dates and security codes for stolen payment card data by trying different values
OAT-011 | Scraping | Collect application content and/or other data for use elsewhere
OAT-012 | Cashing Out | Buy goods or obtain cash utilising validated stolen payment card or other user account data
OAT-013 | Sniping | Last minute bid or offer, for goods or services
OAT-014 | Vulnerability Scanning | Crawl and fuzz application to identify weaknesses and possible vulnerabilities
OAT-015 | Denial of Service | Target resources of the application and database servers, or individual user accounts, to achieve denial of service (DoS)
OAT-016 | Skewing | Repeated link clicks, page requests or form submissions intended to alter some metric
OAT-017 | Spamming | Malicious and/or more benign information addition, that appears in public or private content, databases or user messages
OAT-018 | Footprinting | Probe and explore application to identify its constituents and properties
OAT-019 | Account Creation | Create multiple accounts for subsequent misuse

### Full list of threat events, ordered by name

Identity | Name | Defining characteristics
--------|-------|------
OAT-019 | Account Creation | Create multiple accounts for subsequent misuse
OAT-003 | Ad Fraud | False clicks and fraudulent display of web-placed advertisements
OAT-009 | CAPTCHA Bypass | Solve anti-automation tests
OAT-001 | Carding | Multiple payment authorisation attempts used to verify the validity of bulk stolen payment card data
OAT-010 | Card Cracking | Identify missing expiry dates and security codes for stolen payment card data by trying different values
OAT-012 | Cashing Out | Buy goods or obtain cash utilising validated stolen payment card or other user account data
OAT-007 | Credential Cracking | Identify valid log in credentials by trying different values for usernames and/or passwords
OAT-008 | Credential Stuffing | Mass log in attempts used to verify the validity of stolen username/password pairs
OAT-015 | Denial of Service | Target resources of the application and database servers, or individual user accounts, to achieve denial of service (DoS)
OAT-006 | Expediting | Perform actions to hasten progress of usually slow, tedious or time-consuming actions on behalf of a person.
OAT-004 | Fingerprinting | Elicit information from the web, application and database servers about the supporting software and framework types and versions
OAT-018 | Footprinting | Probe and explore application to identify its constituents and properties
OAT-005 | Scalping | Obtain limited-availability and/or preferred goods/services by unfair methods
OAT-011 | Scraping | Collect application content and/or other data for use elsewhere
OAT-016 | Skewing | Repeated link clicks, page requests or form submissions intended to alter some metric
OAT-013 | Sniping | Last minute bid or offer, for goods or services
OAT-017 | Spamming | Malicious and/or more benign information addition, that appears in public or private content, databases or user messages
OAT-002 | Token Code Cracking | Mass enumeration of coupon numbers, voucher codes, discount tokens, etc
OAT-014 | Vulnerability Scanning | Crawl and fuzz application to identify weaknesses and possible vulnerabilities

### Authentication-related threat events, ordered by name

Identity | Name | Defining characteristics
--------|-------|------
OAT-019 | Account Creation | Create multiple accounts for subsequent misuse
OAT-009 | CAPTCHA Bypass | Solve anti-automation tests
OAT-007 | Credential Cracking | Identify valid log in credentials by trying different values for usernames and/or passwords
OAT-008 | Credential Stuffing | Mass log in attempts used to verify the validity of stolen username/password pairs
OAT-015 | Denial of Service | Target resources of the application and database servers, or individual user accounts, to achieve denial of service (DoS)
OAT-002 | Token Code Cracking | Mass enumeration of coupon numbers, voucher codes, discount tokens, etc

### Payment cardholder data-related threat events, ordered by name

Identity | Name | Defining characteristics
--------|-------|------
OAT-001 | Carding | Multiple payment authorisation attempts used to verify the validity of bulk stolen payment card data
OAT-010 | Card Cracking | Identify missing expiry dates and security codes for stolen payment card data by trying different values
OAT-012 | Cashing Out | Buy goods or obtain cash utilising validated stolen payment card or other user account data

### Application information gathering prior to exploitation threat events, ordered by name

Identity | Name | Defining characteristics
--------|-------|------
OAT-004 | Fingerprinting | Elicit information from the web, application and database servers about the supporting software and framework types and versions
OAT-018 | Footprinting | Probe and explore application to identify its constituents and properties
OAT-014 | Vulnerability Scanning | Crawl and fuzz application to identify weaknesses and possible vulnerabilities

### CAPEC mapping to threat events

TODO

Only three automated threats were found to map to multiple more detailed CAPEC attack pattern IDs. The best example of good coverage by both this ontology with CAPEC is **OAT-007 Credential Cracking**, where the latter has three attack patterns defined that completely cover the automated threat event. Based on this comparison it was found that CAPEC categories are often too broad, or the attack patterns are missing or much more detailed than this ontology.

### WASC Threat Dictionary mapping to threat events

TODO


## Ontology Reference

This section contains the full details of each threat event in the ontology.


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
	