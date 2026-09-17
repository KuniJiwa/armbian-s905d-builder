# Armbian S905D Builder

S905D 设备的 Armbian 自动构建仓库。每月 1 号自动构建并发布多内核版本镜像。

## 📥 下载

前往 [Releases](../../releases) 页面，按需选择。

## 📦 镜像说明

每个 Release 包含 6 个内核版本的镜像：

| 内核 | 适用场景 |
|---|---|
| 5.10.y | 老版本，兼容性优先 |
| 5.15.y | 稳定长期支持 |
| 6.1.y | 稳定长期支持 |
| 6.6.y | 稳定长期支持 |
| 6.12.y | 较新特性 |
| 6.18.y | 最新特性 |

文件名格式：`Armbian_{版本}_amlogic_s905d_bookworm_{内核}_server_{日期}.img.gz`

选一个内核版本下载即可，不确定用哪个就选 6.1.y 或 6.6.y。

## 💾 刷机

1. 解压 `.img.gz`
2. 写入启动介质（U 盘 / SD 卡，或直接写设备 eMMC）
   - 工具：`balenaEtcher`、`dd`、或设备自带的 `armbian-install`
3. 从对应介质启动，默认账号 `root` / 密码 `1234`
4. 首次登录会提示改密码和创建普通用户

## ✨ 关于 Rootfs 瘦身

本仓库镜像比上游默认镜像少 500 MB 左右占用（删除文档、多余语言包、高通固件、APT 缓存），刷入后系统盘空间更充裕。

## 🙏 来源

构建流程基于 [ophub/amlogic-s9xxx-armbian](https://github.com/ophub/amlogic-s9xxx-armbian)，本仓库附加了 Rootfs 瘦身补丁与自动构建逻辑。
