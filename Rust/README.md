## 一、开发环境

### 安装编译器

安装：

```bash
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

卸载：

```bash
rustup self uninstall
```

检查安装：

```bash
rustc --version
cargo --version
```

### 开发工具

开发工具：VS Code。

插件：

- rust-analyzer
- Even Better TOML：.toml文件支持
- Error Lens：错误提示
- One Dark Pro：主题
- CodeLLDB：Debugger程序

自动格式化配置（Ctrl + Shift + P）：

```json
{
    "editor.unicodeHighlight.nonBasicASCII": false,
    "workbench.colorTheme": "One Dark Pro Darker",
    "editor.fontSize": 18,
    // "editor.fontFamily": "Fira Code, Consolas, 'Courier New', monospace",
    "editor.fontFamily": "Fira Code Light, Consolas, Microsoft YaHei",
    "editor.fontLigatures": true,
    "debug.console.fontSize": 18,
    "debug.console.fontFamily": "Fira Code Light, Consolas, Microsoft YaHei",
    "terminal.integrated.fontFamily": "Fira Code Light, Consolas, Microsoft YaHei",
    "window.zoomLevel": 1.2,
    "remote.SSH.remotePlatform": {
        "45.136.15.240": "linux"
    },
    "[rust]": {
        "editor.defaultFormatter": "rust-lang.rust-analyzer",
        "editor.formatOnSave": true
    },
}
```

### 配置镜像源（天朝专用）

新增配置文件（.cargo/config），放置于用户目录或项目根目录下，以用户目录为例：

```
$HOME/.cargo/config
```

配置内容：

```
[source.crates-io]
registry = "https://github.com/rust-lang/crates.io-index"
# 指定镜像
replace-with = 'tuna' # 如：tuna、sjtu、ustc，或者 rustcc

# 中国科学技术大学
[source.ustc]
registry = "git://mirrors.ustc.edu.cn/crates.io-index"

# 上海交通大学
[source.sjtu]
registry = "https://mirrors.sjtug.sjtu.edu.cn/git/crates.io-index"

# 清华大学
[source.tuna]
registry = "https://mirrors.tuna.tsinghua.edu.cn/git/crates.io-index.git"

# rustcc社区
[source.rustcc]
registry = "https://code.aliyun.com/rustcc/crates.io-index.git"
```




