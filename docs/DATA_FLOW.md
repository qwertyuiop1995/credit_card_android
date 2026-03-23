# Android 数据流

## 1. 总体目标

`Android` 端作为补充移动端，数据流必须和 `iOS` 保持同一协议思路。

## 2. 导入流程

1. 用户选择文件
2. `FilePicker` 读取文本
3. `JsonParser` 解析内容
4. `SchemaMigrator` 按版本迁移
5. `ValueNormalizer` 做值标准化
6. `ImportValidator` 校验
7. `SharedCardRepository` 落库
8. `ClientMetaRepository` 补本地元数据
9. Compose 页面刷新

## 3. 展示流程

1. 查询 `SharedCard`
2. 合并 `ClientMeta`
3. 按需读取 `Asset`
4. 计算 `DerivedView`
5. Compose 渲染

## 4. 编辑流程

1. 用户提交表单
2. 生成新的 `SharedCard`
3. 更新时间戳
4. Repository 写入数据库
5. 刷新列表和详情

## 5. 导出流程

1. 查询全部 `SharedCard`
2. 组装协议对象
3. `source = android`
4. 序列化 JSON
5. 分享或写入文件

## 6. NFC 与相机

### NFC

- Tag 数据进入本地扩展层
- 不直接进 `cards[]`

### 相机

- 照片进入 `Asset`
- OCR 结果如需共享，必须经过字段映射后写入 `SharedCard`

## 7. 冲突处理

1. `id` 一致视为同一卡片
2. 比较 `lastModifyTime`
3. 时间新的覆盖旧的

