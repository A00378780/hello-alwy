# xray for Alwaysdata

在 Alwaysdata 虚拟主机上部署 xray 节点

## 项目特点

* 本项目用于在 Alwaysdata 上部署 xray ，采用的方案为 xray + WebSocket + VMess/Vless/Trojan/Shadowsocks + TLS
* vmess 和 vless 的 uuid 或 trojan 和 shadowsocks 的密码，路径既可以自定义，又或者使用默认值
* 部署完成如发现不能上网，请检查域名是否被墙，如域名被墙，可使用 Cloudflare CDN 或者 worker 解决。

## 部署

* 注册 [Alwaysdata](https://www.alwaysdata.com/)
* 创建一个 Web 项目
* 进入其的 SSH，输入以下命令，以下载项目文件

```shell
wget -N https://raw.githubusercontent.com/A00378780/hello-alwy/main/web.sh && chmod +x web.sh
```

* 在网站设置中，按照下图设置启动项并设置环境变量

![image](https://user-images.githubusercontent.com/122191366/230263139-b461e5a4-c52a-4afe-b4ce-e36903ed6372.png)

* 项目用到的环境变量
  | 变量名 | 是否必须 | 默认值 | 备注 |
  | ------------ | ------ | ------ | ------ |
  | UUID         | 否 | de04add9-5c68-8bab-950c-08cd5320df18 | 可在线生成 https://www.uuidgenerator.net/ |
  | VMESS_WSPATH | 否 | /vmess | 以 / 开头 |
  | VLESS_WSPATH | 否 | /vless | 以 / 开头 |
  | TROJAN_WSPATH | 否 | /trojan | 以 / 开头 |
  | SS_WSPATH | 否 | /shadowsocks | 以 / 开头 |
  | NEZHA_SERVER | 否 |        | 哪吒探针服务端的 IP 或域名 |
  | NEZHA_PORT   | 否 |        | 哪吒探针服务端的端口 |
  | NEZHA_KEY    | 否 |        | 哪吒探针客户端专用 Key |

