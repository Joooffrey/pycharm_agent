# DeepSeek Agent Linux 离线包

本目录用于把 DeepSeek Agent 插件和适配的 Linux 版 PyCharm 放到同一个位置，便于在 Linux 上离线安装。

## 文件

- `deepseek-pycharm-agent-plugin-0.1.0.zip`
  - DeepSeek Agent 插件包
  - 适配 IntelliJ Platform / PyCharm `2025.2+`
- `pycharm-community-2025.2.5.tar.gz`
  - Linux 免费版 PyCharm Community
  - 这是插件工程使用 `pycharmCommunity("2025.2.5")` 构建验证的目标版本

## 中文语言包

已检查 `pycharm-community-2025.2.5.tar.gz`，其中自带中文语言包：

```text
pycharm-community-2025.2.5/plugins/localization-zh/lib/localization-zh.jar
```

因此不需要额外下载中文语言包 zip。安装后如未自动启用中文，可在 PyCharm 中打开：

```text
Settings -> Plugins -> Installed -> Chinese (Simplified) Language Pack
```

确认插件启用后重启 IDE。

## 其他依赖插件

DeepSeek Agent 的 `plugin.xml` 只显式依赖：

```text
com.intellij.modules.platform
com.intellij.modules.json
```

这两项在 PyCharm Community 2025.2.5 中为平台/内置插件，不需要另行下载。Python 支持也随 PyCharm Community 提供。

## Linux 安装步骤

```bash
mkdir -p ~/apps
tar -xzf pycharm-community-2025.2.5.tar.gz -C ~/apps
~/apps/pycharm-community-2025.2.5/bin/pycharm.sh
```

在 PyCharm 中安装插件：

```text
Settings -> Plugins -> Install Plugin from Disk...
```

选择：

```text
deepseek-pycharm-agent-plugin-0.1.0.zip
```

安装后重启 PyCharm。

## SHA-256

```text
0f743282aad6b7ec7b284206cfbc84e3557bb8a0ff5182f2bd4d64cc5a811f69  deepseek-pycharm-agent-plugin-0.1.0.zip
7f49a014f53f0f6f7c46f6710b131f390302287f4046b606331d88081cdb551f  pycharm-community-2025.2.5.tar.gz
```
