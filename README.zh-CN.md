# 文件架

[English](README.md)

用 TypeScript 写的 tessoa 插件：一个让文件随手可取的文件架页面。

它是 tessoa 插件 SDK 的一个例子，单独做成了一个项目，好拿来当你自己插件的起点：从它建一个仓库，改，再构建。插件模板在
<https://github.com/Tessoa/tessoa-plugin-template>，里面有其余的例子，以及 TypeScript 和 Rust 各一套空白起点。

## 测试、打包、安装

```
powershell -ExecutionPolicy Bypass -File scripts/setup.ps1 -Lang ts   # Windows
bash scripts/setup.sh --lang ts                                    # macOS、Linux
tessoa-plugin test
tessoa-plugin package
tessoa-plugin install
```

装环境脚本只装缺的东西：Node.js，以及 `tessoa-plugin` 命令行工具。`test` 在真实沙箱里、对着模拟的 tessoa 跑
`tests/scenarios` 下的剧本，不需要装 tessoa。`package` 写出 `dist/com.example.shelf-0.1.0.zip`。`install` 把插件交给本机正在运行的
tessoa，由它请你确认插件要的权限。装进 tessoa 需要授权，测试和打包不需要。

## 改成你自己的插件

1. 先改 `plugin.toml` 里的 `id`。`com.example.shelf` 是这个例子的，tessoa 按 id 区分插件。换成你自己的，比如
   `com.yourname.shelf`，`name` 也一起改掉。
2. 改 `src/` 里的代码和 `tests/scenarios` 里的剧本，再跑一遍 `tessoa-plugin test`。

在这个仓库里打开编程助手，它会从 `AGENTS.md` 开始，再去读 `sdk/` 里的说明书。`tessoa-plugin upgrade` 会把 `sdk/`
换成最新的套件；里面的文件不要改。

## 许可

这个插件的代码按 `LICENSE` 里的 MIT 许可发布。`sdk/` 下的文件是 tessoa 插件 SDK，不在这份许可之内，
另有自己的许可，见 `sdk/LICENSE.zh-CN.md`。
