## MariaDB ver 10.3.7 and 10.3.8 has Denial of Service Vulnerability Description
- Author: YU-HSIANG HUANG, YUNG-HAO TSENG, Eddie TC CHANG
- Contact: huang.yuhsiang.phone@gmail.com; 0xuhaw@gmail.com; eddietcchang@gmail.com
---
### Testing Target
- Product: MariaDB
- Version: 10.3.7 and 10.3.8
- Official Website: https://mariadb.org/
- Github: https://github.com/MariaDB

### Summary
MariaDB version in 10.3.7 and 10.3.8 has Denial of Service (DoS) vulnerability.

### Description
We test the MariaDB 10.3.7 and 10.3.8 version exist DoS vulnerability when any user modifies column name and comment in any table at the same time.
 
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
eyJoaXN0b3J5IjpbMTY4Mjc4NzA1NywtMjA4ODc0NjYxMl19
-->