# 启用全局代理 

## 1. 宿主机安装clash for windows

## 2. clash启用TUN Mode
```yaml
dns:
  nameserver:
    - 114.114.114.114
  fallback:
    - 8.8.8.8
```
```yaml
dns-hijack:
  - 198.18.0.2:53
```

## 3. 宿主机配置无污染的dns
[wsl配置dns](wsl.conf.md)


## 说明
理论上宿主机clash已经启用了防污染的dns，wsl也会受益，不需要配置第3项<br>
实际上，wsl内的域名默认会被解会被解析成198.18.0.x的fake-ip,说明dns-hijack有生效
但是，下面的却是无响应
```bash
curl www.google.com
```
猜测wsl在请求198.18.0.x时，经过了宿主机网关时被NAT了，导致clash从NAT后的包里匹配不了198.18.0.x<br>


