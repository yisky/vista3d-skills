---
name: webgl-engine
description: >
  Create a WebGL render loop with WebGLEngine.
  Use when constructing the engine, setting renderer options, or disposing it.
  适用于创建 WebGLEngine、配置 renderer、释放引擎、WebGL 渲染循环时。
---

# WebGLEngine

## 何时用

要用 WebGL 创建引擎、配置 `renderer`、或调用 `dispose` 时，用 `WebGLEngine`。不要 `new Engine`。

## 最小示例

```ts
import { WebGLEngine } from '@vista3d/core';
const viewport = document.createElement('div');
viewport.style.width = '100%';
viewport.style.height = '100%';
document.body.appendChild(viewport);
const engine = new WebGLEngine({
    maxFps: 60,
    renderer: {
        clearColor: 'rgb( 201, 207, 183 )',
        viewport
    }
});
```

```ts
import { WebGLEngine } from '@vista3d/core';
const canvas = document.getElementById('render-canvas') as HTMLCanvasElement;
const engine = new WebGLEngine({
    renderer: {
        canvas,
        clearColor: '#1a1a2e'
    }
});
```

```ts
engine.dispose();
```

## 限制

- 构造时会把渲染器挂到文档并开启动画循环。
- 不要直接 `new Engine`。
- 设置了 `renderer.canvas` 时，`renderer.viewport` 会被忽略。
- `maxFps` ≤ 0 表示不限帧率。
- `dispose()` 会释放引擎并强制丢失 WebGL 上下文。
