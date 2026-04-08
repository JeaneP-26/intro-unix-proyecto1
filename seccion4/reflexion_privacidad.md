
#----------------------------------------------------------**Section 4**------------------------------------------------

1. What is asymmetric encryption (public, private key) and how does it work in the context of GPG? 
What is the difference between encrypting a message and digitally signing it?

Asymmetric encryption uses a public key and a private key, and it can be understood as a secure way to send information using two “keys”. 
Each user has a public key, which can be shared freely, and a private key, which must be kept secret and not shared with anyone. (NinjaOne, 2024)
In GPG, a combination of asymmetric and symmetric encryption is used to send messages securely. For example, if someone wants to send you something confidential, 
they encrypt the message with your public key, and then yoy decrypt it with your private key. This way, even if the message passes through many places or is intercepted, 
it cannot be understood. (Coinmetro, n.d.)
Now, regarding the difference between encrypting a message and digitally signing it, it may seem similar at first. Encrypting is about “hiding” the content so that no one else can read it. 
On the other hand, digital signing does not hide the message; instead, it proves that it really comes from the person who claims to have sent it and that it has not been modified along the way
A digital signature works by creating a summary (hash) of the message using the sender’s private key. Then, the receiver uses the public key to verify that summary, if everything matches, it can be trusted that the message is authentic. 
However, signing a message does not mean it is protected: if it is not encrypted, anyone could still read it even If it is signed. (Encyption Consulting, 2020).

2.  Compare ProtonMail, Gmail and Outlook in terms of: 
a)	Encryption at rest, b) encryption in transit, c) end-to-end encryption,
d) privacy policies and provider access to data, e) legal jurisdiction. 

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   Email       ||         Encryption at rest        ||         Encryption in transit           ||       End-to-end encryption              ||     Privacy policies and           ||   Legal jurisdiction                                                                                                                                                    |
               ||                                   ||                                         ||                                          ||     provider access to data          ||                                                                                                                                                                         |
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
 ProtonMail    || Uses zero-access encryption, which|| Messages are secured during transmission   Messages are always encrypted end-to-end,  Data is always stored encrypted   The jurisdiction is Switzerland,  
                  keeps all emails stored on its       although the encryption used depends on ||  while they are being transmitted.       ||and only authorized personnel can access the servers ||so it is governed by its privacy laws. (Proton, n.d.)
               || servers private. (Proton, n.d.)   || the recipient’s email provider. (Proton,|| (Proton, n.d.)                           ||In addition, not even Proton can read the content of emails,
                                                    || n.d.)                                                                               ||which ensures greater security for the user. (Proton, 2025)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
 Gmail         || Emails are encrypted at rest, but ||Google protects emails by encrypting them||E2EE in Workspace uses client-side        ||It can process user data to support || USA Subject to FISA, Cloud Act.  
               ||Google can still scan them for spam||both during transmission and while they  ||encryption, where the user controls the   ||advertising activities and adhere to legal || 
               ||and security,so they aren´t fully  ||are stored on its servers. (Private      ||keys and Google cannot read the messages. ||obligations when necessary.
               ||private. (Private Internet Access  ||Internet Access, 2025)                   ||(Private Internet Access, 2025)           ||
               ||, 2025)                            ||                                         ||                                          ||
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
 Outlook       ||The encrypt option secures the     ||The encrypt option secures the messages  ||Uses MPME to secure emails and attachments||Data is under our control,and Microsoft || It is owned by Microsoft and is included                                                   
               ||messages and attachments at rest,  ||and attachments in transit, and the      ||during their transmission, ensuring end-to||only uses it with our consent to   || as part of the Microsoft 365 application suite
               ||and the encryption cannot be       ||encryption cannot be removed. (University||-end encryption. (Beyond Encryption, 2025)||provide its services. (Microsoft, n.d.)|| (Universidad Politecnica de Cartagena, n.d.)
               ||removed. (University of Pittsburgh ||Pittsburgh , n.d.)                       ||                                          ||                                    ||
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

3. What is the PKI model based on certificate authorities (CA), and mention 2 advantages and 2 disadvantages compared to the Web of Trust?

The PKI (Public key Infrastructure) model is a way to secure communication between two parties using public key cryptography. It works with a pair of keys, a public key and a private key, 
that allow information to be encrypted and transmitted securely. (Splunk, 2023)
Public keys are verified by a certificate Authority (CA), which acts as a trusted third party that issues and signs digital certificates. These certificates confirm that 
a public key belongs to the person or entity it claims, preventing impersonation. (Splunk, 2023)
Additionally, the CA has other important roles, such as revoking certificates if they are no longer secure, managing their expiration, and validating digital signatures. 
Overall, its purpose is to maintain trust in the system and ensure secure communication. (Splunk, 2023)
On the other hand, the Web of Trust has the advantage of being more secure, since trust does not rely on a single entity but on multiple people who validate a key. 
This makes it harder for someone to impersonate identities or manipulate information. Additionally, it is more economical and practical model because it does not require a centralized infrastructure. 
In this approach, users themselves take part in the verification process, making it more flexible and accessible. (PhoenixNAP, 2025)
On the other hand, the Web of Trust also has some disadvantages. One of them is that it can be hard to find a clear or reliable trust path between users. 
Since trust is built through indirect relationships, there may be multiple possible paths, and it’s not always obvious which one is the most trustworthy. 
Another disadvantage is that it can feel overwhelming for users. They are responsible for managing trust relationships and verifying their keys,
which can be confusing or tedious, especially for those without much experience, leading to lower adoption of the model. (PhoenixNAP, 2025)

4. Research the General Data Protection Regulation (GDPR) of the EU and the Organic Law on Personal Data Protection of Ecuador. 
What rights do they grant to citizens regarding email and digital surveillance? (create a comparative table)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Aspect                   ||                        European Union (GDPR)                                        ||                   Ecuador (LOPDP)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Start date of the law    || This regulation has been in effect since 2018.                                      || This law started being applied in 2021.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Who it applies to        || It includes any organization that handles personal data of people living in the EU, || It applies to any person or organization that processes personal 
                         ||even if the company operates from another country.                                   ||data of Ecuadorian citizens.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Access to personal data  ||Individuals can request information about what data organizations have about         || This right is clearly established and must be answered within 15 days.
                         ||them and access it whenever they need.                                               ||
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Deletion of personal data|| People can ask for their personal data to be deleted when it is no longer           ||Citizens also have the right to request the deletion of their data, 
                         ||necessary for the purpose it was collected.                                          ||as long as it follows the conditions set by the law.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

5. What is email metadata? Why does encrypting the content not protect metadata, and what are the implications for privacy?
Email metadata is the information that comes with an email but isn’t part of the actual message. It’s basically “data about data”. 
While it helps emails work properly, it can also raise privacy and security concerns. (PauBox, 2024)
This metadata includes headers and routing information, which can show the sender’s domain, the IP addresses of the servers the email passed through, 
timestamps, and authentication results such as SPF, DKIM, and DMARC. (Vecta AI, n.d.)
Analyzing this data can help detect attacks like phishing, since it can reveal impersonation attempts. It can also expose communication patterns within an organization, 
such as who communicates with whom attackers could exploit. (Vecta AI, n.d.)
Encrypting protects the content of a message, but not its metadata, because that information is needed to deliver it. 
For privacy, this means that even without seeing the message, someone can still analyze patterns and learn a lot about a person



**Reflection**:
While working on these topics, I realized that digital security is much closer to our everyday lives than I thought. 
It’s not just about hiding information, but also about knowing who to trust and how our data is handled.
Comparing email services and learning about concepts like metadata and security models made me see that things are not as private as they may seem.
Overall, I take away the idea that protecting our information online is essential and largely depends on the decisions we make every day.
