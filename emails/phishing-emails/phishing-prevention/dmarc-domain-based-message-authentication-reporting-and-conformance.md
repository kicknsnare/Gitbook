# DMARC (Domain-Based Message Authentication, Reporting, and Conformance)

_Uses a concept called alignment to tie the result of two other open source standards, SPF (a published list of servers that are authorized to send email on behalf of a domain) and DKIM (a tamper-evident domain seal associated with a piece of email), to the content of an email. If not already deployed, putting a DMARC record into place for your domain will give you feedback that will allow you to troubleshoot your SPF and DKIM configurations if needed._"



**`Identifier alignment is at the heart of DMARC. Alignment refers to the relationship between the domain in the From Header address and the domains associated with SPF and DKIM authentication checks. Alignment requires that these domains match. Only emails that are aligned can pass DMARC. A mismatch in domains will result in a DMARC fail.`**

{% embed url="https://dmarcian.com/what-is-a-dmarc-record/" %}

{% embed url="https://dmarc.org/overview/" %}

## Domain Checker

{% embed url="https://dmarcian.com/domain-checker/" %}
