# install_nessus
安裝 Nessus 套件

## POC 安裝CVE(弱掃)工具
- https://www.tenable.com/downloads/nessus?utm_source=nessus-trial-thank-you-update&loginAttempted=true
- port: 8834
- POC(061)、ai40

## 依據：Ubuntu 官方工具，顯示發行版名稱與版本號。
### 查詢系統架構（amd64 / aarch64）
```bash
uname -m
```

```
# 輸出判讀：
x86_64 → amd64
aarch64 → arm64
```

# install
```
# 方法1
sudo apt install Nessus-10.11.1-ubuntu1604_amd64.deb
# 方法2 <-- 採用這個
sudo dpkg -i Nessus-10.11.1-ubuntu1604_amd64.deb
```

## 啟動並驗證服務狀態：

```bash
systemctl start nessusd
systemctl status nessusd --no-pager 
```

## 確認監聽狀態：

```
ss -lntp | grep 8834 
```

 **管理介面**

- Nessus Web UI 位於：

    `https://<主機 IP 或 hostname>:8834/  `

- 初次進入需完成初始化精靈（帳號、授權、plugin download）。