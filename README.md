# Shodan-IDOR

I found a vulnerability within the popular platform that allows one to access some membership features without even having a registered account. That is an example of Insecure Direct Object References—an important critical security vulnerability exposing sensitive data.

Affected Membership Packages: Academic Users, Small Business API Subscription, and up.
<br>
Parameter: vuln (Restricted)

![image](https://github.com/user-attachments/assets/d0c15f10-ef0e-415c-92c7-98f7c26bafb8)

![image](https://github.com/user-attachments/assets/ec27c6b9-059a-4b83-b5a9-322379f3f92a)

How It Works:
The URL parameters can be tampered with to bypass access controls and retrieve information intended for higher-tier members. For example, using any restricted params in the URL and allows grouping the result set by IP addresses without the membership normally required for this action.

IDOR Link: 
```
- https://www.shodan.io/search/facet?query=vuln%3Acve-2021-34473&facet=ip
- You can also use country param (IL used in this example): https://www.shodan.io/search/facet?query=vuln%3Acve-2021-34473+country%3AIL&facet=ip
```

(You need to change the CVE you want to search in the URL and you can also to choose how you want to group the list with facet parameter. in this example I used to group them for IP's.

Proof of Concept (PoC):

![Bypass PoC](https://github.com/user-attachments/assets/aa5ab410-9a0b-419b-b970-2588fc976316)

Reporting and Responses<br>
I immediately reported this issue to the platform owners—Shodan—, and they acknowledged the vulnerability.

![image](https://github.com/user-attachments/assets/56f69e6a-15e6-416f-92b9-975c5a3c98cb)
