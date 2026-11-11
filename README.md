# Maple iStoreOS for NanoPi R4S (4GB)

为 NanoPi R4S 4GB 定制的 iStoreOS 云编译配置。

## 目标配置
- 设备：FriendlyARM NanoPi R4S（4GB）
- 上游：iStoreOS `istoreos-25.12` 分支
- 科学上网：Nikki（通过独立 feed 尝试集成）
- Docker：Docker Engine + LuCI Docker 管理界面
- 构建：GitHub Actions

## 如何编译
1. 打开仓库的 **Actions** 页面。
2. 如果首次使用，按 GitHub 提示启用 Actions。
3. 进入 **Build Maple iStoreOS (R4S)**。
4. 点击 **Run workflow**，再点击绿色按钮。
5. 编译完成后进入该次运行页面的 **Artifacts** 下载固件。

## 注意
- 这是个人定制构建配置，不是 iStoreOS 官方发布。
- 首次编译可能因上游分支、软件包 feed 或 GitHub Runner 磁盘空间变化而失败；请查看 Actions 日志。
- 刷机前务必备份当前配置。确认固件文件名含 `friendlyarm_nanopi-r4s`，不要刷 R4SE 或其他机型镜像。
- 首次先用 TF 卡测试，确认网络、Nikki 和 Docker 正常后再考虑迁移。
- 默认管理地址沿用 iStoreOS 该设备配置；首次启动后请立即修改 root 密码。

## 目录
- `.github/workflows/build.yml`：云编译工作流
- `config/r4s.config`：R4S 目标与基础软件包配置
