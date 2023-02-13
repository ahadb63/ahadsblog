---
toc: true
comments: false
layout: post
title: Big Idea 5.6 Safe Computing
description: This tech talk discusses safe computing
permalink: /safe
categories: [5.D, 5.E]
type: ap
week: 22
---

# Safe Computing

### Personal Identifiable Information (PII)
As we create a Web Site and post information we are adding to the Searchable PII.  However, there is a dichotomy as a site ***like LinkedIn is a place where we want to be known for our accomplishments***.  But be aware, the person that looks at your LinkedIn will, **most likely**, look at things like TikTok, Instagram or Facebook.  

### PII considerations
* Things that will be known by everyone:  Name, Email (suggest a junk email), Picture, High School attended, College Attended, Properties you own, State-City of residence, all State-City of previous residence, Credit Reports, ... 
* Gray area items, more cautious: Birth date, Place of Birth, Street Address, Phone Number, Maiden names of Mother and Grandmother, Drivers License Number, ...
* Things that you should strive to keep absolutely secret: Credentials for Access, Two-Factor Authentication on Financial accounts, Social Security Number, Tax records, ...

### Beware, Establish practices for your own Safety
* ***Multi-factor authentication*** often requires you to enter a code that has been texted or emailed to you.   Other types of authentication are biometrics (finger print or facial recognition).
* ***Malware*** is often sent in attachments to things in email.  Often they request you to click on an attachment and it starts the process of adding a virus to your computer.
* ***Phishing*** is where unknown sources try to entice you into a response, like click here and receive $500.  Often such systems impersonate someone like Amazon asking for login information.  Be careful to look closely at source of email (ie amzn.com vs amazon.com).

### Factors to Increase Security of System (**recommend** Watch 5.6 Video 2)
* Most of my financials or critical systems use **Multi Factor authentication**
* Biometrics is something that is used secure systems, fingerprints or facial recognition
* ***Symmetric*** encryption is a type of encryption where only ***one key (a secret key)*** is used to both encrypt and decrypt electronic information.
* ***Asymmetric cryptography***, also known as public-key cryptography, is a process that uses a pair of related keys -- ***one public key and one private key*** -- to encrypt and decrypt a message and protect it from unauthorized access or use.
* SSL Uses both Asymmetric and Symmetric Encryption

### Nefarious Uses of Internet
* A Virus or Malware compromise security, they are opposite of increasing security.  
* Phishing is a way to get a Virus on your machine, or a way to get you to input PII.
* After a Virus or being compromised by Phishing it is advised to review all of you PII vulnerabilities.

## Blog Post Reflection:
1. Describe PII you have seen on project in CompSci Principles.  

- When signing up for GitHub I used google. ThIs mean github has access to all the PII stored inside of my google account. Our own porject will be taking user PII in the form of thier full name. 

1. What are your feelings about PII and your personal exposure?

- I think that some people share wayyy to much online and it ends up hurting them in the long run with things like jobs. Ive always kept my online small (compared to others) because of the fear of getting into trouble, or not finding a job later, etc.

1. Describe good and bad passwords?  What is another step that is used to assist in authentication.

- Bad paswords are things that can be easily found out like your name, bday, fav number etc. A good number looks like a combinations of symbols, numbers and charachters that are randomized.

1. Try to describe Symmetric and Asymmetric encryption.  

- Symmetric encryption is an encryption method where the same secret key is used for both encryption and decryption of data. It means that both the sender and the receiver must have the same key to encrypt and decrypt the data. 

- Asymmetric encryption is an encryption method where different keys are used for encryption and decryption. The sender uses the receiver's public key to encrypt the data, and the receiver uses their private key to decrypt the data. The public key can be freely shared and is used for encryption, while the private key must be kept secret and is used for decryption.


1. Provide an example of encryption we used in AWS deployment.

- 

1. Describe a phishing scheme you have learned about ***the hard way***.  Describe some other phishing techniques.
- Sometimes when you click links such as a discord login, it is a fake discord website and they hack you. Fake sites or email address like google.com compared to goggle.com. They create fake logim pages and steal your info