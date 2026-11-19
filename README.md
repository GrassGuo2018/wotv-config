# wotv-config

WoTV（沃TV）内置源配置，供 App「配置地址」直接导入。

## 文件

| 文件 | 说明 |
| --- | --- |
| `config.json` | TVBox 标准配置：9 个点播源 + 2 组直播源（17 个频道） |
| `live.m3u` | 纯直播播放列表，可在「直播」页单独导入 |

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

## 内容

点播源（接口均实测可用）：红牛、UK、量子、哔嘀、光速、豪华、极速、最多、速播。
其中红牛 / UK / 量子为实测能直拉到播放流的三家。

直播源（逐条实测可拉流）：CCTV-1、CCTV-9、CCTV-12、CCTV-13，以及东方、东南、湖南、浙江、吉林、江西、山西、内蒙古、青海、新疆、延边、安多、人间卫视。
CCTV-2/3/4/5/6/7/8/10/11/14/15/16/17 在公开源中已无可用地址。

## 注意

直播源寿命通常按周计，失效后需重新测换。配置里的地址采集与验证日期为 2026-11-19。
