---
layout: post
title: Conducting a Security Audit - Example
---
Following is an example of an internal security audit that I created for a fictional company as part of the Google Cybersecurity Certificate program. 

[*See my full breakdown of the course here.*](https://1dgk.github.io/2024/01/24/gcc-course-index.html)

### Scenario

*This scenario is based on a fictional company:*

Botium Toys is a small U.S. business that develops and sells toys. The business has a single physical location, which serves as their main office, a storefront, and warehouse for their products. However, Botium Toy’s online presence has grown, attracting customers in the U.S. and abroad. As a result, their information technology (IT) department is under increasing pressure to support their online market worldwide. 

The manager of the IT department has decided that an internal IT audit needs to be conducted. She expresses concerns about not having a solidified plan of action to ensure business continuity and compliance, as the business grows. She believes an internal audit can help better secure the company’s infrastructure and help them identify and mitigate potential risks, threats, or vulnerabilities to critical assets. The manager is also interested in ensuring that they comply with regulations related to internally processing and accepting online payments and conducting business in the European Union (E.U.).   

The IT manager starts by implementing the National Institute of Standards and Technology Cybersecurity Framework (NIST CSF), establishing an audit scope and goals, listing assets currently managed by the IT department, and completing a risk assessment. The goal of the audit is to provide an overview of the risks and/or fines that the company might experience due to the current state of their security posture.

Your task is to review the IT manager’s scope, goals, and risk assessment report. Then, perform an internal audit by completing a controls and compliance checklist.

### My recommendations
The entire security program at Botium Toys requires immediate attention. Following are risks and suggested fixes:

- Least privilege and separation of duties. Currently all employees at Botium can access cardholder data and PII/SPII. This is a security risk and can be prevented by ensuring that only employees who are required to handle such information have access to it. 
- Encryption. Botium can implement industry-standard encryption to protect credit card information. While credit card data is processed and stored internally, the environment is not secure without proper encryption methods. 
- Botium should implement a data backup and recovery strategy in the event of a natural disaster or cyberattack. 
- More robust password requirements will help reduce the risk of account compromise for their customers. 

Finally, since Botium Toys aims to expand their business into the E.U., the company must address the data encryption issue to be compliant with the General Data Protection Regulation (GDPR).

### Resources
[Google Cybersecurity Certificate](https://grow.google/certificates/cybersecurity/)