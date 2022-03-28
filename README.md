# Spring-Cloud-Function-SPEL-RCE

# 漏洞详情
当Spring Cloud Function 启用动态路由functionRouter时， HTTP请求头 spring.cloud.function.routing-expression参数存在SPEL表达式注入漏洞，攻击者可通过该漏洞进行远程命令执行。
# 影响版本
3.0.0.RELEASE <= Spring Cloud Function <= 3.2.2
# 漏洞环境
https://github.com/N1ce759/Spring-Cloud-Function-SPEL-RCE
JDK15！
![image](https://user-images.githubusercontent.com/100123029/160384105-7eab286d-ddc8-4a39-8f27-23904c39e6e2.png)

# 漏洞复现
POC:
```

POST /functionRouter HTTP/1.1
Host: localhost:8080
spring.cloud.function.definition: reverseString
Content-Type: text/plain
Content-Length: 3
abc
```
![image](https://user-images.githubusercontent.com/100123029/160383973-fe42241e-58f3-4b66-b5f6-0a853c00db29.png)


# 漏洞分析
参考https://mp.weixin.qq.com/s/cEOXkEgBO6IiuBhMXj_SMQ
