# Select Your Email Provider to view Document

* Urgency
* HTML to impersonate a legitimate brand
* Link manipulation
* Credential harvesting
* Poor grammar and/or typos

Let's take a closer look...\


\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email6-details2.png" alt=""><figcaption></figcaption></figure>

Here are some quick observations about this email sample:

1. The email was sent on Thursday, July 15th, 2021. &#x20;
2. A sense of urgency is introduced in this email. Notice that the link to download the fax document expires on the same day.
3. There is an action to perform. In this case, a button to download the fax.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email6-phish1b.png" alt=""><figcaption></figcaption></figure>

The above image shows the victim is redirected to a page created to pass as OneDrive. Notice that the URL is not anything Microsoft-related.&#x20;

There are two more links for the victim to interact with. The victim has to click either button to obtain the fax document that is set to expire.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email6-phish2b.png" alt=""><figcaption></figcaption></figure>

The victim is directed to yet another site. This one was crafted to resemble Adobe. Again, notice the URL. It doesn't look like it's related to Adobe.

Also, notice the page title in the tab. It's called "Share Point Online", which is a Microsoft product.  There are a couple of grammatical errors as well.&#x20;

The victim has options to sign in with the email provider of their choice.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email6-phish3.png" alt=""><figcaption></figcaption></figure>

Our victim chose to log in with Outlook because, per the instructions, "_To read the document, please enter with the valid email credentials that this file was sent to._"; the email was viewed in Outlook.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email6-phish4.png" alt=""><figcaption></figcaption></figure>

In this sample, we can tell that fake credentials were entered, but even if the victim would have entered valid credentials, the error message would be the same. This scenario happens because the victim is not really authenticating to an email provider. Instead, the credentials that were entered now reside on the criminal's server. The criminal's objective to harvest credentials has been met.&#x20;

Lastly, notice more grammatical errors. All this work they put into this, you would think they would run a spell check.&#x20;

This email sample was obtained from Any Run. If you wish to interact with the email and see the full analysis, refer to the link below.

* Analysis: [https://app.any.run/tasks/12dcbc54-be0f-4250-b6c1-94d548816e5c/#](https://app.any.run/tasks/12dcbc54-be0f-4250-b6c1-94d548816e5c/)
