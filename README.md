# draw-dance 🎨🎵

在画布上随手画几条线 → 麦克风听任何声音(音乐、喊叫、环境声)→ 线条跟着律动 → 录 30 秒视频下载。

> **在线试用**: https://transcendent-salamander-0eddfa.netlify.app/
>
> iPhone / iPad 用户可在 Safari 打开后,点分享 → "添加到主屏幕",像 App 一样使用(全屏、自定义图标、已配置 PWA)。

## 特点

- 单文件 HTML,纯前端,无后端,无依赖
- 声源完全由用户提供:手机外放音乐、对着麦克风喊、环境声都行
- 不内置任何音乐文件
- 移动端友好,iPad Safari 测试通过
- 已支持 PWA(可添加到主屏幕)

## 本地运行

因为 `getUserMedia`(麦克风权限)需要安全上下文,直接双击打开 `index.html` 不行,必须用本地服务器:

```bash
cd draw-dance
python3 -m http.server 8080
```

然后浏览器打开 <http://localhost:8080>。

## 技术栈

- 原生 Canvas 2D(绘图)
- Web Audio API(`AnalyserNode` + FFT 做音频分析)
- Pointer Events API(同时支持手指、Apple Pencil、鼠标)
- MediaRecorder API(录视频)

## 文件结构

```
.
├── index.html              # 主程序,所有 CSS/JS 内嵌
├── site.webmanifest        # PWA manifest
├── apple-touch-icon.png    # iOS 主屏图标
├── android-chrome-*.png    # Android / PWA 图标
├── favicon.ico, *.png      # 浏览器标签页图标
└── README.md
```

## License

[MIT](./LICENSE)
