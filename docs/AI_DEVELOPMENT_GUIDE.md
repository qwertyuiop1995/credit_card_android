# Android 开工文档

## 1. 项目目标

本项目是 `Android` 原生客户端，必须使用：

- `Kotlin`
- `Jetpack Compose`

禁止改成：

- XML 页面为主的新方案
- React Native
- Flutter

## 2. 架构要求

- UI 层：Compose
- 状态层：ViewModel
- 业务层：UseCase
- 数据层：Repository + Local DB + Sync

## 3. 必须遵守

1. 不允许把平台权限状态写入共享 JSON
2. 不允许把照片本地路径写入 `SharedCard`
3. 导入导出只能使用统一协议
4. 页面层不能直接操作 SQLite

## 4. 开发顺序

1. Domain 模型
2. JSON 解析器
3. Local DB
4. 列表页
5. 详情页
6. 编辑页
7. 导入导出
8. NFC / CameraX

## 5. Compose 开发要求

- 页面只负责状态展示
- 业务逻辑放到 ViewModel 或 UseCase
- 不要把导入导出逻辑写进 Composable

## 6. 后续 AI 要求

- 先看 `docs` 目录
- 不得自行新增共享字段
- 新增字段前必须先更新协议文档和 schema

