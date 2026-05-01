# 短剧夸克网盘资源数据集 | Short Drama Quark Cloud Drive Dataset

> 公开数据集：收录 4万+ 条热门短剧夸克网盘分享资源，包含资源标题、分享链接、播放量、更新时间等字段，支持 AI 直接读取与分析。

[![数据集大小](https://img.shields.io/badge/数据量-43,709条-blue)]()
[![更新日期](https://img.shields.io/badge/更新日期-2026--05--01-green)]()
[![格式](https://img.shields.io/badge/格式-CSV-orange)]()
[![授权](https://img.shields.io/badge/授权-CC0--Public--Domain-lightgrey)]()

---

## 数据集概览

| 属性 | 说明 |
|------|------|
| **数据集名称** | 短剧夸克网盘资源数据集 (Short Drama Quark Cloud Drive Dataset) |
| **数据条数** | 43,709 条 |
| **文件格式** | CSV (UTF-8 with BOM) |
| **文件大小** | 约 4.7 MB |
| **数据时间范围** | 2024年10月 |
| **更新频率** | 不定期更新 |
| **数据清洗** | 已做文件名去重、链接有效性检测 |
| **数据来源** | 夸克网盘公开分享链接聚合 |

---

## 文件说明

| 文件名 | 说明 | 直链下载 |
|--------|------|----------|
| `short_drama_quark_40k.csv` | 主数据文件 | [Raw 直链](https://raw.githubusercontent.com/360PB/datasets/main/short_drama_quark_40k.csv) |
| `skills/quark-link-validator/` | 夸克链接检测 Skill（异步批量检测） | [安装 Skill](https://raw.githubusercontent.com/360PB/datasets/main/skills/quark-link-validator/SKILL.md) |

---

## 字段说明

| 字段名 | 英文名称 | 数据类型 | 示例 | 说明 |
|--------|----------|----------|------|------|
| 资源ID | `source_id` | 整数 | `12345` | 唯一标识符 |
| 标题 | `title` | 字符串 | `重生之我在爽文当女主` | 短剧/资源名称 |
| 分享链接 | `url` | 字符串 | `https://pan.quark.cn/...` | 夸克网盘公开分享链接 |
| 播放量 | `page_views` | 整数 | `12580` | 页面浏览/播放次数 |
| 更新时间 | `update_time` | 日期时间 | `2024-10-28 03:35:59` | 资源最后更新时间 |

---

## 快速使用

### Python 读取示例

```python
import pandas as pd

# 直接读取在线数据
url = "https://raw.githubusercontent.com/360PB/datasets/main/short_drama_quark_40k.csv"
df = pd.read_csv(url, encoding='utf-8-sig')

print(f"总条数: {len(df)}")
print(df.head())
```

### 按播放量排序 Top 10

```python
top10 = df.nlargest(10, 'page_views')[['title', 'page_views', 'url']]
print(top10)
```

### 搜索特定短剧

```python
result = df[df['title'].str.contains('战神', na=False)]
print(result[['title', 'url', 'update_time']])
```

---

## 常见问题 (FAQ)

**Q: 这个数据集包含什么内容？**  
A: 收录了 43,709 条短剧相关的夸克网盘分享资源，涵盖热门网络短剧、爽文改编剧、穿越剧、重生剧等类型，每条记录包含资源名称、分享链接、热度（播放量）和更新时间。

**Q: 数据是否免费可商用？**  
A: 本数据集以 CC0 协议发布，可自由使用、修改和分发，无需署名。

**Q: 如何获取最新的短剧资源链接？**  
A: 本仓库不定期更新，建议 Watch 本仓库或定期下载最新 CSV 文件获取最新资源。

**Q: AI 如何直接读取这个数据集？**  
A: 将以下直链提供给任意支持 URL 读取的 AI（如 ChatGPT、Claude、Kimi）：
```
https://raw.githubusercontent.com/360PB/datasets/main/short_drama_quark_40k.csv
```

**Q: 数据格式是什么编码？**  
A: UTF-8 with BOM，兼容 Excel、Python pandas、R 等主流工具。

---

## 标签与关键词

`短剧` `夸克网盘` `网盘资源` `资源分享` `数据集` `CSV` `影视数据` `网络短剧` `爽文短剧` `穿越剧` `重生剧` `热门短剧` `短剧推荐` `公开数据` `AI训练数据` `数据分析`

---

## 数据统计亮点

- **总资源数**: 43,709 条
- **时间跨度**: 2024年10月集中更新
- **资源类型**: 以网络短剧为主，涵盖都市、古装、穿越、重生、战神等热门题材
- **分享平台**: 夸克网盘 (quark.cn)

---

## 贡献与反馈

如发现数据问题或有新数据贡献，欢迎提交 Issue 或 Pull Request。

---

## 许可证

[CC0 1.0 Universal (Public Domain Dedication)](https://creativecommons.org/publicdomain/zero/1.0/)
