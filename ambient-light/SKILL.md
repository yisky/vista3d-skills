---
name: ambient-light
description: >
  Add uniform scene lighting with AmbientLight.
  Use when attaching ambient light to an entity, setting color or intensity, or enabling and disabling it.
  适用于给实体添加 AmbientLight、设置 color / intensity、启用或禁用环境光时。
---

# AmbientLight

## 何时用

要给实体加均匀、无方向的环境光，或改 `color` / `intensity` 时，用 `AmbientLight`。

## 最小示例

```ts
import { AmbientLight } from '@vista3d/core';
const entity = scene.rootEntity.createChild();
entity.addComponent(AmbientLight, {
    color: '#ffffff',
    intensity: 1
});
entity.removeComponent(AmbientLight);
```

## 限制

- 启用时把原生灯光挂到实体的 `Transform.object3D` 下；禁用时卸下；销毁时会 `dispose`。
- `enabled` 只是用户开关，和实体是否在层级中激活无关；两边都为 true 组件才会运行。
- 构造时不会调用生命周期，实体进入层级后才开始激活。
- 不要直接调用 `destroy()`，由 `entity.removeComponent(AmbientLight)` 调用。
