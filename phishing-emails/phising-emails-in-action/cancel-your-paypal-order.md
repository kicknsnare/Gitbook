# Cancel Your Paypal Order

* Spoofed email address
* URL shortening services
* HTML to impersonate a legitimate brand

Here are some quick observations about this email sample:

1. This is an unusual email recipient address. This is not the email address associated with the Yahoo account.&#x20;
2. This mismatch should immediately stand out. The sender's details (service@paypal.com) don't match the sender's email address (gibberish@sultanbogor.com).&#x20;
3. The subject line hints that you made a purchase or a transaction of some sort. If you don't recall this account, then it will grab your attention. This social engineering tactic is to prompt you to interact with the email with haste.&#x20;

![](https://assets.tryhackme.com/additional/phishing2.0/email1-details.png)

Email Body Text (Image 1):

![](https://assets.tryhackme.com/additional/phishing2.0/email-body-1.png)\


The second half of the same email body text (Image 2):

![](https://assets.tryhackme.com/additional/phishing2.0/email-body-2b.png)\


The email body compliments the sender information and subject line. The email was designed as a legitimate email from PayPal.&#x20;

There aren't any attachments associated with this email. The only interactive element in this email is the Cancel the order button/link.&#x20;

Let's investigate that further by reviewing the raw HTML source for the email...

Email Hyperlinks:

![](https://assets.tryhackme.com/additional/phishing2.0/cancel-order.png)\


The link uses URL shortening services. It is not a good idea to click on the link if you don't know where the link is taking you.&#x20;

Luckily, there are online tools that we can use to let us know the destination of a shortened URL.&#x20;

![](https://assets.tryhackme.com/additional/phishing2.0/email1-url-shortener.png)
