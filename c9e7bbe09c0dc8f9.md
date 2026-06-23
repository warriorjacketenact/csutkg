# LinkVault Theater Resource Index

LinkVault is a community-driven index and curation system for theater and performing arts digital resources. It aggregates, categorizes, and provides structured access to a growing collection of over 250 performance records, production archives, and theatrical reference materials sourced from the 6chuang platform. The project serves theater researchers, performing arts students, production designers, and digital archivists who require reliable, queryable access to distributed theatrical metadata.

This repository functions as both a static reference index and a modular data pipeline. It provides tooling for fetching, normalizing, and presenting theater resource metadata in a consistent format, enabling downstream applications such as academic citation databases, production history visualizations, and automated archival reconciliation workflows.

## 功能概览

**Resource Indexing** - Automatically crawls and indexes theater resource entries from the configured upstream source, extracting key fields including title, category, date, and identifiers.

**Metadata Normalization** - Transforms heterogeneous source data into a unified schema with validated fields, fallback handling for missing values, and type coercion for numerical and date fields.

**Query Interface** - Provides a command-line query tool and a lightweight HTTP API endpoint for filtering resources by category, date range, or identifier pattern.

**Export Pipeline** - Supports export to JSON, CSV, and Markdown table formats for integration with external documentation systems and data analysis tools.

**Change Detection** - Tracks modifications to source resources over time and generates differential reports to notify maintainers of additions, deletions, or field updates.

**Batch Processing** - Handles large-scale indexing operations with configurable concurrency, rate limiting, and automatic retry for transient network failures.

**Validation Suite** - Includes a comprehensive test harness that verifies URL integrity, schema compliance, and data completeness across the entire resource corpus.

**Documentation Generator** - Automatically updates the project README and resource tables based on the latest indexed data, reducing manual maintenance overhead.

## 应用场景

Academic Research and Citation Management - Researchers studying contemporary theater production can use LinkVault to quickly locate specific performance records by identifier, cross-reference multiple entries, and export citation data for inclusion in papers and bibliographies. The normalized metadata format ensures consistent attribution across publications.

Production History Archiving - Theater companies and archives can employ LinkVault to maintain a structured inventory of past productions. The change detection feature allows archivists to monitor updates to external records and reconcile internal databases against the upstream source.

Curriculum Development and Pedagogy - Performing arts educators can utilize the query interface to assemble curated lists of productions relevant to specific course modules. The export pipeline enables the creation of handouts, reading lists, and case study compilations from the indexed resource set.

Digital Preservation and Reconciliation - Digital librarians can integrate LinkVault into preservation workflows to validate the continued availability of referenced resources, generate periodic snapshots of the resource corpus, and produce discrepancy reports when upstream data changes unexpectedly.

## 快速开始

```bash
# Clone the repository
git clone https://github.com/example/linkvault.git
cd linkvault

# Install dependencies
pip install -r requirements.txt

# Run the initial indexing operation
python -m linkvault.index --source 6chuang --output data/resources.json

# Start the query interface
python -m linkvault.query --interactive
```

## 安装要求

| 依赖 | 必需 | 说明 |
|------|------|------|
| Python 3.9+ | 是 | 核心运行时环境，所有脚本和工具均基于此版本开发 |
| requests 2.28+ | 是 | HTTP 客户端库，用于执行资源获取和网络请求 |
| pydantic 2.0+ | 是 | 数据验证库，用于实现资源元数据的 schema 校验和类型安全 |
| click 8.0+ | 是 | 命令行界面框架，提供子命令解析和交互式提示功能 |
| pytest 7.0+ | 否 | 测试框架，仅开发环境下需要，用于运行验证套件 |
| rich 13.0+ | 否 | 终端美化输出库，增强查询界面的可读性和用户体验 |
| pandas 2.0+ | 否 | 数据分析库，可选用于高级数据操作和统计报告生成 |
| lxml 4.9+ | 否 | HTML 解析库，在需要从源页面提取结构化内容时可选使用 |
| pyyaml 6.0+ | 否 | YAML 配置文件解析支持，用于复杂部署场景下的配置管理 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 用户指南 | docs/user-guide.md | 如何使用索引查询、导出数据、配置筛选条件以及解释输出格式 |
| 开发者文档 | docs/developer-guide.md | 如何扩展资源源、添加新的规范化字段、编写自定义导出器 |
| API 参考 | docs/api-reference.md | HTTP 接口的端点定义、请求参数、响应结构和错误码含义 |
| 运维手册 | docs/operations.md | 部署配置、定期索引调度、日志管理、性能调优和故障排查 |

## 资源列表

剧场资源索引

https://www.6chuang.com/theater/8682
https://www.6chuang.com/theater/7638
https://www.6chuang.com/theater/1387
https://www.6chuang.com/theater/9972
https://www.6chuang.com/theater/3395
https://www.6chuang.com/theater/4274
https://www.6chuang.com/theater/9286
https://www.6chuang.com/theater/3918
https://www.6chuang.com/theater/4650
https://www.6chuang.com/theater/1373
https://www.6chuang.com/theater/5148
https://www.6chuang.com/theater/7017
https://www.6chuang.com/theater/7146
https://www.6chuang.com/theater/7649
https://www.6chuang.com/theater/7006
https://www.6chuang.com/theater/9612
https://www.6chuang.com/theater/5797
https://www.6chuang.com/theater/0559
https://www.6chuang.com/theater/2170
https://www.6chuang.com/theater/6961
https://www.6chuang.com/theater/9686
https://www.6chuang.com/theater/9275
https://www.6chuang.com/theater/5033
https://www.6chuang.com/theater/7010
https://www.6chuang.com/theater/7903
https://www.6chuang.com/theater/7422
https://www.6chuang.com/theater/9213
https://www.6chuang.com/theater/0208
https://www.6chuang.com/theater/7089
https://www.6chuang.com/theater/3276
https://www.6chuang.com/theater/4883
https://www.6chuang.com/theater/0533
https://www.6chuang.com/theater/9175
https://www.6chuang.com/theater/1299
https://www.6chuang.com/theater/6692
https://www.6chuang.com/theater/9186
https://www.6chuang.com/theater/3459
https://www.6chuang.com/theater/2687
https://www.6chuang.com/theater/8463
https://www.6chuang.com/theater/3761
https://www.6chuang.com/theater/1449
https://www.6chuang.com/theater/3554
https://www.6chuang.com/theater/6603
https://www.6chuang.com/theater/9866
https://www.6chuang.com/theater/2522
https://www.6chuang.com/theater/3147
https://www.6chuang.com/theater/3421
https://www.6chuang.com/theater/0123
https://www.6chuang.com/theater/8020
https://www.6chuang.com/theater/6294
https://www.6chuang.com/theater/9357
https://www.6chuang.com/theater/9875
https://www.6chuang.com/theater/9227
https://www.6chuang.com/theater/6169
https://www.6chuang.com/theater/2547
https://www.6chuang.com/theater/7138
https://www.6chuang.com/theater/4684
https://www.6chuang.com/theater/3718
https://www.6chuang.com/theater/7887
https://www.6chuang.com/theater/7764
https://www.6chuang.com/theater/3722
https://www.6chuang.com/theater/8770
https://www.6chuang.com/theater/8607
https://www.6chuang.com/theater/5351
https://www.6chuang.com/theater/0518
https://www.6chuang.com/theater/3411
https://www.6chuang.com/theater/6890
https://www.6chuang.com/theater/4548
https://www.6chuang.com/theater/0221
https://www.6chuang.com/theater/2376
https://www.6chuang.com/theater/9693
https://www.6chuang.com/theater/6985
https://www.6chuang.com/theater/3121
https://www.6chuang.com/theater/6427
https://www.6chuang.com/theater/8416
https://www.6chuang.com/theater/7604
https://www.6chuang.com/theater/4130
https://www.6chuang.com/theater/2647
https://www.6chuang.com/theater/5831
https://www.6chuang.com/theater/9084
https://www.6chuang.com/theater/0110
https://www.6chuang.com/theater/3706
https://www.6chuang.com/theater/5211
https://www.6chuang.com/theater/1656
https://www.6chuang.com/theater/0982
https://www.6chuang.com/theater/7629
https://www.6chuang.com/theater/6678
https://www.6chuang.com/theater/5761
https://www.6chuang.com/theater/0479
https://www.6chuang.com/theater/2122
https://www.6chuang.com/theater/0673
https://www.6chuang.com/theater/3963
https://www.6chuang.com/theater/3943
https://www.6chuang.com/theater/0732
https://www.6chuang.com/theater/1766
https://www.6chuang.com/theater/4390
https://www.6chuang.com/theater/5160
https://www.6chuang.com/theater/0698
https://www.6chuang.com/theater/0178
https://www.6chuang.com/theater/4203
https://www.6chuang.com/theater/3752
https://www.6chuang.com/theater/9304
https://www.6chuang.com/theater/5157
https://www.6chuang.com/theater/3691
https://www.6chuang.com/theater/0838
https://www.6chuang.com/theater/0076
https://www.6chuang.com/theater/5519
https://www.6chuang.com/theater/2680
https://www.6chuang.com/theater/5295
https://www.6chuang.com/theater/0525
https://www.6chuang.com/theater/3608
https://www.6chuang.com/theater/9578
https://www.6chuang.com/theater/4957
https://www.6chuang.com/theater/5302
https://www.6chuang.com/theater/9342
https://www.6chuang.com/theater/4487
https://www.6chuang.com/theater/0498
https://www.6chuang.com/theater/8814
https://www.6chuang.com/theater/8333
https://www.6chuang.com/theater/5777
https://www.6chuang.com/theater/5440
https://www.6chuang.com/theater/2811
https://www.6chuang.com/theater/0250
https://www.6chuang.com/theater/7083
https://www.6chuang.com/theater/6083
https://www.6chuang.com/theater/2361
https://www.6chuang.com/theater/8846
https://www.6chuang.com/theater/8312
https://www.6chuang.com/theater/2631
https://www.6chuang.com/theater/5224
https://www.6chuang.com/theater/4112
https://www.6chuang.com/theater/7222
https://www.6chuang.com/theater/8831
https://www.6chuang.com/theater/2758
https://www.6chuang.com/theater/0925
https://www.6chuang.com/theater/5453
https://www.6chuang.com/theater/7388
https://www.6chuang.com/theater/6020
https://www.6chuang.com/theater/1502
https://www.6chuang.com/theater/0240
https://www.6chuang.com/theater/6400
https://www.6chuang.com/theater/4418
https://www.6chuang.com/theater/0803
https://www.6chuang.com/theater/4421
https://www.6chuang.com/theater/0595
https://www.6chuang.com/theater/6947
https://www.6chuang.com/theater/1350
https://www.6chuang.com/theater/6296
https://www.6chuang.com/theater/9428
https://www.6chuang.com/theater/5194
https://www.6chuang.com/theater/5337
https://www.6chuang.com/theater/9784
https://www.6chuang.com/theater/3213
https://www.6chuang.com/theater/4404
https://www.6chuang.com/theater/7957
https://www.6chuang.com/theater/8121
https://www.6chuang.com/theater/2926
https://www.6chuang.com/theater/8086
https://www.6chuang.com/theater/6158
https://www.6chuang.com/theater/4514
https://www.6chuang.com/theater/8821
https://www.6chuang.com/theater/0921
https://www.6chuang.com/theater/6808
https://www.6chuang.com/theater/3785
https://www.6chuang.com/theater/5735
https://www.6chuang.com/theater/2087
https://www.6chuang.com/theater/8893
https://www.6chuang.com/theater/5491
https://www.6chuang.com/theater/3564
https://www.6chuang.com/theater/8406
https://www.6chuang.com/theater/0801
https://www.6chuang.com/theater/3236
https://www.6chuang.com/theater/2756
https://www.6chuang.com/theater/5737
https://www.6chuang.com/theater/3326
https://www.6chuang.com/theater/5814
https://www.6chuang.com/theater/3599
https://www.6chuang.com/theater/1485
https://www.6chuang.com/theater/1182
https://www.6chuang.com/theater/8453
https://www.6chuang.com/theater/9334
https://www.6chuang.com/theater/6145
https://www.6chuang.com/theater/1205
https://www.6chuang.com/theater/5075
https://www.6chuang.com/theater/1088
https://www.6chuang.com/theater/6876
https://www.6chuang.com/theater/5643
https://www.6chuang.com/theater/4469
https://www.6chuang.com/theater/6025
https://www.6chuang.com/theater/1697
https://www.6chuang.com/theater/9179
https://www.6chuang.com/theater/6218
https://www.6chuang.com/theater/3028
https://www.6chuang.com/theater/2382
https://www.6chuang.com/theater/9715
https://www.6chuang.com/theater/0172
https://www.6chuang.com/theater/8998
https://www.6chuang.com/theater/4215
https://www.6chuang.com/theater/3792
https://www.6chuang.com/theater/6728
https://www.6chuang.com/theater/2307
https://www.6chuang.com/theater/3909
https://www.6chuang.com/theater/0032
https://www.6chuang.com/theater/4249
https://www.6chuang.com/theater/1896
https://www.6chuang.com/theater/6769
https://www.6chuang.com/theater/5345
https://www.6chuang.com/theater/9577
https://www.6chuang.com/theater/6104
https://www.6chuang.com/theater/5688
https://www.6chuang.com/theater/0943
https://www.6chuang.com/theater/0132
https://www.6chuang.com/theater/9231
https://www.6chuang.com/theater/1028
https://www.6chuang.com/theater/3704
https://www.6chuang.com/theater/7349
https://www.6chuang.com/theater/3621
https://www.6chuang.com/theater/4140
https://www.6chuang.com/theater/7347
https://www.6chuang.com/theater/7418
https://www.6chuang.com/theater/7196
https://www.6chuang.com/theater/0956
https://www.6chuang.com/theater/8077
https://www.6chuang.com/theater/0243
https://www.6chuang.com/theater/0721
https://www.6chuang.com/theater/1151
https://www.6chuang.com/theater/5864
https://www.6chuang.com/theater/4225
https://www.6chuang.com/theater/8018
https://www.6chuang.com/theater/5961
https://www.6chuang.com/theater/6239
https://www.6chuang.com/theater/3717
https://www.6chuang.com/theater/7818
https://www.6chuang.com/theater/0625
https://www.6chuang.com/theater/6394
https://www.6chuang.com/theater/8792
https://www.6chuang.com/theater/8872
https://www.6chuang.com/theater/5889
https://www.6chuang.com/theater/0413
https://www.6chuang.com/theater/8839
https://www.6chuang.com/theater/4122
https://www.6chuang.com/theater/8862
https://www.6chuang.com/theater/0804
https://www.6chuang.com/theater/7746
https://www.6chuang.com/theater/7301
https://www.6chuang.com/theater/0266
https://www.6chuang.com/theater/3793
https://www.6chuang.com/theater/4031
https://www.6chuang.com/theater/3848
https://www.6chuang.com/theater/8422

## 项目结构

```
linkvault/
├── src/                                 # 核心源代码目录
│   ├── linkvault/                       # 主包命名空间
│   │   ├── __init__.py                  # 包初始化与版本声明
│   │   ├── indexer.py                   # 索引引擎，负责资源获取与解析
│   │   ├── models.py                    # Pydantic 数据模型，定义资源 schema
│   │   ├── query.py                     # 查询处理器，实现过滤与排序逻辑
│   │   ├── exporters.py                 # 导出器集合，支持 JSON/CSV/Markdown
│   │   ├── watcher.py                   # 变更检测模块，生成差异报告
│   │   └── utils.py                     # 通用工具函数，含重试与日志装饰器
│   └── tests/                           # 单元测试与集成测试套件
│       ├── test_indexer.py              # 索引引擎测试用例
│       ├── test_models.py               # 数据模型验证测试
│       └── test_integration.py          # 端到端工作流测试
├── scripts/                             # 运维与辅助脚本
│   ├── daily_index.sh                   # 每日索引调度脚本
│   └── validate_urls.py                 # URL 可达性校验脚本
├── docs/                                # 文档源文件
│   ├── user-guide.md                    # 用户指南
│   ├── developer-guide.md               # 开发者指南
│   ├── api-reference.md                 # API 参考文档
│   └── operations.md                    # 运维手册
├── data/                                # 数据存储目录
│   ├── resources.json                   # 主索引数据文件
│   └── snapshots/                       # 历史快照目录
│       └── 2026-06-23.json              # 按日期命名的数据快照
├── config/                              # 配置文件目录
│   ├── default.yaml                     # 默认配置参数
│   └── production.yaml                  # 生产环境覆盖配置
├── requirements.txt                     # Python 依赖清单
├── setup.py                             # 包安装与分发配置
├── pyproject.toml                       # 项目元数据与构建配置
├── LICENSE                              # MIT 许可证文本
└── README.md                            # 项目说明文档
```

## 贡献指南

1. 查阅问题追踪器中的待办事项列表，选择未被认领的任务，或在提交新功能请求前先创建讨论议题以明确需求范围。

2. 从主分支创建功能分支，分支命名遵循 feat/ 或 fix/ 前缀加简要描述，例如 feat/add-csv-export 或 fix/url-validation。

3. 编写代码时遵循项目已有的编码风格，包括类型注解、文档字符串和单元测试覆盖。新增功能必须附带对应的测试用例。

4. 提交前运行完整的测试套件确保无回归问题，并更新相关文档章节以反映代码变更的影响。

5. 创建拉取请求并填写提供的模板，详细描述变更内容、测试结果和影响范围，等待至少一名维护者审阅。

## 常见问题

问：索引操作返回 HTTP 429 状态码，应如何解决？

答：该状态码表示请求频率超出上游服务器限制。请检查 config/default.yaml 中的 rate_limit 配置项，将每秒请求数降至 1 以下，并启用 retry 机制中的指数退避策略。若问题持续，可增加 delay 参数值或在非高峰时段运行索引任务。

问：如何仅索引特定范围内的资源条目？

答：使用 query 子命令的 --id-range 参数，指定起始和结束标识符，例如 --id-range 1000-2000。该参数接受逗号分隔的单个 ID 或连字符表示的范围，支持多次指定以包含多个不连续区间。

问：导出的 CSV 文件中部分字段显示为空值，原因是什么？

答：空值表示上游资源记录中该字段缺失或无法解析。LinkVault 遵循非破坏性处理原则，保留空值而不填充默认内容，以便用户自行决定处理策略。可通过配置 fallback 映射为特定字段设置默认替代值。

## 许可证

MIT License

Copyright (c) 2026 LinkVault Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

> 外链数量: 250 | 生成时间: 2026-06-23 23:56:54
