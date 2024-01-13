# DHL Express Courier Shipping notice

This email sample will highlight the following techniques:\


* Spoofed email address
* HTML to impersonate a legitimate brand
* Attachments

Here are some quick observations about this email sample:

1. The sender's email doesn't match the company that is being impersonated, which in this case is DHL.
2. The subject line gives the impression that there is a package DHL will ship for you.
3. The HTML in the email body was designed to look like it was sent from DHL.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email4-details.png" alt=""><figcaption></figcaption></figure>

Looking at the source code for the email, the link to view the email as a web page doesn't contain an actual destination URL.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email4-body-1.png" alt=""><figcaption></figcaption></figure>

...

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email4-body-2.png" alt=""><figcaption></figcaption></figure>

The only element the victim can interact with in this email is the email attachment, which, in this case is an Excel document.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email4-attachment.png" alt=""><figcaption></figcaption></figure>

The image below shows what is contained within the attachment.\


\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email4-attachment2.png" alt=""><figcaption></figcaption></figure>

The attachment runs a payload that throws an error.&#x20;

![](https://assets.tryhackme.com/additional/phishing2.0/email4-attachment3.png)
