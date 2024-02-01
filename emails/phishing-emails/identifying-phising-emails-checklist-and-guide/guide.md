# Guide

<pre class="language-bash"><code class="lang-bash">#From
Who the message is from (FORGED)
#Subject
Topic of the email content
#Date
Date and Time the email message was composed
#To
<strong>To whom the message was addressed, but may not contain the recipient's address.
</strong>#Return-Path
Same as "Reply-To:"
#Envelope-To
Shows that this email was delivered to the mailbox of a subscriber whose email address is user@example.com.
#Delivery Date
Date and Time at which the email was received by your (mt) service or email client.

################ Received ################
First "Received:" line is your own system or mail server. 
Last "Received:" line is where the mail originated.
#Dkim-Signature &#x26; Domainkey-Signature
keys which are currently not supported by (mt) 
#Message-id
unique string created when the email was created (FORGED)
#Mime-Version
Format
#Content-Type
Type of the content
#X-Spam-Status
Spam Score
#X-Spam-Level
Spam Score
#Message Body
Content of the email
################ X-Originating-IP ############
Original Sender

Once you know the sender go check for online tools to make some research
</code></pre>

{% embed url="http://www.arin.net/" %}
