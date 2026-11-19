# wotv-config

WoTV（沃TV）内置源配置，供 App 直接导入。

## 文件

| 文件 | 说明 |
| --- | --- |
| `config.json` | TVBox 标准配置：9 个点播源 + 2 组直播源（17 个频道） |
| `live.m3u` | 纯直播播放列表，可单独使用 |

## 导入地址

直连：
```
https://raw.githubusercontent.com/GrassGuo2018/wotv-config/main/config.json
```

国内反代（直连打不开时用这两个，均实测可用）：
```
https://gh.zrfme.com/https://raw.githubusercontent.com/GrassGuo2018/wotv-config/main/config.json
https://gh-proxy.com/https://raw.githubusercontent.com/GrassGuo2018/wotv-config/main/config.json
```

直播列表（m3u）：
```
https://raw.githubusercontent.com/GrassGuo2018/wotv-config/main/live.m3u
```

## 平台差异（重要）

**Android / 电视端**：设置页里有「配置地址」，填上面任意一条 URL，点导入即生效。

**Windows 桌面版**：**没有配置入口，上面这些地址在 Windows 上无处可填**。2026-11-19 在 1.1.72（zip 与 Setup 同版）逐项实测：

- 设置页只有 6 项——外观、首页频道、播放器、数据与记录、诊断、免责声明、关于，没有「配置地址」，也没有「影视源 / 接口配置」；窗口最大化切 TV 布局后仍是这 6 项。
- 本地配置在 `%APPDATA%\com.example\沃TV\shared_preferences.json`，字段 `flutter.api_url` 原值是内置标识 `wogg://fty`；改成 http 地址再启动会被自动重置回 `wogg://fty`，说明桌面版只认内置源标识。
- 程序里没有任何本地配置文件读取路径，丢 json 到目录也没用。
- 它自带的直播（咪咕央视 / 咪咕卫视 / 国内官方 / 地区官方 / 卫星官方 / 评审最佳）实测 CCTV-1 综合可直接播放，本来就够用。

所以在 Windows 上想用这份配置，只能：① 去 Android / 电视端导入；② 换一个支持 TVBox 配置的 Windows 客户端；③ 等作者给桌面端加入口（需改私有源码，外部做不了）。

## 内容

点播源（接口均实测可用）：红牛、UK、量子、哔嘀、光速、豪华、极速、最多、速播。
其中红牛 / UK / 量子为实测能直拉到播放流的三家。

直播源（逐条实测可拉流）：CCTV-1、CCTV-9、CCTV-12、CCTV-13，以及东方、东南、湖南、浙江、吉林、江西、山西、内蒙古、青海、新疆、延边、安多、人间卫视。
CCTV-2/3/4/5/6/7/8/10/11/14/15/16/17 在公开源中已无可用地址。

## 注意

直播源寿命通常按周计，失效后需重新测换。配置里的地址采集与验证日期为 2026-11-19。
