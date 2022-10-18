**chrome安装switchyOmega插件**

**配置代理**

代理配置代理服务器ip为127.0.0.1  代理端口8090

**下载BurpSuite并代理**

- 在Proxy -> intercept 中配置 配置代理服务器
- 点击intercept is off

**构造攻击请求**

页面构造创建视图的Post请求，在Contents找到待攻击的url，右键 send to intruder或send to repeater，repeater是一次请求，intruder是构造多次攻击

**构造多线程并发攻击**

- 选择一个值设置为载荷位置，用以遍历线程数

- Payload中选择payload type为Numbers类型，构造线程数为1-999，step递增规则为1
- OPtions中选择Number of threads为100，构造并发线程数为100
