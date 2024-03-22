- The main reason we do Pentetration testing is to manage or midigate risks to identify and evauluate secruity risks.
- **This is a graph of different laws and regulations for cybersecurity**
  | **Categories** | **USA** | **Europe** | **UK** | **India** | **China** |
  | ---- | ---- | ---- |
  | Protecting critical information infrastructure and personal data | [Cybersecurity Information Sharing Act](https://www.cisa.gov/resources-tools/resources/cybersecurity-information-sharing-act-2015-procedures-and-guidance) (`CISA`) | [General Data Protection Regulation](https://gdpr-info.eu/) (`GDPR`) | [Data Protection Act 2018](https://www.legislation.gov.uk/ukpga/2018/12/contents/enacted) | [Information Technology Act 2000](https://www.indiacode.nic.in/bitstream/123456789/13116/1/it_act_2000_updated.pdf) | [Cyber Security Law](https://digichina.stanford.edu/work/translation-cybersecurity-law-of-the-peoples-republic-of-china-effective-june-1-2017/) |
  | Criminalizing malicious computer usage and unauthorized access to computer systems | [Computer Fraud and Abuse Act](https://www.justice.gov/jm/jm-9-48000-computer-fraud) (`CFAA`) | [Network and Information Systems Directive](https://www.enisa.europa.eu/topics/cybersecurity-policy/nis-directive-new) (`NISD`) | [Computer Misuse Act 1990](https://www.legislation.gov.uk/ukpga/1990/18/contents) | [Information Technology Act 2000](https://www.indiacode.nic.in/bitstream/123456789/13116/1/it_act_2000_updated.pdf) | [National Security Law](https://www.chinalawtranslate.com/en/2015nsl/) |
  | Prohibiting circumventing technological measures to protect copyrighted works | [Digital Millennium Copyright Act](https://www.congress.gov/bill/105th-congress/house-bill/2281) (`DMCA`) | [Cybercrime Convention of the Council of Europe](https://www.europarl.europa.eu/cmsdata/179163/20090225ATT50418EN.pdf) |  |  | [Anti-Terrorism Law](https://www.omm.com/resources/alerts-and-publications/alerts/what-companies-need-to-know-about-the-chinese-anti-terrorism-law/?sc_lang=zh-CN) |
  | Regulating the interception of electronic communications | [Electronic Communications Privacy Act](https://www.congress.gov/bill/99th-congress/house-bill/4952) (`ECPA`) | [E-Privacy Directive 2002/58/EC](https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX%3A32002L0058) | [Human Rights Act 1998](https://www.legislation.gov.uk/ukpga/1998/42/contents) (`HRA`) | [Indian Evidence Act of 1872](https://legislative.gov.in/sites/default/files/A1872-01.pdf) |  |
  | Governing the use and disclosure of protected health information | [Health Insurance Portability and Accountability Act](https://aspe.hhs.gov/reports/health-insurance-portability-accountability-act-1996) (`HIPAA`) |  | [Police and Justice Act 2006](https://www.legislation.gov.uk/ukpga/2006/48/contents) | [Indian Penal Code of 1860](https://legislative.gov.in/sites/default/files/A1860-45.pdf) |  |
  | Regulating the collection of personal information from children | [Children's Online Privacy Protection Act](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa) (`COPPA`) |  | [Investigatory Powers Act 2016](https://www.legislation.gov.uk/ukpga/2016/25/contents/enacted) (`IPA`) |  |  |
  | A framework for cooperation between countries in investigating and prosecuting cybercrime |  |  | [Regulation of Investigatory Powers Act 2000](https://www.legislation.gov.uk/ukpga/2000/23/contents) (`RIPA`) |  |  |
  | Outlining individuals' legal rights and protections regarding their personal data |  |  |  | [Personal Data Protection Bill 2019](https://www.congress.gov/bill/116th-congress/senate-bill/2889) | [Measures for the Security Assessment of Cross-border Transfer of Personal Information and Important Data](https://www.mayerbrown.com/en/perspectives-events/publications/2022/07/china-s-security-assessments-for-cross-border-data-transfers-effective-september-2022) |
  | Outlining individuals' fundamental rights and freedoms |  |  |  |  | [State Council Regulation on the Protection of Critical Information Infrastructure Security](http://english.www.gov.cn/policies/latestreleases/202108/17/content_WS611b8062c6d0df57f98de907.html) |
- Make sure to take these steps before a pentest to avoid violating laws
  | **Precautionary Measure** |
  | ---- | ---- | ---- |
  | `☐` | Obtain written consent from the owner or authorized representative of the computer or network being tested |
  | `☐` | Conduct the testing within the scope of the consent obtained only and respect any limitations specified |
  | `☐` | Take measures to prevent causing damage to the systems or networks being tested |
  | `☐` | Do not access, use or disclose personal data or any other information obtained during the testing without permission |
  | `☐` | Do not intercept electronic communications without the consent of one of the parties to the communication |
  | `☐` | Do not conduct testing on systems or networks that are covered by the Health Insurance Portability and Accountability Act (HIPAA) without proper authorization |
- A quick summary of the procedures for a pentest start to finish
- | **Stage** | **Description** |
  | ---- | ---- | ---- |
  | `1. Pre-Engagement` | The first step is to create all the necessary documents in the pre-engagement phase, discuss the assessment objectives, and clarify any questions. |
  | `2. Information Gathering` | Once the pre-engagement activities are complete, we investigate the company's existing website we have been assigned to assess. We identify the technologies in use and learn how the web application functions. |
  | `3. Vulnerability Assessment` | With this information, we can look for known vulnerabilities and investigate questionable features that may allow for unintended actions. |
  | `4. Exploitation` | Once we have found potential vulnerabilities, we prepare our exploit code, tools, and environment and test the webserver for these potential vulnerabilities. |
  | `5. Post-Exploitation` | Once we have successfully exploited the target, we jump into information gathering and examine the webserver from the inside. If we find sensitive information during this stage, we try to escalate our privileges (depending on the system and configurations). |
  | `6. Lateral Movement` | If other servers and hosts in the internal network are in scope, we then try to move through the network and access other hosts and servers using the information we have gathered. |
  | `7. Proof-of-Concept` | We create a proof-of-concept that proves that these vulnerabilities exist and potentially even automate the individual steps that trigger these vulnerabilities. |
  | `8. Post-Engagement` | Finally, the documentation is completed and presented to our client as a formal report deliverable. Afterward, we may hold a report walkthrough meeting to clarify anything about our testing or results and provide any needed support to personnel tasked with remediating our findings. |
- **Pre-engagment**
	- Note before you can talk to the client in depth about these topics please have an NDA signed here are the different kinds 
	  | **Type** | **Description** |
	  | ---- | ---- | ---- |
	  | `Unilateral NDA` | This type of NDA obligates only one party to maintain confidentiality and allows the other party to share the information received with third parties. |
	  | `Bilateral NDA` | In this type, both parties are obligated to keep the resulting and acquired information confidential. This is the most common type of NDA that protects the work of penetration testers. |
	  | `Multilateral NDA` | Multilateral NDA is a commitment to confidentiality by more than two parties. If we conduct a penetration test for a cooperative network, all parties responsible and involved must sign this document. |
	- Scoping questionnaire
	- Pre-engagement meeting
	- Kick-off meeting
	- When Documents should be signed
		- | **Document** | **Timing for Creation** |
		  | ---- | ---- | ---- |
		  | `1. Non-Disclosure Agreement` (`NDA`) | `After` Initial Contact |
		  | `2. Scoping Questionnaire` | `Before` the Pre-Engagement Meeting |
		  | `3. Scoping Document` | `During` the Pre-Engagement Meeting |
		  | `4. Penetration Testing Proposal` (`Contract/Scope of Work` (`SoW`)) | `During` the Pre-engagement Meeting |
		  | `5. Rules of Engagement` (`RoE`) | `Before` the Kick-Off Meeting |
		  | `6. Contractors Agreement` (Physical Assessments) | `Before` the Kick-Off Meeting |
		  | `7. Reports` | `During` and `after` the conducted Penetration Test |
	- Example of Scoping Questionnaire
		- | ☐ Internal Vulnerability Assessment | ☐ External Vulnerability Assessment |
		  | ☐ Internal Penetration Test | ☐ External Penetration Test |
		  | ☐ Wireless Security Assessment | ☐ Application Security Assessment |
		  | ☐ Physical Security Assessment | ☐ Social Engineering Assessment |
		  | ☐ Red Team Assessment | ☐ Web Application Security Assessment |
		- | How many expected live hosts? |  |
		  | How many IPs/CIDR ranges in scope? |  |
		  | How many Domains/Subdomains are in scope? |  |
		  | How many wireless SSIDs in scope? |  |
		  | How many web/mobile applications? If testing is authenticated, how many roles (standard user, admin, etc.)? |  |
		  | For a phishing assessment, how many users will be targeted? Will the client provide a list, or we will be required to gather this list via OSINT? |  |
		  | If the client is requesting a Physical Assessment, how many locations? If multiple sites are in-scope, are they geographically dispersed? |  |
		  | What is the objective of the Red Team Assessment? Are any activities (such as phishing or physical security attacks) out of scope? |  |
		  | Is a separate Active Directory Security Assessment desired? |  |
		  | Will network testing be conducted from an anonymous user on the network or a standard domain user? |  |
		  | Do we need to bypass Network Access Control (NAC)? |
		- Then ask how the client wants information discloser and evasiveness
		  collapsed:: true
			- What is a black box pentest
				- A black box pentest is a type of penetration test where the tester has no prior knowledge or access to the internal systems, networks, or source code of the target organization. The tester simulates the perspective of an external attacker to identify potential vulnerabilities and assess the overall security of the target system. The objective is to uncover any vulnerabilities that could be exploited by an attacker without any privileged information. The tester relies solely on publicly available information and common attack techniques to evaluate the security posture of the target system. The results of the black box pentest help organizations identify weaknesses in their defenses and enhance their overall cybersecurity posture.
			- What is a grey box pentest
				- A grey box pentest, short for grey box penetration testing, is a type of security assessment that combines elements of both white box and black box testing. In grey box testing, the ethical hacker has partial knowledge about the target system or network being tested. This usually means having some level of information, such as system architecture, access credentials, or internal documentation.
				  
				  With this limited knowledge, the grey box tester emulates a realistic attack scenario, attempting to identify vulnerabilities and exploit them. The goal is to simulate the perspective of an attacker who has obtained some insider knowledge about the target but is still outside the organization. This type of testing helps uncover potential security flaws that could arise from both external and internal attackers.
				  
				  The advantage of a grey box pentest is that it provides a more realistic assessment of a system's security posture compared to black box testing, which starts with no prior knowledge, and white box testing, which has full knowledge of the system. It allows the tester to focus on specific areas of concern and prioritize their efforts while leveraging the benefits of insider knowledge. This approach helps organizations identify critical vulnerabilities and make informed decisions regarding security enhancements.
			- What is a white box pentest
				- A white box pentest, also known as a white box penetration test, is a type of cybersecurity assessment where the pentester has full access to the internal workings of a system or network. The term "white box" refers to having complete knowledge of the system's architecture, design, code, and other technical details. During a white box pentest, the pentester is typically provided with source code, network diagrams, documentation, credentials, and any other relevant information that can aid in the identification and exploitation of vulnerabilities. This comprehensive understanding of the system allows the pentester to conduct a thorough assessment, simulating real-world attack scenarios with the goal of identifying weaknesses and recommending appropriate security measures. White box pentests are often utilized to assess the security posture of critical systems, applications, or networks before they are deployed or to validate the effectiveness of existing security controls.
	-
	- #### Contract - Checklist
	  | **Checkpoint** | **Description** |
	  | ---- | ---- | ---- |
	  | `☐ NDA` | Non-Disclosure Agreement (NDA) refers to a secrecy contract between the client and the contractor regarding all written or verbal information concerning an order/project. The contractor agrees to treat all confidential information brought to its attention as strictly confidential, even after the order/project is completed. Furthermore, any exceptions to confidentiality, the transferability of rights and obligations, and contractual penalties shall be stipulated in the agreement. The NDA should be signed before the kick-off meeting or at the latest during the meeting before any information is discussed in detail. |
	  | `☐ Goals` | Goals are milestones that must be achieved during the order/project. In this process, goal setting is started with the significant goals and continued with fine-grained and small ones. |
	  | `☐ Scope` | The individual components to be tested are discussed and defined. These may include domains, IP ranges, individual hosts, specific accounts, security systems, etc. Our customers may expect us to find out one or the other point by ourselves. However, the legal basis for testing the individual components has the highest priority here. |
	  | `☐ Penetration Testing Type` | When choosing the type of penetration test, we present the individual options and explain the advantages and disadvantages. Since we already know the goals and scope of our customers, we can and should also make a recommendation on what we advise and justify our recommendation accordingly. Which type is used in the end is the client's decision. |
	  | `☐ Methodologies` | Examples: OSSTMM, OWASP, automated and manual unauthenticated analysis of the internal and external network components, vulnerability assessments of network components and web applications, vulnerability threat vectorization, verification and exploitation, and exploit development to facilitate evasion techniques. |
	  | `☐ Penetration Testing Locations` | External: Remote (via secure VPN) and/or Internal: Internal or Remote (via secure VPN) |
	  | `☐ Time Estimation` | For the time estimation, we need the start and the end date for the penetration test. This gives us a precise time window to perform the test and helps us plan our procedure. It is also vital to explicitly ask how time windows the individual attacks (Exploitation / Post-Exploitation / Lateral Movement) are to be carried out. These can be carried out during or outside regular working hours. When testing outside regular working hours, the focus is more on the security solutions and systems that should withstand our attacks. |
	  | `☐ Third Parties` | For the third parties, it must be determined via which third-party providers our customer obtains services. These can be cloud providers, ISPs, and other hosting providers. Our client must obtain written consent from these providers describing that they agree and are aware that certain parts of their service will be subject to a simulated hacking attack. It is also highly advisable to require the contractor to forward the third-party permission sent to us so that we have actual confirmation that this permission has indeed been obtained. |
	  | `☐ Evasive Testing` | Evasive testing is the test of evading and passing security traffic and security systems in the customer's infrastructure. We look for techniques that allow us to find out information about the internal components and attack them. It depends on whether our contractor wants us to use such techniques or not. |
	  | `☐ Risks` | We must also inform our client about the risks involved in the tests and the possible consequences. Based on the risks and their potential severity, we can then set the limitations together and take certain precautions. |
	  | `☐ Scope Limitations & Restrictions` | It is also essential to determine which servers, workstations, or other network components are essential for the client's proper functioning and its customers. We will have to avoid these and must not influence them any further, as this could lead to critical technical errors that could also affect our client's customers in production. |
	  | `☐ Information Handling` | HIPAA, PCI, HITRUST, FISMA/NIST, etc. |
	  | `☐ Contact Information` | For the contact information, we need to create a list of each person's name, title, job title, e-mail address, phone number, office phone number, and an escalation priority order. |
	  | `☐ Lines of Communication` | It should also be documented which communication channels are used to exchange information between the customer and us. This may involve e-mail correspondence, telephone calls, or personal meetings. |
	  | `☐ Reporting` | Apart from the report's structure, any customer-specific requirements the report should contain are also discussed. In addition, we clarify how the reporting is to take place and whether a presentation of the results is desired. |
	  | `☐ Payment Terms` | Finally, prices and the terms of payment are explained. |
	- #### Rules of Engagement - Checklist
	  | **Checkpoint** | **Contents** |
	  | ---- | ---- | ---- |
	  | `☐ Introduction` | Description of this document. |
	  | `☐ Contractor` | Company name, contractor full name, job title. |
	  | `☐ Penetration Testers` | Company name, pentesters full name. |
	  | `☐ Contact Information` | Mailing addresses, e-mail addresses, and phone numbers of all client parties and penetration testers. |
	  | `☐ Purpose` | Description of the purpose for the conducted penetration test. |
	  | `☐ Goals` | Description of the goals that should be achieved with the penetration test. |
	  | `☐ Scope` | All IPs, domain names, URLs, or CIDR ranges. |
	  | `☐ Lines of Communication` | Online conferences or phone calls or face-to-face meetings, or via e-mail. |
	  | `☐ Time Estimation` | Start and end dates. |
	  | `☐ Time of the Day to Test` | Times of the day to test. |
	  | `☐ Penetration Testing Type` | External/Internal Penetration Test/Vulnerability Assessments/Social Engineering. |
	  | `☐ Penetration Testing Locations` | Description of how the connection to the client network is established. |
	  | `☐ Methodologies` | OSSTMM, PTES, OWASP, and others. |
	  | `☐ Objectives / Flags` | Users, specific files, specific information, and others. |
	  | `☐ Evidence Handling` | Encryption, secure protocols |
	  | `☐ System Backups` | Configuration files, databases, and others. |
	  | `☐ Information Handling` | Strong data encryption |
	  | `☐ Incident Handling and Reporting` | Cases for contact, pentest interruptions, type of reports |
	  | `☐ Status Meetings` | Frequency of meetings, dates, times, included parties |
	  | `☐ Reporting` | Type, target readers, focus |
	  | `☐ Retesting` | Start and end dates |
	  | `☐ Disclaimers and Limitation of Liability` | System damage, data loss |
	  | `☐ Permission to Test` | Signed contract, contractors agreement |
	- #### Contractors Agreement - Checklist for Physical Assessments
	  | **Checkpoint** |
	  | ---- | ---- | ---- |
	  | `☐ Introduction` |
	  | `☐ Contractor` |
	  | `☐ Purpose` |
	  | `☐ Goal` |
	  | `☐ Penetration Testers` |
	  | `☐ Contact Information` |
	  | `☐ Physical Addresses` |
	  | `☐ Building Name` |
	  | `☐ Floors` |
	  | `☐ Physical Room Identifications` |
	  | `☐ Physical Components` |
	  | `☐ Timeline` |
	  | `☐ Notarization` |
	  | `☐ Permission to Test` |
	-