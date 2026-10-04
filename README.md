# cachedata

静态数据缓存仓库，存放供其他 farfarfun 项目下载使用的原始数据文件，本身不含代码。

- `farfarfun/fungame/topwar/data/` —— 手游《Top War》相关的配置/文本数据文件，供 [fungame](https://github.com/farfarfun/fungame) 的 `fungame.games.topwar` 模块使用。

## 获取数据

克隆整个仓库，或只拉取需要的文件：

```bash
git clone https://github.com/farfarfun/cachedata.git
# 或只下载单个文件
curl -O https://raw.githubusercontent.com/farfarfun/cachedata/master/farfarfun/fungame/topwar/data/zh_cn_1.3.1821.txt
```

## 最小示例

数据文件是游戏客户端导出的原始 UTF-8 文本，使用自定义分隔符而非 JSON 格式，按文本方式读取即可：

```python
from pathlib import Path

path = Path("farfarfun/fungame/topwar/data/zh_cn_1.3.1821.txt")
content = path.read_text(encoding="utf-8", errors="ignore")
print(content[:200])
```

具体字段含义由使用方（如 `fungame`）按各自的解析逻辑处理，本仓库只负责托管原始文件。

---

## 关于 farfarfun

[farfarfun](https://github.com/farfarfun) 是一个专注于实用工具库的开源组织，
涵盖云存储、数据处理、AI、多媒体与开发工具链等方向。

- 🏠 组织主页：<https://github.com/farfarfun>
- 📧 联系：farfarfun@qq.com

本项目基于 [MIT](LICENSE) 协议开源。
