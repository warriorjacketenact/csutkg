# LinkVault Resource Aggregator

LinkVault 是一个面向开发者、技术研究人员与内容创造成员的轻量级外链资源汇总与导航系统。该项目定位于将分散于网络各处的优质视频资源链接、技术文档入口与数据资产索引进行集中化、结构化存储，并通过简洁的 Web 界面或 API 形式提供快速检索与访问能力。

本项目并非一个传统的内容管理系统（CMS），而是一个“链接的链接”——即元聚合层。它主要面向需要批量维护大量外部资源 URL 的中小型团队、开源文档维护者以及个人知识管理（PKM）重度用户。LinkVault 不对所指向的资源内容进行任何本地存储或二次分发，仅作为纯索引层存在，严格遵循外部资源的原始访问协议与地址结构。

## 功能概览

- **批量链接入库与自动规范化**：支持一次性导入大批量 URL 列表，系统自动识别协议类型（http/https）、域名结构及路径层级，并生成唯一内部标识符，避免重复条目。

- **多维度标签分类与全文检索**：每个资源条目可绑定多个自定义标签（如“教程”、“演示”、“数据集”），并基于 SQLite 或 PostgreSQL 的全文搜索（FTS）引擎提供毫秒级的关键词匹配响应。

- **结构化目录树生成**：根据 URL 路径的层级关系（如 /voddetail/xxx）自动构建虚拟目录树，方便用户按业务模块或资源类型进行层级式浏览。

- **资源可用性健康检查**：内置定时任务（通过 cron 或 systemd timer）对已收录的 URL 执行周期性 HEAD 请求探测，标记失效或重定向链接，并生成可视化健康报告。

- **导入/导出兼容性**：支持标准 CSV、JSON Lines 及 Markdown 列表格式的批量导入导出，与主流笔记软件（Obsidian、Notion）及电子表格工具无缝对接。

- **访问统计与热度排序**：记录每个资源链接的访问点击次数与最后访问时间，支持按“最热”、“最新”、“即将失效”三种维度排序输出。

- **权限分级与只读镜像**：提供管理员与访客两种角色视图，访客仅能浏览已发布的公共资源列表，管理员可执行增删改操作；同时支持生成静态只读镜像站，便于内网分发。

- **URL 原样透传策略**：严格遵守“资源引用不修改”原则，所有存储的 URL 在输出、导出或跳转时均保持用户提交时的原始字符串形态，不自动补全协议头、不添加尾部斜杠、不转换大小写。

## 应用场景

**开源项目文档站外链管理**
开源项目的 README 或 Wiki 中往往需要引用大量外部参考链接（如依赖库主页、API 规范文档、视频讲解地址）。LinkVault 可作为这些外链的后台存储引擎，通过 API 动态渲染至项目站点，避免硬编码链接散落在各处难以维护。

**技术培训课程资源索引**
培训机构或企业内训部门在交付视频课程时，每期课程会附带数十个课外阅读或实战演示链接。培训管理员可将全部链接录入 LinkVault，并按课程编号（如批次 86/1241）打标签，学员通过统一入口即可获取当期的全部扩展资源。

**个人知识库外链去重与备份**
使用 Obsidian、Logseq 等双链笔记的用户常遇到同一 URL 被多次摘录的问题。LinkVault 提供中心化的外链仓库，笔记中仅需引用仓库生成的短 ID，即可实现“一处存储，多处引用”，同时支持定期导出完整链接列表作为数据保险。

**数据资产合规审计**
法务或数据治理团队需要定期审查企业对外引用的所有第三方资源是否仍处于有效状态、是否存在内容变更或合规风险。LinkVault 的健康检查与历史变更日志功能可为此类审计提供原始数据支撑。

## 快速开始

以下指令适用于 Linux/macOS 环境，Windows 用户建议通过 WSL2 或 Git Bash 执行。

```bash
# 克隆项目仓库至本地
git clone https://github.com/linkvault/linkvault-core.git
cd linkvault-core

# 安装 Python 依赖（推荐使用虚拟环境）
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# 初始化 SQLite 数据库并导入示例资源列表
python manage.py initdb --sample
python manage.py import --file samples/links_batch_86.json

# 启动开发服务器（默认监听 127.0.0.1:5000）
python manage.py runserver
```

访问 http://127.0.0.1:5000 即可看到当前批次资源的目录导航页。生产环境部署请参考 `deploy/` 目录下的 Docker 与 Nginx 配置范例。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 或更高 | 核心运行环境，推荐使用 3.11 以获取性能优化 |
| SQLite | 3.35 以上（或 PostgreSQL 13+） | 默认内置 SQLite，若启用高级检索建议使用 PostgreSQL |
| pip | 22.0 以上 | Python 包管理器，用于安装项目依赖项 |
| Git | 2.30 以上 | 版本控制工具，用于克隆仓库及后续更新 |
| make | 任意兼容 POSIX 版本 | 用于执行自动化脚本（可选，但强烈推荐） |
| curl / wget | 任意版本 | 用于外部健康检查模块的 HTTP 探测后端 |
| virtualenv | 任意版本 | Python 虚拟环境隔离工具（推荐，非强制） |

## 文档导航

| 层面 | 目录路径 | 回答的问题 |
|---|---|---|
| 用户手册 | `/docs/user/guide.md` | 如何录入新链接、如何分类、如何生成分享页面 |
| 运维手册 | `/docs/ops/deployment.md` | 生产环境容器化部署、数据库迁移、定时任务配置 |
| API 参考 | `/docs/api/endpoints.md` | 全部 RESTful 接口规范、请求/响应示例、认证方式 |
| 架构设计 | `/docs/design/architecture.md` | 系统模块划分、数据流走向、扩展点设计说明 |
| 外部资源 | `/docs/external/resource-mapping.md` | 本批次原始 URL 与内部 ID 的对照表及溯源说明 |
| 贡献指南 | `/CONTRIBUTING.md` | 面向外部开发者的代码提交、测试、文档规范总览 |

## 资源列表

### 核心资源库（第 86 批 / 共 1241 批，本批收录 250 条）

以下列表为 LinkVault 第 86 批次收录的全部原始资源链接。所有条目均保持用户提交时的原始形态，不添加任何前缀或后缀修饰。

https://www.lt-test28.net/voddetail/46405323
https://www.lt-test28.net/voddetail/221776
https://www.lt-test28.net/voddetail/0063
https://www.lt-test28.net/voddetail/220842
https://www.lt-test28.net/voddetail/13114
https://www.lt-test28.net/voddetail/761195
https://www.lt-test28.net/voddetail/5685
https://www.lt-test28.net/voddetail/8676530
https://www.lt-test28.net/voddetail/60887
https://www.lt-test28.net/voddetail/19573
https://www.lt-test28.net/voddetail/790770
https://www.lt-test28.net/voddetail/98338677
https://www.lt-test28.net/voddetail/5637
https://www.lt-test28.net/voddetail/47364579
https://www.lt-test28.net/voddetail/8851562
https://www.lt-test28.net/voddetail/0036
https://www.lt-test28.net/voddetail/212180
https://www.lt-test28.net/voddetail/3808050
https://www.lt-test28.net/voddetail/3397589
https://www.lt-test28.net/voddetail/209070
https://www.lt-test28.net/voddetail/69591
https://www.lt-test28.net/voddetail/67308
https://www.lt-test28.net/voddetail/62322
https://www.lt-test28.net/voddetail/5669
https://www.lt-test28.net/voddetail/5440
https://www.lt-test28.net/voddetail/90323785
https://www.lt-test28.net/voddetail/96365130
https://www.lt-test28.net/voddetail/0030
https://www.lt-test28.net/voddetail/8248128
https://www.lt-test28.net/voddetail/753067
https://www.lt-test28.net/voddetail/5082
https://www.lt-test28.net/voddetail/762123
https://www.lt-test28.net/voddetail/5534
https://www.lt-test28.net/voddetail/8461493
https://www.lt-test28.net/voddetail/0573
https://www.lt-test28.net/voddetail/63279
https://www.lt-test28.net/voddetail/95394408
https://www.lt-test28.net/voddetail/715237
https://www.lt-test28.net/voddetail/99354026
https://www.lt-test28.net/voddetail/753727
https://www.lt-test28.net/voddetail/3839775
https://www.lt-test28.net/voddetail/3116940
https://www.lt-test28.net/voddetail/42397613
https://www.lt-test28.net/voddetail/233475
https://www.lt-test28.net/voddetail/43207039
https://www.lt-test28.net/voddetail/8351214
https://www.lt-test28.net/voddetail/5754
https://www.lt-test28.net/voddetail/16985
https://www.lt-test28.net/voddetail/8195208
https://www.lt-test28.net/voddetail/298598
https://www.lt-test28.net/voddetail/271800
https://www.lt-test28.net/voddetail/40049230
https://www.lt-test28.net/voddetail/13248
https://www.lt-test28.net/voddetail/3637422
https://www.lt-test28.net/voddetail/13588
https://www.lt-test28.net/voddetail/0631
https://www.lt-test28.net/voddetail/61932
https://www.lt-test28.net/voddetail/3429757
https://www.lt-test28.net/voddetail/717599
https://www.lt-test28.net/voddetail/97969829
https://www.lt-test28.net/voddetail/743412
https://www.lt-test28.net/voddetail/66263
https://www.lt-test28.net/voddetail/8345015
https://www.lt-test28.net/voddetail/0628
https://www.lt-test28.net/voddetail/41343333
https://www.lt-test28.net/voddetail/3572681
https://www.lt-test28.net/voddetail/3050195
https://www.lt-test28.net/voddetail/47659401
https://www.lt-test28.net/voddetail/64229
https://www.lt-test28.net/voddetail/68842
https://www.lt-test28.net/voddetail/97226784
https://www.lt-test28.net/voddetail/15755
https://www.lt-test28.net/voddetail/756787
https://www.lt-test28.net/voddetail/247679
https://www.lt-test28.net/voddetail/8767620
https://www.lt-test28.net/voddetail/5223
https://www.lt-test28.net/voddetail/99891247
https://www.lt-test28.net/voddetail/784310
https://www.lt-test28.net/voddetail/18165
https://www.lt-test28.net/voddetail/8347007
https://www.lt-test28.net/voddetail/49422742
https://www.lt-test28.net/voddetail/0012
https://www.lt-test28.net/voddetail/67588
https://www.lt-test28.net/voddetail/753035
https://www.lt-test28.net/voddetail/5702
https://www.lt-test28.net/voddetail/8714103
https://www.lt-test28.net/voddetail/8130722
https://www.lt-test28.net/voddetail/269416
https://www.lt-test28.net/voddetail/8601295
https://www.lt-test28.net/voddetail/10275
https://www.lt-test28.net/voddetail/5319
https://www.lt-test28.net/voddetail/720444
https://www.lt-test28.net/voddetail/704512
https://www.lt-test28.net/voddetail/45929588
https://www.lt-test28.net/voddetail/212354
https://www.lt-test28.net/voddetail/92804630
https://www.lt-test28.net/voddetail/3552188
https://www.lt-test28.net/voddetail/18169
https://www.lt-test28.net/voddetail/99884848
https://www.lt-test28.net/voddetail/241144
https://www.lt-test28.net/voddetail/46309245
https://www.lt-test28.net/voddetail/68502
https://www.lt-test28.net/voddetail/5722
https://www.lt-test28.net/voddetail/17642
https://www.lt-test28.net/voddetail/41446397
https://www.lt-test28.net/voddetail/61254
https://www.lt-test28.net/voddetail/48755309
https://www.lt-test28.net/voddetail/49935894
https://www.lt-test28.net/voddetail/754607
https://www.lt-test28.net/voddetail/96247473
https://www.lt-test28.net/voddetail/11332
https://www.lt-test28.net/voddetail/92500236
https://www.lt-test28.net/voddetail/67160
https://www.lt-test28.net/voddetail/8266904
https://www.lt-test28.net/voddetail/5631
https://www.lt-test28.net/voddetail/3493652
https://www.lt-test28.net/voddetail/97609051
https://www.lt-test28.net/voddetail/0915
https://www.lt-test28.net/voddetail/48470930
https://www.lt-test28.net/voddetail/65141
https://www.lt-test28.net/voddetail/0456
https://www.lt-test28.net/voddetail/751110
https://www.lt-test28.net/voddetail/97757830
https://www.lt-test28.net/voddetail/40922353
https://www.lt-test28.net/voddetail/43397310
https://www.lt-test28.net/voddetail/44434752
https://www.lt-test28.net/voddetail/62434
https://www.lt-test28.net/voddetail/5550
https://www.lt-test28.net/voddetail/11374
https://www.lt-test28.net/voddetail/3516295
https://www.lt-test28.net/voddetail/5186
https://www.lt-test28.net/voddetail/278765
https://www.lt-test28.net/voddetail/8516851
https://www.lt-test28.net/voddetail/0452
https://www.lt-test28.net/voddetail/238270
https://www.lt-test28.net/voddetail/8813895
https://www.lt-test28.net/voddetail/68759
https://www.lt-test28.net/voddetail/12288
https://www.lt-test28.net/voddetail/705699
https://www.lt-test28.net/voddetail/5270
https://www.lt-test28.net/voddetail/797137
https://www.lt-test28.net/voddetail/43545052
https://www.lt-test28.net/voddetail/42739436
https://www.lt-test28.net/voddetail/5126
https://www.lt-test28.net/voddetail/775833
https://www.lt-test28.net/voddetail/99930793
https://www.lt-test28.net/voddetail/710989
https://www.lt-test28.net/voddetail/43322161
https://www.lt-test28.net/voddetail/8181112
https://www.lt-test28.net/voddetail/66616
https://www.lt-test28.net/voddetail/61686
https://www.lt-test28.net/voddetail/797880
https://www.lt-test28.net/voddetail/3085132
https://www.lt-test28.net/voddetail/211540
https://www.lt-test28.net/voddetail/64938
https://www.lt-test28.net/voddetail/68402
https://www.lt-test28.net/voddetail/0578
https://www.lt-test28.net/voddetail/741864
https://www.lt-test28.net/voddetail/14410
https://www.lt-test28.net/voddetail/709607
https://www.lt-test28.net/voddetail/92238450
https://www.lt-test28.net/voddetail/8146789
https://www.lt-test28.net/voddetail/269695
https://www.lt-test28.net/voddetail/743107
https://www.lt-test28.net/voddetail/759649
https://www.lt-test28.net/voddetail/794798
https://www.lt-test28.net/voddetail/762041
https://www.lt-test28.net/voddetail/0995
https://www.lt-test28.net/voddetail/8035575
https://www.lt-test28.net/voddetail/8472944
https://www.lt-test28.net/voddetail/40033303
https://www.lt-test28.net/voddetail/755409
https://www.lt-test28.net/voddetail/90412018
https://www.lt-test28.net/voddetail/49033439
https://www.lt-test28.net/voddetail/8299444
https://www.lt-test28.net/voddetail/46674166
https://www.lt-test28.net/voddetail/0565
https://www.lt-test28.net/voddetail/3382642
https://www.lt-test28.net/voddetail/97770310
https://www.lt-test28.net/voddetail/3637834
https://www.lt-test28.net/voddetail/5644
https://www.lt-test28.net/voddetail/42276061
https://www.lt-test28.net/voddetail/0031
https://www.lt-test28.net/voddetail/11437
https://www.lt-test28.net/voddetail/5664
https://www.lt-test28.net/voddetail/3689964
https://www.lt-test28.net/voddetail/98551907
https://www.lt-test28.net/voddetail/0808
https://www.lt-test28.net/voddetail/49526308
https://www.lt-test28.net/voddetail/0611
https://www.lt-test28.net/voddetail/0369
https://www.lt-test28.net/voddetail/15500
https://www.lt-test28.net/voddetail/3939308
https://www.lt-test28.net/voddetail/299065
https://www.lt-test28.net/voddetail/0748
https://www.lt-test28.net/voddetail/48888844
https://www.lt-test28.net/voddetail/43344467
https://www.lt-test28.net/voddetail/5997
https://www.lt-test28.net/voddetail/3104629
https://www.lt-test28.net/voddetail/19059
https://www.lt-test28.net/voddetail/91466428
https://www.lt-test28.net/voddetail/48513767
https://www.lt-test28.net/voddetail/63512
https://www.lt-test28.net/voddetail/92928300
https://www.lt-test28.net/voddetail/3184833
https://www.lt-test28.net/voddetail/3106115
https://www.lt-test28.net/voddetail/95906782
https://www.lt-test28.net/voddetail/241246
https://www.lt-test28.net/voddetail/48590872
https://www.lt-test28.net/voddetail/8474035
https://www.lt-test28.net/voddetail/0930
https://www.lt-test28.net/voddetail/786963
https://www.lt-test28.net/voddetail/748650
https://www.lt-test28.net/voddetail/228686
https://www.lt-test28.net/voddetail/0486
https://www.lt-test28.net/voddetail/41265284
https://www.lt-test28.net/voddetail/236394
https://www.lt-test28.net/voddetail/3722504
https://www.lt-test28.net/voddetail/91022139
https://www.lt-test28.net/voddetail/5224
https://www.lt-test28.net/voddetail/12844
https://www.lt-test28.net/voddetail/276523
https://www.lt-test28.net/voddetail/238689
https://www.lt-test28.net/voddetail/15396
https://www.lt-test28.net/voddetail/3845094
https://www.lt-test28.net/voddetail/3098995
https://www.lt-test28.net/voddetail/61474
https://www.lt-test28.net/voddetail/68045
https://www.lt-test28.net/voddetail/64920
https://www.lt-test28.net/voddetail/65625
https://www.lt-test28.net/voddetail/15608
https://www.lt-test28.net/voddetail/3231168
https://www.lt-test28.net/voddetail/764864
https://www.lt-test28.net/voddetail/3507897
https://www.lt-test28.net/voddetail/17097
https://www.lt-test28.net/voddetail/98881470
https://www.lt-test28.net/voddetail/8701972
https://www.lt-test28.net/voddetail/61572
https://www.lt-test28.net/voddetail/231998
https://www.lt-test28.net/voddetail/233084
https://www.lt-test28.net/voddetail/17421
https://www.lt-test28.net/voddetail/90889844
https://www.lt-test28.net/voddetail/8184120
https://www.lt-test28.net/voddetail/8210059
https://www.lt-test28.net/voddetail/8884463
https://www.lt-test28.net/voddetail/0500
https://www.lt-test28.net/voddetail/5190
https://www.lt-test28.net/voddetail/782454
https://www.lt-test28.net/voddetail/789756
https://www.lt-test28.net/voddetail/17987

## 项目结构

```
linkvault-core/
├── app/
│   ├── api/                           # RESTful API 路由与视图函数
│   │   ├── routes.py                  # 注册所有蓝图及前缀
│   │   └── v1/                        # API 版本 v1 实现
│   │       ├── resources.py           # 资源 CRUD 端点 (GET/POST/PUT/DELETE)
│   │       └── health.py              # 批量健康检查端点
│   ├── core/                          # 核心业务逻辑层（与框架解耦）
│   │   ├── importer.py                # 批量导入器（支持 CSV/JSON/Markdown）
│   │   ├── exporter.py                # 导出器（生成结构化目录树）
│   │   ├── validator.py               # URL 合规性校验（协议、长度、黑名单）
│   │   └── tag_engine.py              # 标签自动提取与推荐引擎
│   ├── models/                        # 数据模型与 ORM 映射
│   │   ├── resource.py                # 资源实体（含 url_raw, url_hash, status_code）
│   │   ├── batch.py                   # 批次元数据（批次号、导入时间、条目计数）
│   │   └── tag.py                     # 标签与资源的多对多关联表
│   ├── services/                      # 外部服务集成层
│   │   ├── fetcher.py                 # 异步 HTTP 客户端（基于 aiohttp）
│   │   ├── notifier.py                # 失效链接告警（邮件/Webhook 推送到企业微信）
│   │   └── cache.py                   # Redis 缓存预热与过期策略
│   ├── static/                        # 前端静态资源（CSS / JS / 图标）
│   │   ├── css/
│   │   │   └── style.css              # 响应式导航主题（暗色模式适配）
│   │   └── js/
│   │       └── dashboard.js           # 前端交互（排序、筛选、一键复制链接）
│   └── templates/                     # Jinja2 模板（服务端渲染）
│       ├── index.html                 # 资源总览页（分页、搜索框）
│       ├── detail.html                # 单条资源详情（含元数据与访问历史）
│       └── batch.html                 # 批次专属视图（按 86/1241 维度展示）
├── config/                            # 配置文件目录
│   ├── development.py                 # 开发环境配置（DEBUG=True, SQLite 路径）
│   ├── production.py                  # 生产环境配置（PostgreSQL DSN, 日志等级）
│   └── settings.py                    # 基础配置父类（通用常量）
├── data/                              # 数据存储目录（非代码）
│   ├── database/                      # SQLite 数据库文件及迁移脚本
│   ├── imports/                       # 待导入的原始 CSV / JSON 文件暂存区
│   └── exports/                       # 生成的结构化目录树 Markdown 输出
├── scripts/                           # 运维与辅助脚本
│   ├── init_db.py                     # 初始化数据库表结构
│   ├── health_check_cron.py           # 定时健康检查任务（配合 crontab 使用）
│   └── migrate_v1_to_v2.py            # 数据模型升级迁移工具
├── tests/                             # 单元测试与集成测试
│   ├── unit/                          # 细粒度模块测试（pytest 框架）
│   └── integration/                   # API 端到端测试（含测试用数据库）
├── .env.example                       # 环境变量示例（数据库 URL、密钥占位）
├── .gitignore                         # Git 忽略规则（venv, pycache, .env）
├── docker-compose.yml                 # 容器编排（PostgreSQL + Redis + App）
├── Dockerfile                         # 多阶段构建镜像（基于 Alpine Linux）
├── LICENSE                            # MIT 许可证全文
├── Makefile                           # 常用命令封装（install, test, run, clean）
├── README.md                          # 本文件
└── requirements.txt                   # Python 依赖清单（Flask, SQLAlchemy, aiohttp）
```

## 贡献指南

我们欢迎社区贡献者以多种形式参与 LinkVault 项目的改进。请遵循以下步骤确保协作流程顺畅：

1.  **查阅问题跟踪器与项目看板**：访问 GitHub Issues 页面，筛选标签为 `good-first-issue` 或 `help-wanted` 的任务。在开始工作前，请在对应 Issue 下留言说明认领，避免重复劳动。

2.  **复刻仓库并创建功能分支**：将主仓库复刻（Fork）至个人账号下，然后基于 `main` 分支创建新的特性分支（命名规范：`feature/简述改动` 或 `fix/简述修复`）。严禁直接在 `main` 分支上修改。

3.  **编写测试用例并确保通过**：所有新增功能或缺陷修复必须附带对应的单元测试（位于 `tests/unit/` 目录）。执行 `make test` 确保全部测试用例通过，且覆盖率不低于 85%。

4.  **更新文档与变更日志**：若改动涉及用户可见行为（如 API 参数变动、配置项新增），请同步更新 `docs/` 下的对应手册，并在 `CHANGELOG.md` 中按 `[Added]`、`[Changed]`、`[Fixed]` 分类记录。

5.  **发起拉取请求并等待审查**：推送分支至个人复刻仓库后，向主仓库的 `main` 分支发起 Pull Request。PR 描述需清晰说明改动动机、实现方式及测试结果，至少获得一名核心维护者的批准后方可合并。

## 常见问题

**问：LinkVault 是否会对收录的 URL 内容进行本地缓存或快照备份？**

答：不会。LinkVault 严格仅存储 URL 字符串本身及相关的元数据（如收录时间、标签、访问计数）。系统不下载、不代理、不缓存外部资源的内容。所有链接在用户点击时均直接跳转至原始目标地址，流量不经过 LinkVault 服务器。这一设计规避了内容版权风险与存储成本膨胀问题。

**问：如果外部链接失效或域名过期，LinkVault 能自动修复吗？**

答：LinkVault 内置的健康检查模块会定期探测链接的有效性，并在发现 HTTP 状态码非 2xx/3xx 时标记为“异常”并记录最后状态码。但系统不具备自动替换或修复链接的能力，因为原始资源地址的变更通常涉及内容所有者的域名迁移或路径调整，外部系统无法推断新地址。管理员会收到异常告警邮件，需人工核实并手动更新记录。

**问：如何将 LinkVault 当前使用的 SQLite 数据库迁移至生产级的 PostgreSQL？**

答：项目提供了完整的迁移脚本 `scripts/migrate_v1_to_v2.py`。执行前请修改 `config/production.py` 中的 `SQLALCHEMY_DATABASE_URI` 指向目标 PostgreSQL 实例（建议版本 13+），然后运行迁移命令。该脚本会逐表复制数据并重建索引。生产环境切换前强烈建议在预发布环境进行全量演练并备份原始 SQLite 文件。

## 许可证

MIT License

Copyright (c) 2026 LinkVault Maintainers

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

> 外链数量: 250 | 生成时间: 2026-06-23 23:48:06
