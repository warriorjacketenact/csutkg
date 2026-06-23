# ResourceIndex

ResourceIndex 是一个面向开发者、技术研究人员与内容策展人的轻量级外链资源聚合与导航工具。该项目定位于将分散在多个来源的优质技术资料、评测报告、项目文档与参考案例统一收录，并以可检索、可分类、可版本化的方式呈现，帮助用户从海量信息中快速定位所需内容，避免重复检索与信息过载。

ResourceIndex 本身不存储任何第三方内容，仅提供结构化索引与元数据描述。其核心使用场景包括技术团队内部知识库建设、开源项目外部参考链接管理、以及个人学习路径中的书签系统化整理。通过统一的索引格式与清晰的分类体系，用户可以高效维护属于自己的外链资源网络。

## 功能概览

- **统一资源录入接口** 提供标准化的资源条目格式，支持标题、来源、标签、摘要与访问链接的批量导入与单条添加，便于用户将分散的书签与收藏统一纳入管理。

- **多维度分类与筛选** 内置主题分类、内容类型、适用领域等标签系统，用户可按技术栈、应用场景或资源形式快速过滤资源列表，提升查找效率。

- **全文检索与模糊匹配** 针对资源标题、摘要及标签字段构建轻量级索引，支持关键词检索与拼音模糊匹配，降低用户对精确记忆的依赖。

- **资源状态与可用性标记** 支持为每个资源链接标记访问状态（有效、失效、需代理）、最后检查时间与备注信息，帮助用户识别已失效的外部引用。

- **批量导入与导出** 支持 CSV 与 JSON 格式的资源列表导入导出，便于在不同团队或项目之间迁移索引数据，也支持与浏览器书签系统互操作。

- **静态站点生成模式** 内置模板引擎，可将当前索引数据生成为纯静态 HTML 站点，适用于内网部署或个人知识库发布，无需数据库依赖。

- **链接关系图谱预览** 对收录的资源进行域名聚合与引用关系分析，展示高频来源站点与关联资源簇，辅助用户发现潜在高价值信息源。

- **变更历史与版本记录** 记录每次资源条目的增删改操作，支持按时间范围回溯变更内容，满足团队协作场景下的审计与责任追溯需求。

## 应用场景

- **技术团队内部文档中心的外部参考管理** 在撰写技术方案或设计文档时，团队成员需要引用外部资料。ResourceIndex 可作为统一的外部链接管理中心，避免不同成员各自保存书签导致的参考来源不一致或链接失效问题。

- **开源项目 README 与官网的外部资源维护** 开源项目通常需要列出相关工具、插件、教程或社区资源。ResourceIndex 可以帮助维护者分类整理这些外部链接，并定期检查可用性，确保文档中的引用始终有效。

- **个人开发者学习路径的系统化组织** 在学习新技术栈时，开发者会积累大量教程、视频、代码示例和官方文档链接。ResourceIndex 提供标签与检索功能，让用户可以在后续回顾时快速找到特定主题的资料，而非依赖浏览器历史记录。

- **社区内容策展与资源推荐** 技术社区运营者或内容创作者可以定期收集和筛选优质外部内容，形成主题资源合集。ResourceIndex 的分类与导出功能支持将合集生成为可直接分享的静态页面或数据文件。

- **多项目资源复用与同步** 当同一组织内有多个项目需要引用相似的外部资源集时，ResourceIndex 支持导出标准格式的数据文件，供不同项目复用，减少重复劳动并保持引用一致性。

## 快速开始

以下命令演示如何获取 ResourceIndex 源码、安装依赖并启动本地开发服务。

```bash
git clone https://github.com/resourceindex/resourceindex.git
cd resourceindex
pip install -r requirements.txt
python app.py --port 8080
```

执行完成后，在浏览器中访问 http://127.0.0.1:8080 即可进入本地索引管理界面。首次启动会自动生成示例数据文件，用户可按需修改或清空。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 及以上 | 核心运行环境，提供 HTTP 服务与数据处理能力 |
| pip | 21.0 及以上 | Python 包管理工具，用于安装依赖库 |
| SQLite | 3.35 及以上 | 本地轻量级数据库，存储资源条目与元数据 |
| Git | 2.30 及以上 | 用于克隆项目仓库及版本控制集成 |
| Markdown | 3.4 及以上 | 用于解析资源描述中的 Markdown 格式文本 |
| PyYAML | 6.0 及以上 | 用于读取和写入配置文件及资源数据 |
| Jinja2 | 3.1 及以上 | 模板引擎，用于静态站点生成功能 |
| requests | 2.28 及以上 | 用于检查外部链接的可用性状态 |
| pytest | 7.0 及以上 | 可选依赖，用于运行单元测试与集成测试 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 入门指南 | docs/getting-started.md | 如何安装、配置和首次运行 ResourceIndex；如何添加第一条资源记录 |
| 数据管理 | docs/data-management.md | 资源条目的字段含义、批量导入导出格式、数据迁移与备份方法 |
| 高级配置 | docs/advanced-config.md | 自定义分类体系、链接可用性检查策略、静态站点生成参数调优 |
| API 参考 | docs/api-reference.md | 内置 HTTP API 的端点说明、请求与响应格式、错误码定义 |
| 部署指南 | docs/deployment.md | 在生产环境中部署 ResourceIndex 的方式，包括容器化与反向代理配置 |
| 贡献规范 | docs/contributing.md | 面向贡献者的代码风格、提交信息格式、测试用例编写要求 |

## 资源列表

本节列出 ResourceIndex 默认收录的外部参考链接。所有链接均按原始来源原样呈现，未做任何协议、域名或路径改写。

### 评测与参考资源

https://www.realrcreviews.com/theater/ltmkcv
https://www.realrcreviews.com/theater/tzgrhgo
https://www.realrcreviews.com/theater/thcic
https://www.realrcreviews.com/theater/sdmij
https://www.realrcreviews.com/theater/oagsfq
https://www.realrcreviews.com/theater/oxjlxzz
https://www.realrcreviews.com/theater/onzuhlya
https://www.realrcreviews.com/theater/dzxdkjm
https://www.realrcreviews.com/theater/vvyrcca
https://www.realrcreviews.com/theater/caxs
https://www.realrcreviews.com/theater/auex
https://www.realrcreviews.com/theater/qojqihdc
https://www.realrcreviews.com/theater/uxdn
https://www.realrcreviews.com/theater/lewvxryi
https://www.realrcreviews.com/theater/vurgn
https://www.realrcreviews.com/theater/nohlty
https://www.realrcreviews.com/theater/jarq
https://www.realrcreviews.com/theater/eulpxp
https://www.realrcreviews.com/theater/yplmw
https://www.realrcreviews.com/theater/hknomj
https://www.realrcreviews.com/theater/jjbsh
https://www.realrcreviews.com/theater/hxxil
https://www.realrcreviews.com/theater/fvqia
https://www.realrcreviews.com/theater/snuhtfwf
https://www.realrcreviews.com/theater/qyfbhe
https://www.realrcreviews.com/theater/oxog
https://www.realrcreviews.com/theater/ozaltjnv
https://www.realrcreviews.com/theater/hgnra
https://www.realrcreviews.com/theater/rprybtw
https://www.realrcreviews.com/theater/uuqbnz
https://www.realrcreviews.com/theater/yimxtsdu
https://www.realrcreviews.com/theater/izsnq
https://www.realrcreviews.com/theater/cpkltqj
https://www.realrcreviews.com/theater/nexsx
https://www.realrcreviews.com/theater/znlqa
https://www.realrcreviews.com/theater/bvkrk
https://www.realrcreviews.com/theater/rweoswct
https://www.realrcreviews.com/theater/cfsqdt
https://www.realrcreviews.com/theater/ayoil
https://www.realrcreviews.com/theater/ppcpeqg
https://www.realrcreviews.com/theater/bidw
https://www.realrcreviews.com/theater/fujcum
https://www.realrcreviews.com/theater/rlxcbbvy
https://www.realrcreviews.com/theater/kkqw
https://www.realrcreviews.com/theater/opblat
https://www.realrcreviews.com/theater/ithkxum
https://www.realrcreviews.com/theater/ahgemzy
https://www.realrcreviews.com/theater/jmmesrxo
https://www.realrcreviews.com/theater/fjunm
https://www.realrcreviews.com/theater/iwpiqjrx
https://www.realrcreviews.com/theater/ylgz
https://www.realrcreviews.com/theater/ssijukd
https://www.realrcreviews.com/theater/qtxqoy
https://www.realrcreviews.com/theater/vosbvch
https://www.realrcreviews.com/theater/zade
https://www.realrcreviews.com/theater/rtoqaxb
https://www.realrcreviews.com/theater/hkhjyp
https://www.realrcreviews.com/theater/gfviunbw
https://www.realrcreviews.com/theater/qllimuyl
https://www.realrcreviews.com/theater/jfgftorv
https://www.realrcreviews.com/theater/rvfc
https://www.realrcreviews.com/theater/jvhf
https://www.realrcreviews.com/theater/puqbwqgi
https://www.realrcreviews.com/theater/mcddso
https://www.realrcreviews.com/theater/qxpalsal
https://www.realrcreviews.com/theater/gxsuuf
https://www.realrcreviews.com/theater/mbsdo
https://www.realrcreviews.com/theater/dcbya
https://www.realrcreviews.com/theater/pkzbtbp
https://www.realrcreviews.com/theater/tlquf
https://www.realrcreviews.com/theater/letpsi
https://www.realrcreviews.com/theater/xgqiin
https://www.realrcreviews.com/theater/zsmmji
https://www.realrcreviews.com/theater/elqcbos
https://www.realrcreviews.com/theater/smvvmq
https://www.realrcreviews.com/theater/sssivb
https://www.realrcreviews.com/theater/skavyre
https://www.realrcreviews.com/theater/lfhgn
https://www.realrcreviews.com/theater/ngkax
https://www.realrcreviews.com/theater/ghwpj
https://www.realrcreviews.com/theater/yilavi
https://www.realrcreviews.com/theater/qiud
https://www.realrcreviews.com/theater/iden
https://www.realrcreviews.com/theater/tfjhd
https://www.realrcreviews.com/theater/zjgr
https://www.realrcreviews.com/theater/vgezk
https://www.realrcreviews.com/theater/dblpxy
https://www.realrcreviews.com/theater/gsgrug
https://www.realrcreviews.com/theater/usibr
https://www.realrcreviews.com/theater/voca
https://www.realrcreviews.com/theater/jepnqks
https://www.realrcreviews.com/theater/phzki
https://www.realrcreviews.com/theater/rggmes
https://www.realrcreviews.com/theater/civvtn
https://www.realrcreviews.com/theater/ytws
https://www.realrcreviews.com/theater/iesxqddu
https://www.realrcreviews.com/theater/waknscae
https://www.realrcreviews.com/theater/bilvq
https://www.realrcreviews.com/theater/nztyjg
https://www.realrcreviews.com/theater/owlv
https://www.realrcreviews.com/theater/gghvzthu
https://www.realrcreviews.com/theater/eyknmaxy
https://www.realrcreviews.com/theater/uaafg
https://www.realrcreviews.com/theater/xsfm
https://www.realrcreviews.com/theater/prxxhcad
https://www.realrcreviews.com/theater/hqdrofm
https://www.realrcreviews.com/theater/bxnxkbzy
https://www.realrcreviews.com/theater/ktyqhtbw
https://www.realrcreviews.com/theater/qzizuyzw
https://www.realrcreviews.com/theater/tpxbpj
https://www.realrcreviews.com/theater/hpbkr
https://www.realrcreviews.com/theater/pfgnvv
https://www.realrcreviews.com/theater/vliaofip
https://www.realrcreviews.com/theater/qmpbo
https://www.realrcreviews.com/theater/ubkzgzd
https://www.realrcreviews.com/theater/oabhrgk
https://www.realrcreviews.com/theater/yqrqr
https://www.realrcreviews.com/theater/duxtnx
https://www.realrcreviews.com/theater/rfyij
https://www.realrcreviews.com/theater/kvwbr
https://www.realrcreviews.com/theater/ymwd
https://www.realrcreviews.com/theater/eyjuj
https://www.realrcreviews.com/theater/avanfnj
https://www.realrcreviews.com/theater/rxgls
https://www.realrcreviews.com/theater/nfwsoka
https://www.realrcreviews.com/theater/fsnz
https://www.realrcreviews.com/theater/xnyezlb
https://www.realrcreviews.com/theater/kazc
https://www.realrcreviews.com/theater/ktlwgfp
https://www.realrcreviews.com/theater/hdiuudtw
https://www.realrcreviews.com/theater/xswxx
https://www.realrcreviews.com/theater/pzvzj
https://www.realrcreviews.com/theater/pbooduw
https://www.realrcreviews.com/theater/aynq
https://www.realrcreviews.com/theater/kgcnrnmh
https://www.realrcreviews.com/theater/yyooks
https://www.realrcreviews.com/theater/yphrx
https://www.realrcreviews.com/theater/fohb
https://www.realrcreviews.com/theater/jwxxn
https://www.realrcreviews.com/theater/etioteo
https://www.realrcreviews.com/theater/ygoqe
https://www.realrcreviews.com/theater/aoct
https://www.realrcreviews.com/theater/opradtg
https://www.realrcreviews.com/theater/hkxv
https://www.realrcreviews.com/theater/nbga
https://www.realrcreviews.com/theater/lvtayqem
https://www.realrcreviews.com/theater/rtsxrqdv
https://www.realrcreviews.com/theater/anxi
https://www.realrcreviews.com/theater/yxjy
https://www.realrcreviews.com/theater/rwtrrz
https://www.realrcreviews.com/theater/rnkxmq
https://www.realrcreviews.com/theater/rvooxpq
https://www.realrcreviews.com/theater/xbltdld
https://www.realrcreviews.com/theater/ssjppzc
https://www.realrcreviews.com/theater/cactiw
https://www.realrcreviews.com/theater/quykfn
https://www.realrcreviews.com/theater/izgqijwz
https://www.realrcreviews.com/theater/hjwttakb
https://www.realrcreviews.com/theater/fphslatb
https://www.realrcreviews.com/theater/yzztho
https://www.realrcreviews.com/theater/mdyudbu
https://www.realrcreviews.com/theater/stoff
https://www.realrcreviews.com/theater/cdyiex
https://www.realrcreviews.com/theater/xets
https://www.realrcreviews.com/theater/lmqgtij
https://www.realrcreviews.com/theater/hfhdxnhs
https://www.realrcreviews.com/theater/trho
https://www.realrcreviews.com/theater/iwmt
https://www.realrcreviews.com/theater/ehywsns
https://www.realrcreviews.com/theater/smoa
https://www.realrcreviews.com/theater/udtjxdef
https://www.realrcreviews.com/theater/memav
https://www.realrcreviews.com/theater/endn
https://www.realrcreviews.com/theater/vydftjvn
https://www.realrcreviews.com/theater/lqijz
https://www.realrcreviews.com/theater/pewangse
https://www.realrcreviews.com/theater/xksnzljk
https://www.realrcreviews.com/theater/izevszv
https://www.realrcreviews.com/theater/oxlonuy
https://www.realrcreviews.com/theater/xczr
https://www.realrcreviews.com/theater/tiuxdnv
https://www.realrcreviews.com/theater/njgepqac
https://www.realrcreviews.com/theater/jrdgzl
https://www.realrcreviews.com/theater/cgyexf
https://www.realrcreviews.com/theater/wsdw
https://www.realrcreviews.com/theater/ahdwpgv
https://www.realrcreviews.com/theater/wflgvxin
https://www.realrcreviews.com/theater/tckkgr
https://www.realrcreviews.com/theater/jdsvktcc
https://www.realrcreviews.com/theater/qpsyjcv
https://www.realrcreviews.com/theater/meckse
https://www.realrcreviews.com/theater/gtxz
https://www.realrcreviews.com/theater/qghlbgp
https://www.realrcreviews.com/theater/fckwpyb
https://www.realrcreviews.com/theater/byhwht
https://www.realrcreviews.com/theater/rebu
https://www.realrcreviews.com/theater/fjfnqm
https://www.realrcreviews.com/theater/azxznvv
https://www.realrcreviews.com/theater/czzl
https://www.realrcreviews.com/theater/reqrjgg
https://www.realrcreviews.com/theater/fvioxa
https://www.realrcreviews.com/theater/niugtqe
https://www.realrcreviews.com/theater/fmlir
https://www.realrcreviews.com/theater/itqed
https://www.realrcreviews.com/theater/gfvpok
https://www.realrcreviews.com/theater/indruasi
https://www.realrcreviews.com/theater/okzgytu
https://www.realrcreviews.com/theater/tdsjahb
https://www.realrcreviews.com/theater/zjwvupcl
https://www.realrcreviews.com/theater/wfuvmuy
https://www.realrcreviews.com/theater/kyekc
https://www.realrcreviews.com/theater/ovmo
https://www.realrcreviews.com/theater/uuus
https://www.realrcreviews.com/theater/nzsqddwp
https://www.realrcreviews.com/theater/jetg
https://www.realrcreviews.com/theater/rmtrqo
https://www.realrcreviews.com/theater/ttzdrzg
https://www.realrcreviews.com/theater/qity
https://www.realrcreviews.com/theater/ygge
https://www.realrcreviews.com/theater/ftpype
https://www.realrcreviews.com/theater/nxzeyqin
https://www.realrcreviews.com/theater/llzbcdgo
https://www.realrcreviews.com/theater/vvtphim
https://www.realrcreviews.com/theater/gxxebiqz
https://www.realrcreviews.com/theater/gwvyw
https://www.realrcreviews.com/theater/qdzgbfjd
https://www.realrcreviews.com/theater/ghsny
https://www.realrcreviews.com/theater/nwszw
https://www.realrcreviews.com/theater/fdxqfdr
https://www.realrcreviews.com/theater/wxwk
https://www.realrcreviews.com/theater/kuesfczk
https://www.realrcreviews.com/theater/amcvyvz
https://www.realrcreviews.com/theater/sysme
https://www.realrcreviews.com/theater/tkmhis
https://www.realrcreviews.com/theater/tczbqwy
https://www.realrcreviews.com/theater/dgyrc
https://www.realrcreviews.com/theater/nbgvi
https://www.realrcreviews.com/theater/kjtcffgw
https://www.realrcreviews.com/theater/uagksl
https://www.realrcreviews.com/theater/bsnhspax
https://www.realrcreviews.com/theater/hhpedmk
https://www.realrcreviews.com/theater/dioggm
https://www.realrcreviews.com/theater/dyew
https://www.realrcreviews.com/theater/iskwmn
https://www.realrcreviews.com/theater/kgrk
https://www.realrcreviews.com/theater/ifxbizi
https://www.realrcreviews.com/theater/klig
https://www.realrcreviews.com/theater/pxjdq
https://www.realrcreviews.com/theater/drwxqex
https://www.realrcreviews.com/theater/aqcy

## 项目结构

```
resourceindex/
├── app.py                      # 主入口文件，初始化 HTTP 服务与路由注册
├── config.yaml                 # 全局配置文件，包含端口、数据库路径、检查策略等
├── requirements.txt            # Python 依赖清单，用于 pip 批量安装
├── README.md                   # 项目说明文档（当前文件）
├── data/
│   ├── resources.db            # SQLite 数据库文件，存储所有资源条目
│   ├── seeds.json              # 初始示例数据，首次启动时导入
│   └── backups/                # 自动备份目录，按日期存放数据库快照
├── src/
│   ├── core/
│   │   ├── database.py         # 数据库连接池与基础 CRUD 操作
│   │   ├── indexer.py          # 全文索引构建与检索逻辑
│   │   └── validator.py        # URL 格式校验与可用性检查
│   ├── handlers/
│   │   ├── api.py              # RESTful API 路由处理函数
│   │   ├── web.py              # 管理界面页面渲染与表单处理
│   │   └── export.py           # 导出功能（CSV / JSON / 静态站点）
│   ├── models/
│   │   ├── resource.py         # 资源条目数据模型定义
│   │   ├── tag.py              # 标签数据模型
│   │   └── history.py          # 变更历史数据模型
│   └── utils/
│       ├── logger.py           # 日志记录工具，按级别输出至文件与控制台
│       └── parser.py           # 资源描述中的 Markdown 解析与摘要生成
├── templates/
│   ├── base.html               # 管理界面基础模板，包含公共样式与导航
│   ├── index.html              # 资源列表首页模板
│   ├── detail.html             # 单条资源详情页模板
│   └── static/                 # 静态站点生成时使用的输出模板
├── tests/
│   ├── unit/                   # 单元测试用例，覆盖核心模块
│   ├── integration/            # 集成测试用例，覆盖 API 与数据库交互
│   └── fixtures/               # 测试用固定数据文件
├── scripts/
│   ├── migrate.py              # 数据库迁移脚本，用于版本升级
│   └── check_links.py          # 外部链接批量可用性检查脚本
└── docs/
    ├── getting-started.md      # 入门指南
    ├── data-management.md      # 数据管理文档
    ├── advanced-config.md      # 高级配置文档
    ├── api-reference.md        # API 参考文档
    ├── deployment.md           # 部署指南
    └── contributing.md         # 贡献指南
```

## 贡献指南

1. 在 GitHub 上 fork 本仓库，并在本地克隆 fork 后的副本。创建新的功能分支，分支名称应简要描述所处理的问题或新增功能，例如 `fix-import-csv` 或 `add-tag-filter`。

2. 编写代码或文档变更时，请遵循项目现有的代码风格（使用 PEP 8 规范，保持函数单一职责，添加必要的类型注解）。所有新增功能应包含对应的单元测试，测试文件放置在 `tests/unit/` 目录下，命名方式为 `test_<模块名>.py`。

3. 提交代码前，确保所有现有测试和新增测试均能通过。在项目根目录下执行 `pytest tests/` 以运行完整测试套件。同时，请运行 `scripts/check_links.py` 确保未引入格式错误的资源链接。

4. 提交信息采用约定式提交格式，即 `<type>(<scope>): <subject>`，其中 type 可取 `feat`、`fix`、`docs`、`refactor`、`test` 或 `chore`。提交信息正文应简要说明变更原因和影响范围。

5. 向主仓库的 `main` 分支发起 Pull Request，并在描述中引用相关 issue 编号（如有）。项目维护者将在三个工作日内进行审查，必要时会提出修改意见。合并后，您的变更将包含在下一个发布版本中。

## 常见问题

**问：ResourceIndex 是否支持在线直接访问外部链接的实时内容？**

答：不支持。ResourceIndex 仅存储外部链接的元数据（标题、摘要、标签等），不代理或缓存外部页面的实际内容。用户访问链接时将直接跳转至原始站点。项目内置的链接检查功能仅用于探测 HTTP 状态码，以辅助判断链接可用性，不会解析或存储页面正文。

**问：导入大量资源条目时，系统性能是否会下降？**

答：ResourceIndex 使用 SQLite 作为后端存储，单库支持百万级别记录数的常规查询。在导入超过一万条资源时，建议使用批量导入接口（CSV 或 JSON 格式），避免逐条调用 API 产生过多事务开销。同时，全文索引在首次构建时可能耗时较长，索引完成后检索响应可维持在毫秒级别。若条目数超过十万级，可考虑将数据库迁移至 PostgreSQL 并调整连接池配置。

**问：如何迁移 ResourceIndex 到另一台服务器？**

答：迁移过程主要涉及数据库文件与配置文件的复制。首先在目标服务器安装相同版本的 Python 环境及依赖，然后将整个项目目录复制到目标位置。数据库文件位于 `data/resources.db`，配置文件为 `config.yaml`。若使用静态站点生成模式，还需将生成的静态文件一并拷贝。启动服务前，请根据目标服务器的网络环境调整 `config.yaml` 中的 `base_url` 与 `check_timeout` 参数。

## 许可证

MIT License

Copyright (c) 2026 ResourceIndex Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

> 外链数量: 250 | 生成时间: 2026-06-23 23:52:55
