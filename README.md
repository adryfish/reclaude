# reclaude

这是一个`Claude`官网的镜像项目，无需访问官方站点即可使用`Claude`。

## 使用方式

使用`Docker`镜像或二进制可执行文件进行部署。

### Docker
```sh
docker run -d \
  -e TZ="America/Los_Angeles" \
  -e SESSION_KEY=your_claude_session_key \
  -e ALL_PROXY=http://proxy.server:port \
  adryfish/reclaude
```

### Docker Compose
创建 `docker-compose.yml` 文件，内容如下：
```yaml
services:
  reclaude:
    image: adryfish/reclaude
    environment:
      TZ: America/Los_Angeles
      SESSION_KEY: your_claude_session_key
      ALL_PROXY: http://proxy.server:port
    restart: unless-stopped
```
然后运行以下命令启动容器：
```sh
docker-compose up -d
```

### 二进制文件
1. 下载适用于您平台的二进制文件。
<!-- - [Windows](https://example.com/windows-reclaude) -->
- [Linux 下载](https://github.com/adryfish/reclaude/releases/download/untagged-fc83461ddb1a63afe27f/reclaude_linux)
<!-- - [macOS](https://example.com/macos-reclaude) -->
2. 运行命令：
   ```sh
   ./reclaude
   ```

## 环境变量

| 变量名       | 说明                 | 默认值  |
|-------------|--------------------|--------|
| TZ          | 时区                 | UTC    |
| SESSION_KEY | Claude 账号的 Session Key | 必填    |
| ALL_PROXY   | 代理服务器地址          | 选填    |

请确保 `SESSION_KEY` 已正确配置，否则无法正常使用。


## 用户交流

扫码加入QQ群与其他用户交流：

<img src="qqgroup.jpg" alt="QQ群二维码" width="300">