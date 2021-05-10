# memory-analyzer

一个不用开箱就能用的 screeps 内存可视化工具。

## 使用方法

**方法1 直接运行 🌠**：打开游戏，将下方代码直接粘贴进游戏控制台中执行即可

```
`<script>
const sendMemoryInfo = ({ source }) => {
    removeEventListener('message', sendMemoryInfo);
    source.postMessage(${JSON.stringify(Memory)}, '*')
};
addEventListener('message', sendMemoryInfo);
open('https://screeps-cn.github.io/memory-analyzer/main.html', '_blank', 'fullscreen=no');
<\/script>`.replace(/\n/g, '')
```

**方法2 保存到游戏代码 💾**：你可以在你的游戏代码中添加如下逻辑：

```js
global.showMemory = () => /** 上面那一堆代码 */
```

之后直接在控制台中执行 `showMemory()` 即可查看。如有疑问可以参考如下动图：

![](./使用示例.gif)

## 本地调试

- 已安装 node 及 yarn
- clone 本项目到本地
- 执行 `yarn` 安装依赖

最后将上面代码块中的 `https://screeps-cn.github.io/memory-analyzer/main.html` 修改为 `http:localhost:8001/main.html` 再放到游戏控制台中即可。
