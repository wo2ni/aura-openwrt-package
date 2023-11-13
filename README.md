![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=kenzok8&show_icons=true&theme=radical)
<div align="center">
<h1 align="center"smmall</h1>
<img src="https://img.shields.io/github/issues/kenzok8/small?color=green">
<img src="https://img.shields.io/github/stars/kenzok8/small?color=yellow">
<img src="https://img.shields.io/github/forks/kenzok8/small?color=orange">
<img src="https://img.shields.io/github/languages/code-size/kenzok8/small?color=blueviolet">
</div>

<img src="https://v2.jinrishici.com/one.svg?font-size=24&spacing=2&color=Black">


* 把openwrt-packages与small仓库重新归类，ssr、passwall、vssr以及依赖合并small

#### 使用方式
```yaml

默认ssr与passwall的插件与依赖整合包

使用方法：将整合包上传到openwrt设备的tmp目录，输入命令 opkg install *.ipk

默认压缩包里包含ssr passwall bypass passwall2 插件

如果单独安装ssr与依赖，rm -rf {*passwall*,*bypass*,*vssr*}
```

* 喜欢追新的可以去下载small-package，该仓库每天自动同步更新

* [small-package仓库地址](https://github.com/kenzok8/small-package) 


##### 插件每日更新下载:
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/kenzok8/small?style=for-the-badge&label=插件下载)](https://github.com/kenzok8/small/releases/latest)

+ [ssr+passwall依赖仓库](https://github.com/kenzok8/small)

+ [openwrt固件与插件下载](https://op.dllkids.xyz/)

#### 使用
一键命令
```yaml
sed -i '$a src-git kenzo https://github.com/kenzok8/openwrt-packages' feeds.conf.default
sed -i '$a src-git small https://github.com/kenzok8/small' feeds.conf.default
git pull
./scripts/feeds update -a
./scripts/feeds install -a
make menuconfig
```

#### 注意
编译新版Sing-box和hysteria，需golang版本1.20或者以上版本 ，可以用以下命令
```yaml
pushd feeds/packages/lang
rm -rf golang && svn co https://github.com/openwrt/packages/branches/openwrt-23.05/lang/golang
popd
```



# aura-openwrt-package
aura-openwrt-package

- openwrt 固件编译自定义主题与软件

| 软件名                       | 说明                   | 中文说明    |
| -----------------------------|------------------------| ------------|
| luci-app-tencentddns         | TencentDDNS            | 騰訊DDNS
| luci-app-oaf                 | Apply filtering        | 应用过滤    |
| luci-app-wizard              | application wizard     | 应用程序向导|
| luci-app-pcimodem            | PCI Modem Server       | 移动网络    |
| luci-app-wolplus             | Wake on LAN Plus       | 網絡喚醒    |
| luci-app-argon-config        | argon theme config     | argon主題配置|
| luci-app-argone-config       | argone theme config    | argon 主題配置|
| luci-app-sms-tool            | Simple user interface to handle SMS / USSD / AT commands via sms_tool application. OpenWrt =< 19.07 | 简单的用户界面，可通过 sms_tool 应用程序处理 SMS/USSD/AT 命令, OpenWrt =< 19.07|
| luci-app-ramfree             | Ram release            | 內存釋放    |
| luci-app-alist               |  file list program   | 支持多存储的文件列表程序   |
| luci-app-dnsfilter           | dns ad filtering            | 基于DNS的广告过滤        |
| luci-app-openclash           | openclash proxy            |  clash的图形代理软件      |
| luci-app-advanced            | System advanced settings               | 系统高级设置        |
| luci-app-wechatpush          | WeChat/DingTalk Pushed plugins    |   微信/钉钉推送        |
| luci-theme-atmaterial_new    | atmaterial theme (adapted to luci-18.06) | Atmaterial 三合一主题        |
| luci-app-aliddns             | aliyunddns         |   阿里云ddns插件      |
| luci-app-eqos                | Speed ​​limit by IP address       | 依IP地址限速      |
| luci-app-gost                | https proxy      | 隐蔽的https代理   |
| luci-app-adguardhome         | Block adg          |  AdG去广告      |
| luci-app-smartdns            | smartdns dns pollution prevention     |  smartdns DNS防污染       |
| luci-app-passwall            | passwall proxy      | passwall代理软件        |
| luci-theme-argone            | argone theme           | 修改老竭力主题名     |
| luci-app-argone-config       | argone theme settings            |  argone主题设置      |
| luci-app-ssr-plus            | ssr-plus proxy              | ssr-plus 代理软件       |
| luci-app-mosdns              | mosdns dns offload            |DNS 国内外分流解析与广告过滤        |
| luci-app-store               | store software repository            |  应用商店   |
| luci-app-unblockneteasemusic | Unlock NetEase Cloud Music         | 解锁网易云音乐   |
| luci-app-aliyundrive-webdav  | Aliyun Disk WebDAV Service            |  阿里云盘 WebDAV 服务   |
| luci-app-amlogic  | Amlogic Service             |  晶晨宝盒   |

