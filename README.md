# theme-next-live2d

本项目 Fork 自 [Live2D 看板娘插件](https://github.com/fghrsh/live2d_demo)，主要为了简化看板娘在 NexT 主题中的使用。

### 特性

- 基于 API 加载模型，支持 定制 提示语
- 增加 参数设置 一键定制看板娘，易用性++
- 增加 看板娘样式设置，可直接设置宽高度等
- 支持多种一言接口，基于 JQuery UI 实现拖拽

## 使用

### Step 1 → Go to NexT dir

Change dir to NexT directory. There must be layout, source, languages and other directories:
```bash
$ cd themes/next
$ ls
bower.json  _config.yml  docs  gulpfile.coffee  languages  layout  LICENSE.md  package.json  README.md  scripts  source  test
```

### Step 2 → Get module
Install module to source/lib directory:
```bash
$ git clone https://github.com/edsion1107/theme-next-live2d source/lib/live2d
```

### Step 3 → Set it up
Enable module in NexT _config.yml file:
```yaml
live2d:
  enable: true
```
Full configuration : https://github.com/edsion1107/hexo-theme-next/blob/1eb0223eea037bb2d0e10a749a4758ad2a24b0a5/_config.yml#L596

### Step 4 → 修改主题
因为并非 NexT 官方插件，在合入之前只能通过修改主题来解决了，具体参考：
```
https://github.com/edsion1107/hexo-theme-next/commit/0e6b8d61049a795038506b7fd482a7ae5618ecdf
https://github.com/edsion1107/hexo-theme-next/commit/1eb0223eea037bb2d0e10a749a4758ad2a24b0a5
```
主要是修改：
- 创建`layout/_third-party/live2d.swig`，引入依赖的js，并根据配置对看板娘进行初始化
- 在`layout/_partials/head/head.swig`中引入所需css
- 在`layout/_layout.swig`的`body`中添加看板娘的html
- 在`layout/_layout.swig`中引入`live2d.swig`

> 相比原项目的`autoload.js`方式，这样速度会略快一点。

## 版权声明

> ( ˃ ˄ ˂̥̥ ) 都看到这了，点个 Star 吧 ~

[Flat UI Free][1]
[live2d_src / ©journey-ad / GPL v2.0][2]
[waifu-tips.js / ©journey-ad / CC BY-NC-SA 4.0][3]

Open sourced under the GPL v2.0 license.


  [1]: https://designmodo.com/flat-free/ "Flat UI Free"
  [2]: https://github.com/journey-ad/live2d_src "基于 #fea64e4 的修改版"
  [3]: https://imjad.cn/ "猫与向日葵"
