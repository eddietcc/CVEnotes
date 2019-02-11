## DBNinja ver 3.2.7 Reflect Cross-Site Script (R-XSS) Vulnerability Description
- Author: Eddie TC CHANG, YUNG-HAO TSENG, YU-HSIANG HUANG
- Contact: eddietcchang@gmail.com; 0xuhaw@gmail.com; huang.yuhsiang.phone@gmail.com
---
### Testing Target
- Product: DBNinja
- Version: 3.2.7
- Official Website: https://www.dbninja.com/
- Github: N/A

### Summary
DBNinja ver 3.2.7 exist broken authentication vulnerability.

### Description
The attacker designed a URL with a specific `sessid`, if the victim browsed the URL and then logged into NinjaDB. The attacker can login to NinjaDB as the victim by using this `sessid`.
 
### Concept
1. Design a URL with a specific “sessid”, and the victim browsed the URL.  
 **Payload**: `http://127.0.0.1/dbninja/data.php?sessid=exploittest&action=ver`
![](./png/1.png)
2. Then the victim login as the admin account.
![](./png/2.png)
3. An attacker can use the victim's permission to operate DBNinja.
![](./png/3.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MzQ5NDM5MDVdfQ==
-->