## 固定DNS
1. disable auto generate 

vim /etc/wsl.conf
```txt
[network]
generateResolvConf=true
```

2. setting
```bash
sudo rm /etc/resolv.conf
sudo bash -c 'echo "nameserver 8.8.8.8" > /etc/resolv.conf'
sudo chattr +i /etc/resolv.conf
```


## 启用systemd

1. wsl更新到最新
```powershell
wsl --update
```
2. linux内启用systemd 
vim /etc/wsl.conf
```txt
[boot]
systemd=true
```

3. 重启wsl
```powershell
wsl --shutdown
```

