# RondoDox and its exploitation of XWiki vulnerability

I read some articles about RondoDox and XWiki and I wanted to talk a little about it. Since I am still learning I will ask (sometime naive) questions.
I hope you enjoy !

## Introduction / Presentations

I will began by presenting the objects that will be discussed here.
RondoDox is a botnet. Meaning that, once it's installed on a computer, its goal is to send requests to a target disturb its disponibility. 
> Who use it ? What APT is it linked to ?
XWiki is is a solution to organize information, it is a server hosting information which can be linked to the internet. So it is easily accessible to attack.

For this review I decided to follow the flow of the attack steps and to organise it this way :  
  1) Initial access : RondoDox strategy and the XWiki vulnerability
  2) RondoDox structure

## Initial access : RondoDox strategy and the XWiki vulnerability

  So, RondoDox have a bit of history. According to TrendMicro it was spotted in 2022 during the Pwn2Own campaign but the was discreet for a while. Then recently its activity have skyrocketed after using a "loader-as-a-service" : it uses an other malware to exploit vulnerability and download it self on computers. 
  An example of the vulnerability exploited is the CVE-2025-24893 on XWiki. Its exploitation in the wild was first discovered by VulnCheck. It's a command injection vulnerability. Concretly when a request is made through the RSS media in the SolrSearch functionnality the second parameter (the "text" one) seems to be passed to a command without being sanetized. Meaning it can be read and executed as a command on the computer hosting the XWiki server.  An exemple of malicious request is : 
