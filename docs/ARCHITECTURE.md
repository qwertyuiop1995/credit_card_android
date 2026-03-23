# Android 架构设计

## 目标

- 作为补充移动端
- 优先支持查看、同步、拍照、NFC
- 不追求与 iOS 同步上线节奏

## 推荐模块

### app

- Application
- 导航壳
- DI 装配

### domain

- models
- repositories
- usecases

### data

- local-db
- sync
- migration
- serializers

### platform

- nfc
- biometrics
- camera
- file-picker

### feature

- card-list
- card-detail
- card-edit
- import-export
- settings
- stats

## 初始化阶段目录

- `app/`
- `domain/model`
- `domain/usecase`
- `domain/repository`
- `data/local`
- `data/sync`
- `data/migration`
- `platform/nfc`
- `platform/security`
- `platform/media`
- `feature/cardlist`
- `feature/carddetail`
- `feature/cardedit`
- `feature/settings`

