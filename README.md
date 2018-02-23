# AutoDnsmasq
自动更新 Dnsmasq 的 GFWList 规则。



适用于 Dnsmasq ，用于快速解决 DNS 污染问题。

AutoDnsmasq 每天自动维护 Dnsmasq 规则，保持规则处于最新状态。



**list2dnsmasq** 是一个灵活的规则转换工具，**auto-dnsmasq** 为规则的自动维护工具。

---

### auto-dnsmasq

- 安装

  ```bash
  wget https://raw.githubusercontent.com/Sunmxt/AutoDnsmasq/master/auto-dnsmasq && bash ./auto-dnsmasq install
  ```

- 设置更新参数

  ```bash
  auto-dnsmasq set-dns <上游DNS服务器>
  auto-dnsmasq set-dns-port <上游DNS服务器端口>
  auto-dnsmasq set-config	<dnsmasq 配置文件路径> #可选，默认将规则更新到 /etc/dnsmasq.conf
  auto-dnsmasq update # 立即更新 dnsmasq 规则
  ```

- 启用更新：

  ```bash
  auto-dnsmasq enable
  ```

---

### list2dnsmasq 

#### 简单使用

- 生成 Dnsmasq 规则

  ```bash
  list2dnsmasq -r <上游DNS服务器>[:<端口>]  # 输出到标准输出
  list2dnsmasq -r <上游DNS服务器>[:<端口>] -o <路径> # 输出到指定文件
  ```

- 生成规则并更新配置文件

  ```bash
  list2dnsmasq -r <上游DNS服务器>[:<端口>] -D <配置文件路径> --rules-id <规则集名称>
  ```

  list2dnsmasq 将规则以下格式更新到配置文件：

  ```
  # !AutoDnsmasqBegin!<规则集名>!

  ...

  规则.....

  ...

  # !AutoDnsmasqEnd!<规则集名>!
  ```

#### 更多选项

请查看内置的帮助信息：

``` bash
list2dnsmasq --help
```



