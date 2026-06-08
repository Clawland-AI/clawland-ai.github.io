# API 文档

Clawland-AI 提供以下核心 API。

## PicClaw API

### 图像识别

```js
PicClaw.recognize(image)
```

- `image`：输入图像对象。
- 返回：识别结果。

## NanoClaw API

### 推理

```js
NanoClaw.infer(data)
```

- `data`：输入数据。
- 返回：推理结果。

## MicroClaw API

### 设备集成

```js
MicroClaw.connect(device)
```

- `device`：设备对象。
- 返回：连接状态。

## MoltClaw API

### 模型训练

```js
MoltClaw.train(dataset)
```

- `dataset`：训练数据集。
- 返回：训练结果。

## Clawland Fleet API

### 设备管理

```js
ClawlandFleet.manage(devices)
```

- `devices`：设备列表。
- 返回：管理结果。

## 技能相关 API

### 注册技能

```js
Skill.register(skill)
```

- `skill`：技能对象。
- 返回：注册状态。

## 术语说明

- PicClaw、NanoClaw、MicroClaw、MoltClaw、Clawland Fleet 均为产品名称，保持原文不变。
- 技能（Skill）指可扩展的 AI 功能模块。
