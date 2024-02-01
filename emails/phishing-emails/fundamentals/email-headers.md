# Email Headers



## Parts of the Email:

{% embed url="https://mediatemple.zendesk.com/hc/en-us/articles/204643950-understanding-an-email-header" %}

## Received

The received is the most important part of the email header and is usually the most reliable. A "Received:" line typically identifies the machine that received the mail and the machine from which the mail was received. <mark style="color:yellow;">The received lines are best read from bottom to top.</mark><mark style="color:blue;">**`First "Received:`**</mark>" line is your <mark style="color:blue;">**`own system or mail server. Last "Received:`**</mark>" line is <mark style="color:blue;">**`where the mail originated.`**</mark>

### Finding the Original Sender

The easiest way for finding the original sender is by looking for the **X-Originating-IP** header.
