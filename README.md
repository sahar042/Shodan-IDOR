# Shodan-IDOR

I found a vulnerability within the popular platform that allows one to access some membership features without even having a registered account. That is an example of Insecure Direct Object References—an important security vulnerability exposing sensitive data.

Affected Membership Packages: Academic Users, Small Business API Subscription, and up.
<br>
Filter query: vuln (Restricted), tag (Restricted)

![image](https://github.com/user-attachments/assets/d0c15f10-ef0e-415c-92c7-98f7c26bafb8)

![image](https://github.com/user-attachments/assets/ec27c6b9-059a-4b83-b5a9-322379f3f92a)

![image](https://github.com/user-attachments/assets/b45fcaf2-4a44-4d2a-be3f-c70955e8b041)

How It Works:
The URL parameters can be tampered with to bypass access controls and retrieve information intended for higher-tier members. For example, using any restricted params in the URL and allows grouping the result set by IP addresses without the membership normally required for this action.

IDOR Link: 
```
- You can use any Shodan query filters without the need of registered Shodan account and also use the enterprise query filters such as 'vuln' or 'tag'.
- https://www.shodan.io/search/facet?query=vuln%3Acve-2021-34473&facet=ip
- https://www.shodan.io/search/facet?query=tag:honeypot&facet=ip
```

(You need to change the CVE you want to search in the URL and you can also to choose how you want to group the list with facet parameter. in this example I used to group them for IP's.

Proof of Concept (PoC):

![Bypass PoC](https://github.com/user-attachments/assets/aa5ab410-9a0b-419b-b970-2588fc976316)

Reporting and Responses<br>
I immediately reported this issue to the platform owners—Shodan—, and they acknowledged the vulnerability.

Credits: Sahar Shlichove.<br>
Linkedin post: https://www.linkedin.com/posts/activity-7234828819507929088-Iwx5?utm_source=share&utm_medium=member_desktop
