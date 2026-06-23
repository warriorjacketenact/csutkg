# Emha Resource Index

Emha Resource Index 是一个面向技术研究、学术资料整理与网络资源归档的开源外链汇总工具。项目定位为轻量级资源索引系统，主要服务于需要系统化管理大量外部链接的研究人员、开发者以及内容策展人。通过结构化的目录分类与标准化的文档输出，该项目帮助用户从纷杂的原始链接中提炼出可复用、可共享的知识索引，降低信息检索与筛选的时间成本。

本项目不仅提供链接收纳能力，还内置了完整的项目文档模板、分类建议以及自动化生成脚本，使得维护一个大规模外链库从重复劳动转变为可持续的工程实践。无论是建立个人知识库、团队技术周报素材源，还是构建公开的垂直领域导航站，Emha Resource Index 均能提供一致且可靠的底层支持。

## 功能概览

**批量链接导入** 支持从纯文本、CSV 以及常见书签导出文件中批量读取 URL，自动去重并校验可访问性。

**多级分类管理** 允许用户为每个资源链接分配至少两级分类标签，并支持自定义分类体系，适应不同领域的知识组织需求。

**元数据扩展字段** 每条记录除 URL 外，可附加标题、摘要、收录日期、重要等级以及失效标记，便于精细化管理。

**状态监控与报告生成** 内置链接存活检测模块，定期输出失效链接报告，帮助策展人及时更新或下架不可用资源。

**Markdown 原生输出** 所有索引数据最终以纯 Markdown 表格或列表形式导出，与 Git 仓库、静态站点生成器以及文档平台天然兼容。

**全文检索与过滤** 提供基于关键词的轻量级搜索功能，支持按分类、日期范围、状态等维度过滤已收录的资源。

**版本化变更追踪** 所有增删改操作均记录变更日志，便于团队协作时追溯每一次资源调整的原因与责任人。

## 应用场景

**技术团队内部知识库维护** 开发团队可使用 Emha Resource Index 汇总项目相关的官方文档、API 参考、社区博客以及故障排查案例，新成员入职时即可通过该索引快速了解技术生态全貌，减少重复提问。

**学术文献与数据源管理** 研究人员在文献调研阶段会积累大量数据仓库、预印本平台、统计年鉴等链接，通过本项目可按研究主题、数据类型或时间维度分类，撰写综述或论文时可直接引用索引中的结构化列表。

**开源项目推荐与导航站构建** 社区运营者或技术布道师可利用该工具整理某一领域（如机器学习、前端框架、区块链）的开源项目集合，输出为公开的导航页面，供更广泛的开发者群体参考使用。

**个人书签库迁移与去中心化备份** 浏览器书签往往分散在多个设备且缺乏版本控制，本项目提供一种基于 Git 的书签管理方案，所有链接以纯文本形式存储，便于跨平台同步和长期归档。

## 快速开始

以下命令演示如何获取项目源码、安装依赖并启动本地索引服务。

```bash
git clone https://github.com/emha-resource/emha-index.git
cd emha-index
pip install -r requirements.txt
python index.py --init --input ./samples/links.txt
```

执行完成后，将在 `output/` 目录下生成按分类组织的 Markdown 索引文件，并启动一个本地静态预览服务（默认端口 8080）以便即时查看效果。

## 安装要求

| 依赖 | 必需 | 说明 |
|---|---|---|
| Python 3.8 及以上 | 是 | 核心运行环境，用于执行链接处理、分类归并与报告生成逻辑 |
| Git 2.25 及以上 | 是 | 版本控制工具，用于克隆仓库、提交变更记录以及协作同步 |
| Pandoc 2.9 及以上 | 否 | 可选，用于将 Markdown 索引转换为 HTML、PDF 或 Word 格式输出 |
| requests 2.25 及以上 | 是 | Python HTTP 库，用于链接存活检测与状态码校验 |
| python-dotenv 0.19 及以上 | 是 | 环境变量管理，用于存储可选的 API 密钥或代理配置 |
| pytest 6.0 及以上 | 否 | 开发测试依赖，运行单元测试时需要安装 |
| black 21.0 及以上 | 否 | 代码格式化工具，参与贡献前建议使用以保持风格一致 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 入门指南 | docs/getting-started.md | 如何安装、初始化第一个索引库，以及基本的链接增删改操作流程 |
| 分类体系设计 | docs/classification.md | 如何设计符合自身需求的分类树，标签命名规范与层级深度建议 |
| 高级配置 | docs/advanced-config.md | 自定义输出模板、调整检测超时时间、配置自动备份策略等进阶话题 |
| 自动化工作流 | docs/automation.md | 结合 GitHub Actions 或 cron 定时任务实现索引自动更新与失效检测报告发送 |

## 资源列表

本节按类别收录外部参考链接，所有链接均取自用户提供的原始数据，未作任何修改或补全。

程序资源

https://www.emha-shows.org/programme/hlrt.html
https://www.emha-shows.org/programme/ddxkhk.html
https://www.emha-shows.org/programme/bwss.html
https://www.emha-shows.org/programme/nkkc.html
https://www.emha-shows.org/programme/gmctfdnw.html
https://www.emha-shows.org/programme/rbhgdxf.html
https://www.emha-shows.org/programme/kdmlck.html
https://www.emha-shows.org/programme/mttydprb.html
https://www.emha-shows.org/programme/txbq.html
https://www.emha-shows.org/programme/xhdcpr.html
https://www.emha-shows.org/programme/tznp.html
https://www.emha-shows.org/programme/wcplr.html
https://www.emha-shows.org/programme/dwdzcr.html
https://www.emha-shows.org/programme/qjwtgs.html
https://www.emha-shows.org/programme/szpfzckd.html
https://www.emha-shows.org/programme/fhbwcqx.html
https://www.emha-shows.org/programme/xgwrsg.html
https://www.emha-shows.org/programme/lwwxxkp.html
https://www.emha-shows.org/programme/dcqxwr.html
https://www.emha-shows.org/programme/qjplyq.html
https://www.emha-shows.org/programme/yblnrdw.html
https://www.emha-shows.org/programme/hnkb.html
https://www.emha-shows.org/programme/ptjyg.html
https://www.emha-shows.org/programme/mypgmgwp.html
https://www.emha-shows.org/programme/prfdm.html
https://www.emha-shows.org/programme/jhjpd.html
https://www.emha-shows.org/programme/qxqkdz.html
https://www.emha-shows.org/programme/kpkhdd.html
https://www.emha-shows.org/programme/hdlj.html
https://www.emha-shows.org/programme/ktrssd.html
https://www.emha-shows.org/programme/xpcryk.html
https://www.emha-shows.org/programme/ydnpdnc.html
https://www.emha-shows.org/programme/glpbytny.html
https://www.emha-shows.org/programme/nqtg.html
https://www.emha-shows.org/programme/wkrgc.html
https://www.emha-shows.org/programme/hczd.html
https://www.emha-shows.org/programme/zxmfxytf.html
https://www.emha-shows.org/programme/jzjpl.html
https://www.emha-shows.org/programme/ljntgyl.html
https://www.emha-shows.org/programme/dwwzjn.html
https://www.emha-shows.org/programme/wpfkx.html
https://www.emha-shows.org/programme/klgybr.html
https://www.emha-shows.org/programme/mjtbmbgl.html
https://www.emha-shows.org/programme/kcwlhm.html
https://www.emha-shows.org/programme/mlctgdwh.html
https://www.emha-shows.org/programme/byfk.html
https://www.emha-shows.org/programme/jtkhj.html
https://www.emha-shows.org/programme/cpbjg.html
https://www.emha-shows.org/programme/txtk.html
https://www.emha-shows.org/programme/cjlzh.html
https://www.emha-shows.org/programme/pchnb.html
https://www.emha-shows.org/programme/qkzcmb.html
https://www.emha-shows.org/programme/yffrfdl.html
https://www.emha-shows.org/programme/bzlr.html
https://www.emha-shows.org/programme/dsmxjf.html
https://www.emha-shows.org/programme/krykgw.html
https://www.emha-shows.org/programme/hksm.html
https://www.emha-shows.org/programme/qllrkp.html
https://www.emha-shows.org/programme/slnxfbrn.html
https://www.emha-shows.org/programme/gqbmtqyd.html
https://www.emha-shows.org/programme/dpyswr.html
https://www.emha-shows.org/programme/hsng.html
https://www.emha-shows.org/programme/pwryj.html
https://www.emha-shows.org/programme/ryqrbfh.html
https://www.emha-shows.org/programme/twfz.html
https://www.emha-shows.org/programme/sqjsjknq.html
https://www.emha-shows.org/programme/gzbzzjsc.html
https://www.emha-shows.org/programme/fhhgrwp.html
https://www.emha-shows.org/programme/xqnlhj.html
https://www.emha-shows.org/programme/zsydrbst.html
https://www.emha-shows.org/programme/rcjtkpz.html
https://www.emha-shows.org/programme/yhcbgys.html
https://www.emha-shows.org/programme/bfrh.html
https://www.emha-shows.org/programme/dmgsnb.html
https://www.emha-shows.org/programme/qkgyrj.html
https://www.emha-shows.org/programme/rgljpdj.html
https://www.emha-shows.org/programme/zcnbtxsw.html
https://www.emha-shows.org/programme/sbpyflkh.html
https://www.emha-shows.org/programme/qmcfsy.html
https://www.emha-shows.org/programme/dnfhyd.html
https://www.emha-shows.org/programme/bfnp.html
https://www.emha-shows.org/programme/pwsck.html
https://www.emha-shows.org/programme/msnnglnf.html
https://www.emha-shows.org/programme/tsqh.html
https://www.emha-shows.org/programme/cqjzn.html
https://www.emha-shows.org/programme/qzkxhh.html
https://www.emha-shows.org/programme/nsql.html
https://www.emha-shows.org/programme/cnjtw.html
https://www.emha-shows.org/programme/kkpfyr.html
https://www.emha-shows.org/programme/hkyb.html
https://www.emha-shows.org/programme/krjtlj.html
https://www.emha-shows.org/programme/gwshjpby.html
https://www.emha-shows.org/programme/jshlg.html
https://www.emha-shows.org/programme/bwpz.html
https://www.emha-shows.org/programme/dxybgz.html
https://www.emha-shows.org/programme/kfxqpq.html
https://www.emha-shows.org/programme/xtpblf.html
https://www.emha-shows.org/programme/lhhctkp.html
https://www.emha-shows.org/programme/yllllxk.html
https://www.emha-shows.org/programme/qmrdyp.html
https://www.emha-shows.org/programme/ykcnkhf.html
https://www.emha-shows.org/programme/mhcrgngg.html
https://www.emha-shows.org/programme/tnlh.html
https://www.emha-shows.org/programme/rcnglwg.html
https://www.emha-shows.org/programme/zkgndyxc.html
https://www.emha-shows.org/programme/dsgljq.html
https://www.emha-shows.org/programme/lbkfgdh.html
https://www.emha-shows.org/programme/qplrzx.html
https://www.emha-shows.org/programme/jxgtc.html
https://www.emha-shows.org/programme/gmwczwbg.html
https://www.emha-shows.org/programme/sfcllrsk.html
https://www.emha-shows.org/programme/cxksz.html
https://www.emha-shows.org/programme/frbctgc.html
https://www.emha-shows.org/programme/mmpkbrsl.html
https://www.emha-shows.org/programme/tqkd.html
https://www.emha-shows.org/programme/nckq.html
https://www.emha-shows.org/programme/lycpwrh.html
https://www.emha-shows.org/programme/mfrjkpqn.html
https://www.emha-shows.org/programme/krqywg.html
https://www.emha-shows.org/programme/hptg.html
https://www.emha-shows.org/programme/zkmnwchr.html
https://www.emha-shows.org/programme/qfhrdc.html
https://www.emha-shows.org/programme/yqjmwkg.html
https://www.emha-shows.org/programme/qghlqn.html
https://www.emha-shows.org/programme/dffmdy.html
https://www.emha-shows.org/programme/zqskdznr.html
https://www.emha-shows.org/programme/hhzf.html
https://www.emha-shows.org/programme/dtlzfz.html
https://www.emha-shows.org/programme/wtfmg.html
https://www.emha-shows.org/programme/ndpc.html
https://www.emha-shows.org/programme/gmnscwyd.html
https://www.emha-shows.org/programme/zwxhzhsp.html
https://www.emha-shows.org/programme/rbyfnyb.html
https://www.emha-shows.org/programme/zljyycfq.html
https://www.emha-shows.org/programme/xytqlc.html
https://www.emha-shows.org/programme/bzfm.html
https://www.emha-shows.org/programme/drpbyb.html
https://www.emha-shows.org/programme/fnxkbpy.html
https://www.emha-shows.org/programme/xlywlq.html
https://www.emha-shows.org/programme/tgbq.html
https://www.emha-shows.org/programme/mmlrythk.html
https://www.emha-shows.org/programme/syzbylqt.html
https://www.emha-shows.org/programme/llkpxjr.html
https://www.emha-shows.org/programme/jcjjr.html
https://www.emha-shows.org/programme/gtbwndpw.html
https://www.emha-shows.org/programme/xtcprl.html
https://www.emha-shows.org/programme/kcznql.html
https://www.emha-shows.org/programme/wsysz.html
https://www.emha-shows.org/programme/npwt.html
https://www.emha-shows.org/programme/gxfyzrwp.html
https://www.emha-shows.org/programme/sshtphfw.html
https://www.emha-shows.org/programme/hkzg.html
https://www.emha-shows.org/programme/kdzdzz.html
https://www.emha-shows.org/programme/cxtym.html
https://www.emha-shows.org/programme/kqtdcr.html
https://www.emha-shows.org/programme/syfcynnr.html
https://www.emha-shows.org/programme/lpcjjkk.html
https://www.emha-shows.org/programme/cdhcg.html
https://www.emha-shows.org/programme/zjgrbqzt.html
https://www.emha-shows.org/programme/xfhrxc.html
https://www.emha-shows.org/programme/pgdzh.html
https://www.emha-shows.org/programme/qklmmw.html
https://www.emha-shows.org/programme/ypdplys.html
https://www.emha-shows.org/programme/lrqcrts.html
https://www.emha-shows.org/programme/yjhphhw.html
https://www.emha-shows.org/programme/zqhfbrgj.html
https://www.emha-shows.org/programme/cbcpy.html
https://www.emha-shows.org/programme/djkyld.html
https://www.emha-shows.org/programme/qtxwpf.html
https://www.emha-shows.org/programme/jfgss.html
https://www.emha-shows.org/programme/grsknnrh.html
https://www.emha-shows.org/programme/trfd.html
https://www.emha-shows.org/programme/xtffkr.html
https://www.emha-shows.org/programme/kfdbgg.html
https://www.emha-shows.org/programme/xjgrmf.html
https://www.emha-shows.org/programme/bmzt.html
https://www.emha-shows.org/programme/sfmtwkfq.html
https://www.emha-shows.org/programme/ptzcg.html
https://www.emha-shows.org/programme/cnyfn.html
https://www.emha-shows.org/programme/fcwrnyf.html
https://www.emha-shows.org/programme/cztfh.html
https://www.emha-shows.org/programme/jfbrt.html
https://www.emha-shows.org/programme/lwdqllj.html
https://www.emha-shows.org/programme/yhhzctb.html
https://www.emha-shows.org/programme/lsnncbc.html
https://www.emha-shows.org/programme/rcywrmk.html
https://www.emha-shows.org/programme/tdsy.html
https://www.emha-shows.org/programme/qhbnkk.html
https://www.emha-shows.org/programme/jctyf.html
https://www.emha-shows.org/programme/wdbbd.html
https://www.emha-shows.org/programme/nslz.html
https://www.emha-shows.org/programme/xkqwkz.html
https://www.emha-shows.org/programme/tbkn.html
https://www.emha-shows.org/programme/rrmcwtt.html
https://www.emha-shows.org/programme/zwlzgcyw.html
https://www.emha-shows.org/programme/jlzpb.html
https://www.emha-shows.org/programme/bksy.html
https://www.emha-shows.org/programme/hlrj.html
https://www.emha-shows.org/programme/zmgsbrwx.html
https://www.emha-shows.org/programme/msfcrbyk.html
https://www.emha-shows.org/programme/fhfckrz.html
https://www.emha-shows.org/programme/lggrjdr.html
https://www.emha-shows.org/programme/srssqptf.html
https://www.emha-shows.org/programme/wcrsl.html
https://www.emha-shows.org/programme/nxms.html
https://www.emha-shows.org/programme/zqlqwtkk.html
https://www.emha-shows.org/programme/hmym.html
https://www.emha-shows.org/programme/ztwdrhty.html
https://www.emha-shows.org/programme/xxwwfb.html
https://www.emha-shows.org/programme/frtsmyg.html
https://www.emha-shows.org/programme/chqnm.html
https://www.emha-shows.org/programme/dmktjd.html
https://www.emha-shows.org/programme/lxfwfyn.html
https://www.emha-shows.org/programme/jtblg.html
https://www.emha-shows.org/programme/bxbh.html
https://www.emha-shows.org/programme/rrgmgzt.html
https://www.emha-shows.org/programme/kkmnyq.html
https://www.emha-shows.org/programme/dwzgcw.html
https://www.emha-shows.org/programme/ldpnjjy.html
https://www.emha-shows.org/programme/nfgf.html
https://www.emha-shows.org/programme/whbrc.html
https://www.emha-shows.org/programme/knpsxn.html
https://www.emha-shows.org/programme/rlwmkmf.html
https://www.emha-shows.org/programme/fznxlgl.html
https://www.emha-shows.org/programme/xncrfc.html
https://www.emha-shows.org/programme/whbzf.html
https://www.emha-shows.org/programme/jjnyk.html
https://www.emha-shows.org/programme/xdglsb.html
https://www.emha-shows.org/programme/fdhzcfq.html
https://www.emha-shows.org/programme/cykkl.html
https://www.emha-shows.org/programme/pxzbp.html
https://www.emha-shows.org/programme/qkdkqw.html
https://www.emha-shows.org/programme/ydgdzfm.html
https://www.emha-shows.org/programme/gfpzrzpk.html
https://www.emha-shows.org/programme/ymhfqbk.html
https://www.emha-shows.org/programme/kjffrm.html
https://www.emha-shows.org/programme/ckhtz.html
https://www.emha-shows.org/programme/gphhbfbg.html
https://www.emha-shows.org/programme/sczfdyjy.html
https://www.emha-shows.org/programme/qjgbqn.html
https://www.emha-shows.org/programme/jlnlq.html
https://www.emha-shows.org/programme/cmxkm.html
https://www.emha-shows.org/programme/ffkhldk.html
https://www.emha-shows.org/programme/hxfs.html
https://www.emha-shows.org/programme/tjhm.html
https://www.emha-shows.org/programme/dhwxjr.html
https://www.emha-shows.org/programme/gbskxyyd.html
https://www.emha-shows.org/programme/kjpcxf.html
https://www.emha-shows.org/programme/mzgctldd.html
https://www.emha-shows.org/programme/tdsj.html

## 项目结构

```
emha-index/
├── index.py                 # 主入口脚本，负责解析命令行参数并调度各模块
├── requirements.txt         # Python 依赖声明文件，供 pip 一次性安装
├── .env.example             # 环境变量模板，包含代理设置、超时阈值等可配置项
├── core/
│   ├── loader.py            # 链接加载模块，支持从文件、目录或远程 URL 读取原始数据
│   ├── classifier.py        # 分类引擎，基于规则或机器学习标签对链接进行自动归类
│   ├── checker.py           # 存活检测模块，并发请求目标 URL 并记录状态码与响应时间
│   └── exporter.py          # 输出渲染器，将内部数据结构转换为 Markdown 或 JSON 格式
├── config/
│   ├── default.yaml         # 默认分类映射表与输出模板路径，用户可按需覆盖
│   └── custom_rules.yaml    # 用户自定义分类规则，支持正则表达式匹配 URL 路径
├── data/
│   ├── raw/                 # 存放原始导入文件，保留备份以便重新处理
│   ├── indexed/             # 经过去重、校验后的正式索引数据，以 JSON Lines 格式存储
│   └── reports/             # 每日或每周生成的失效链接报告与统计摘要
├── output/                  # 最终导出的 Markdown 文档存放目录，可直接用于站点发布
├── tests/
│   ├── test_loader.py       # 单元测试：覆盖不同格式输入文件的解析逻辑
│   ├── test_checker.py      # 单元测试：模拟 HTTP 响应，验证状态检测的准确性
│   └── test_exporter.py     # 单元测试：检查输出 Markdown 是否符合预期结构
└── docs/
    ├── getting-started.md   # 新手引导，包含详细截图与常见操作示例
    ├── classification.md    # 分类体系设计文档，附带案例与最佳实践
    ├── advanced-config.md   # 高级配置说明，包括性能调优与插件扩展接口
    └── automation.md        # CI/CD 集成指南，帮助用户实现索引自动更新
```

## 贡献指南

1. 首先在 GitHub 上 Fork 本仓库，然后克隆至本地开发环境。建议在独立的功能分支上进行修改，分支命名遵循 `feature/` 或 `fix/` 前缀加简短描述。

2. 运行 `pytest` 确保现有测试全部通过。若新增功能或修复缺陷，请同步补充对应的单元测试用例，测试覆盖率不低于 85%。

3. 代码风格统一使用 Black 格式化，提交前执行 `black .` 进行全量格式化。同时使用 `flake8` 进行静态检查，确保无严重警告或错误。

4. 提交信息采用约定式提交格式，例如 `feat: add batch import from CSV` 或 `fix: handle redirect loop in checker`。每个提交应聚焦于单一逻辑变更。

5. 发起 Pull Request 前，请同步主仓库的 main 分支，解决冲突后再次运行完整测试套件。PR 描述中需清晰说明变更动机、实现方案以及影响范围。

## 常见问题

**问：导入大量链接后，分类速度明显下降，如何优化？**

答：当链接总数超过 5000 条时，建议启用配置文件中的批量模式（`batch_mode: true`），该模式会将分类任务拆分为多个子任务并行处理。同时可适当调整 `checker` 模块的并发数（默认 10），根据网络状况和机器性能设置为 20 至 50 之间。若仍无法满足需求，可考虑使用外部数据库（如 SQLite）替代默认的 JSON 存储。

**问：输出 Markdown 后，部分链接显示为裸域名，无法自动跳转，是否影响使用？**

答：Emha Resource Index 遵循用户输入的原始格式，不对 URL 做任何协议补全或域名规范化处理。若需要统一添加 `https://` 前缀，可在配置文件中设置 `force_https: true`，系统将在输出阶段对缺少协议的链接进行转换。但请注意，该操作可能对仅支持 HTTP 的旧站点造成访问失败，建议谨慎启用。

**问：如何定期自动运行索引更新并发送失效报告？**

答：项目根目录下提供了 `scripts/cron_task.sh` 示例脚本，用户可通过 crontab 或 Windows 任务计划器每天定时执行。该脚本会自动拉取最新代码、运行增量索引，并将生成的报告文件通过邮件或 Webhook 发送至指定接收方。详细配置请参考 `docs/automation.md` 中的 CI/CD 章节。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-06-24 00:05:52
