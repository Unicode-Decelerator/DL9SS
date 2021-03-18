**专为大连九中打造的直播系统**

# 服务器功能

- [x] **直播协议：** RTMP、HTTP(S)-FLV、HTTP(S)-TS、HLS（支持HTTPS）、HLS+（支持HTTPS）、DASH（支持HTTPS）。
- [x] **音视频编码：** H264、H265、MP3、AAC。
- [x] **直播录像：** FLV文件格式和TS文件格式。
- [x] **GOP缓存：** 实现秒开和内存复用。
- [x] **application支持通配符：** “ * ”号通配符实现自动匹配推拉流时使用的application名字，无需累赘的配置。
- [x] **VHOST功能：** 支持配置多个server域名。
- [x] **控制台接口：** 通过HTTP API接口控制推流、拉流以及录像过程。
- [x] **配置动态加载：** 修改配置文件后无需对nginx做任何操作就可读取最新配置。
- [x] **流量计费：** 通过配置自定义流量日志。
- [x] **变量参数配置：** 配置文件中使用变量。
- [x] **进程间回源：** 进程间相互拉流，解决了原生nginx-rtmp-module模块多进程拉流失败的问题。
- [x] **集群化功能：** 服务器间推拉流功能（http-flv、rtmp协议）。
- [x] **html5网页播放器：** [pingos-player](https://github.com/pingostack/pingos-player)播放器将持续兼容各浏览器平台，以及多种直播协议。

## 部署方法

- 直接安装到系统
    ```bash
    # 快速安装
    git clone https://github.com/Unicode-Decelerator/DL9SS.git

    cd DL9SS

    ./release.sh -i

    # 启动服务
    cd /usr/local/pingos/
    ./sbin/nginx
    ```

## 操作说明

### 推流

推流地址：rtmp://ip/live/流名

### 播放地址

- rtmp 播放：rtmp://ip/live/流名

- http(s)-flv 播放：http(s)://ip/flv/流名

- hls 播放：http(s)://ip/hls/流名.m3u8

- hls+ 播放：http(s)://ip/hls2/流名.m3u8

- http(s)-ts 播放：http(s)://ip/ts/流名

### 直播流监控后台

> 访问地址：http://ip/rtmp_stat
> 通过该页面可以查看当前正在发生的推流和播放记录。


### html5播放器

> 访问地址： http://ip/h5player/flv
> 这个播放器是基于flv.js的网页播放器，可以实现无插件播放http-flv直播流。
> 一旦你能够访问这个页面，说明你的直播服务器已经成功搭建起来了。

**本项目关键代码来自PingOS，感谢开源项目PingOS对我们学校提供的支持**
