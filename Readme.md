1 、 docker-compose.yml srs CANDIDATE 改成访问ip

2、 给ip配置HTTPS服务
```
cd nginx/cert

生成证书
openssl req -new -key privatekey.pem -out private-csr.pem

//回车之后会有很多信息需要输入，可以直接回车通过。
//但在Common Name这里需要注意填入你的IP或者域名：
//Common Name (e.g. server FQDN or YOUR name) []:xxx.xxx.xxx.xxx

自签名证书

openssl x509 -req -days 3650 -in private-csr.pem -signkey privatekey.pem -out certificate.pem

```