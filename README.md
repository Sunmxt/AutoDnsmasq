# AutoDnsmasq
Dnsmasq GFWList 规则的管理工具。



###### 特性

- GFWList 规则将转换为 Dnsmasq 规则
- 生成域名列表

---

#### 使用方法



###### 生成 Dnsmasq 规则

```bash
./auto_dnsmasq -r <上游DNS服务器>[:<端口>]  # 输出到标准输出
./auto_dnsmasq -r <上游DNS服务器>[:<端口>] -o <路径> # 输出到指定文件
```



###### 生成规则并更新配置文件

```bash
./auto_dnsmasq -r <上游DNS服务器>[:<端口>] -D <配置文件路径> --rules-id <规则集名称>
```

auto_dnsmasq 将规则以下格式更新到配置文件：

>\# !AutoDnsmasqBegin!<规则集名>!
>
>...
>
>规则.....
>
>...
>
>\# !AutoDnsmasqEnd!<规则集名>!

