# EasyTier Connect

在 Minecraft 中一键启动陶瓦联机（Terracotta），点击按钮即可打开联机网页。

## 使用

1. 安装 Mod（Fabric 1.20.1+，无需 Fabric API）
2. 启动游戏，主菜单右下角 / 暂停菜单底部会出现 **「☁ 陶瓦联机」** 按钮
3. 点击按钮 → 自动启动陶瓦后台 → 弹出浏览器网页
4. 在网页中创建/加入房间，管理联机

## 构建

```bash
# 1. 先下载陶瓦联机二进制
#    从 https://github.com/burningtnt/Terracotta/releases 下载
#    terracotta-0.4.2-windows-x86_64-pkg.tar.gz
#    解压出 terracotta-0.4.2-windows-x86_64.exe → 重命名为 terracotta.exe
#    放到 src/main/resources/natives/ 目录

# 2. 编译
./gradlew build

# 3. 输出在 build/libs/easytier_connect-1.0.0.jar
```

## 依赖的运行时

- 需要 VC++ 运行库（`VCRUNTIME140.DLL`，打包在 Terracotta 发行包中）

## 技术原理

Mod 内嵌了陶瓦联机（Terracotta）二进制，通过 Mixin 在 MC 主菜单和暂停菜单添加按钮。
点击按钮时启动 Terracotta 子进程，检测 Web 端口后自动打开浏览器，所有联机操作由陶瓦的 Web UI 完成。

## 协议

MIT