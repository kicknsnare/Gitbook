# Track Your Package

1. Spoofed email address
2. Pixel tracking
3. Link manipulation

Here are some quick observations about this email sample:

1. The email is tailored to appear that it's sent from a mail distribution center of some sort.&#x20;
2. The subject line adds to the pretense with a 'tracking number.'&#x20;
3. The link in the email body matches the subject line.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email2-details.png" alt=""><figcaption></figcaption></figure>

Note: In this email sample, Yahoo blocked the images from automatically loading. Any guesses as to why?&#x20;

Typically one can hover the cursor over a link to see where the link is pointing to, but in this sample, that technique won't work because Yahoo disabled links in the email.  We can look at the raw source code for the email and find out.&#x20;

Email Hyperlinks:

\


<figure><img src="https://assets.tryhackme.com/additional/phishing2.0/email2-hyperlinks.png" alt=""><figcaption></figcaption></figure>

Here we see an image file, and it's explicitly called Tracking.png. These trackers send information back to the spammer's server.&#x20;

There are many reasons for spammers to embed tracking pixels (very small images) into their spam emails. To read more about this concept, refer to this post on The Verge [here](https://www.theverge.com/22288190/email-pixel-trackers-how-to-stop-images-automatic-download).&#x20;

Now we can understand why Yahoo automatically blocked the images in this email. Many email providers do the same. \


Back to the hyperlink, the link is pointing to a shady-looking domain. The only distribution center this domain can be associated with is malware, but further analysis is the only way to confirm that definitely.&#x20;
