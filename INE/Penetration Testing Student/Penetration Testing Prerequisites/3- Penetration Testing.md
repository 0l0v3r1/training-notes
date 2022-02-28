# Penetration Testing Introduction

## 4.1 Introduction

- Penetration Testing is not about getting **root**
- Penetration Testers cannot destroy their client's infrastructure

* * *

* * *

# Lifecycle of a Penetration Tester

## 4.2 Lifecycle of a penetration Test

- Phases of the penetration testing process:
    - Engagement
    - Information gathering
    - Footprinting and Scanning
    - Vulnerability assessment
    - Exploitation
    - Reporting

<img src="../../../_resources/Screenshot from 2021-11-15 12-05-13.png" alt="Screenshot from 2021-11-15 12-05-13.png" width="899" height="257" class="jop-noMdConv">

## 4.2.1 Engagement

- All the details about the penetration test are established during the **Engagement** phase

## 4.2.1.1 Quotation

- Phase of defining the fee for the penetration test of a network, a web application or the whole organization, the fee will vary according to:
    - Type of engagement (Black box, Gray box, etc)
    - How time-consuming the engagement is
    - The Complexity of the application and services in scope
    - the number of targets (IPs, domains, etc)

## 4.2.1.2 Proposal Submittal

- The proposal should include:
    - The understanding of the client's needs
    - The approach and methodology you want to use, like the use of automated scanning tools, manual testing, onsite testing and any other information that fits
    - How you want to address their needs and what kind of value the pentest will bring to their business in terms of **risks and benefits**: (business continuity, improved confidentiality, avoidance of money, reputation loss due to data breaches)
    - A quotation in terms of price and an estimate of time required to perform your job
    - The type of engagement: penetration test or vulnerability assessment? remote or onsite...
    - The scope of engagement in terms of IP addresses, network bloks, domain names or any name useful in defining the scope

## 4.2.1.3 Staying in Scope

- If it is a part of shared hosting, you must not conduct an assessment on such a target unless you are given written permission from the hosting provider
- Always analyze the target scope and verify if it's your client's property and if you have written permission

## 4.2.1.4 Incident Handling

- During a penetration test, incidents may happen. Incident is an unplanned and unwanted situation that affects the client's enviroment and disrupt its sevices
- Always aim to not damage the target
- In case of planning some intensive or risky tests, contact your customer
- An **Incident Handling Procedure** is a set of instructions that need to be executed by both you and your customer on how to proceed when an incident (e.g., service damage or unavailability) occurs
- If there is no fixed procedure established by the client, the simplest way to handle an incident is to have an emergency contact, a technical person on the client's side that is available that might coordinate further incident handling for the customer's company
- Once the emergency contact is set, it is worth adding a statement to the **rules of engagement**:

<img src="../../../_resources/Screenshot from 2021-11-15 15-26-25.png" alt="Screenshot from 2021-11-15 15-26-25.png" width="899" height="216" class="jop-noMdConv">

## 4.2.1.5 Legal Work

- Sometimes you will need to involve a lawyer as information security laws vary a lot from country to country, and it is strongly adviced have professional insurance just in case
- Companies usally want you to sign one or more **Non-Disclosure Agreements** (NDAs) These documents enforce your full confidentiality regarding any information or confidential data you may come accross during your engagement

## 4.2.2 Information Gathering

## 4.2.2.3 Infrastructure Information Gathering

- After Collecting The General Information, and have an understanding of the Business, The Infrastructure Information Guathering Begins
- In this phase, you transofrm IP addresses or domains into actionable information about servers, operating systemsand much more

## 4.2.2.4 Web Applications

- If there is any web application in scope, in this pahse we harvest:
    - Domains
    - Subdomains
    - Pages (website crawling)
    - Technologies in use (PHP, JAVA, .NET ...)
    - Frameworks and content management systems in use (Drupal, Joomla, Wordpress ...)

## 4.2.3 Footprinting and Scanning

Nothing New or Interresting actually!

## 4.2.4 Vulnerability Assessment

- The Vulerability Assessment phase is aimed at building a list of the vulnerabilities present on the target systems
- The Exploitation phase will go through this list to exploit the system
- Can be conduted manually or automated using special tools (isn't that obvious?)

## 4.2.5 Exploitation

- This phase is takes care of exploiting all the vulnerabilities found during the previous step
- A Penetration Test is a **Cyclic Process**

<img src="../../../_resources/Screenshot from 2021-11-16 23-25-00.png" alt="Screenshot from 2021-11-16 23-25-00.png" width="700" height="625" class="jop-noMdConv">

- The process ends when there are no more systems and services in-scope to exploit

## 4.2.6 Reporting

- The report must address:
    - Techniques used
    - Vulnerabilities found
    - Exploits used
    - Impact and risk analysis for each vulnerability
    - Remediation tips
- **Remediation tips** are the real value for the client

## 4.2.6.2 Consultancy

- Penetration testers are often asked to provide some hours of consultancy after delivering the report; this is an additional service to the client
- After the Consultancy, the pentester must keep the report encrypted and safe, or better shred and destroy it