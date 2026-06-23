# HyperLink Atlas

HyperLink Atlas 是一个面向技术文档工程师、开源项目维护者以及信息架构师的高性能外链资源归集与导航系统。本项目并非简单的书签集合，而是一套具备结构化分类、状态监控与快速检索能力的静态站点生成框架，专用于管理超大规模（千级至万级）的 URL 资源池。

项目定位于解决以下核心问题：当技术团队或社区积累了大量分散于文档、Wiki 和 Issue 中的参考链接后，往往面临链接失效、分类混乱、检索困难以及缺乏统一呈现入口的困境。HyperLink Atlas 提供了一套从数据录入、分类标注、健康检查到前端导航界面的完整工作流，使维护者能够以极低的成本将原始 URL 列表转化为专业、清晰、可维护的技术资源门户。

本项目面向的用户群体包括：需要维护 API 文档生态系统的开发者、开源社区布道师、技术培训资料编写者，以及任何需要向外界系统化展示大量参考信息的技术团队。

## 功能概览

**批量链接导入与解析** 支持从 CSV、JSON 或纯文本列表中批量导入 URL，自动识别协议头与域名结构，完成初步的合法性校验与去重。

**多维度分类与标签系统** 允许为每个链接分配所属领域、技术栈、内容类型（如教程、规范、工具）以及自定义标签，支持层级分类与模糊检索。

**定时可用性健康检查** 内置基于 HTTP 状态码的链接存活检测任务，可自定义检查周期，自动标记失效或重定向的链接，并生成异常报告。

**静态站点渲染引擎** 基于模板引擎将结构化数据渲染为纯静态 HTML 页面，无需后端服务即可部署至任意 Web 服务器或 CDN，确保高并发下的访问性能。

**可配置的导航视图** 提供分类索引页、字母序索引页、标签聚合页与关键词搜索页四种导航视图，终端用户可根据习惯快速定位目标资源。

**访问统计与热度排序** 集成轻量级日志分析模块，统计各链接的点击频次与来源页面，支持按热度对资源列表进行动态排序，帮助识别高价值内容。

## 应用场景

**开源项目参考文档门户** 当开源项目需要对外陈列大量第三方依赖、相关标准、扩展工具或社区案例时，维护者可使用 HyperLink Atlas 快速生成一个独立的参考链接页面，避免在主项目 README 中堆砌过长列表，同时保证链接的可维护性与可追溯性。

**技术培训与课程资料包** 培训机构或企业内部讲师在交付技术课程时，通常需要提供数十乃至数百个课外阅读链接。通过本项目构建的导航站点可作为课程附件分发，学员可在线检索并按主题浏览，显著提升资料获取效率。

**技术社区资源聚合站** 技术社区或用户组可将日常讨论中提及的高质量文章、视频、开源仓库等外链统一收录至 HyperLink Atlas 生成的站点中，作为社区知识沉淀的一部分，降低新人查找历史讨论背景的门槛。

**个人知识库外链管理** 对于长期撰写技术博客或维护个人知识库的开发者，本项目可作为外部引用源的管理中枢，将散落在各篇文章中的引用链接集中管理，并自动检测链接有效性，避免文章中出现大量死链。

## 快速开始

以下指令适用于 Linux 与 macOS 环境，Windows 用户可使用 WSL 或 Git Bash 执行。

```bash
# 克隆项目仓库至本地
git clone https://github.com/hyperlink-atlas/hyperlink-atlas.git
cd hyperlink-atlas

# 安装项目依赖（使用 pip 与虚拟环境）
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# 执行初始化数据导入与站点构建
./scripts/import.sh --input ./data/seed_urls.json --output ./dist
./scripts/build.sh --watch
```

执行完成后，静态页面将生成于 ./dist 目录下，可直接使用浏览器打开 index.html 预览，或通过 `python3 -m http.server 8080` 启动本地测试服务器。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 及以上 | 核心运行环境，用于数据解析、模板渲染及健康检查调度 |
| pip | 21.0 及以上 | Python 包管理器，用于安装 requirements.txt 中声明的第三方库 |
| Git | 2.25 及以上 | 用于克隆仓库及版本管理，非运行时强制依赖，但建议安装 |
| 内存 | 512 MB 及以上 | 处理千级链接数据时的最低内存要求，万级链接建议 1 GB 以上 |
| 磁盘空间 | 200 MB 及以上 | 包含源码、依赖库及生成的静态页面，链接数量增长时存储需求递增 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | docs/user-guide/installation.md, docs/user-guide/quick-start.md | 如何安装、配置并运行本项目生成第一个导航站点 |
| 数据格式规范 | docs/data-format/schema.md, docs/data-format/fields.md | 输入数据应采用何种 JSON 或 CSV 结构，各字段的含义与约束 |
| 模板定制指南 | docs/customization/theming.md, docs/customization/layouts.md | 如何修改页面样式与布局，以适应不同品牌或视觉风格要求 |
| 运维与监控 | docs/operations/health-check.md, docs/operations/logging.md | 如何配置链接健康检查策略，以及如何解读运行日志 |

## 资源列表

### 视频资源分类节点

https://www.365myfl.com/vodshow/jzsjw.html
https://www.365myfl.com/vodshow/gxnmptqw.html
https://www.365myfl.com/vodshow/nhzb.html
https://www.365myfl.com/vodshow/cnhdx.html
https://www.365myfl.com/vodshow/pjmpy.html
https://www.365myfl.com/vodshow/mmyknlrg.html
https://www.365myfl.com/vodshow/ffwddcw.html
https://www.365myfl.com/vodshow/jksjx.html
https://www.365myfl.com/vodshow/llhxzmt.html
https://www.365myfl.com/vodshow/rnjchkx.html
https://www.365myfl.com/vodshow/thzj.html
https://www.365myfl.com/vodshow/hkwg.html
https://www.365myfl.com/vodshow/tnyg.html
https://www.365myfl.com/vodshow/gdxlhwqq.html
https://www.365myfl.com/vodshow/dfqpfz.html
https://www.365myfl.com/vodshow/ghxdpdcf.html
https://www.365myfl.com/vodshow/ddfltg.html
https://www.365myfl.com/vodshow/kmrkxy.html
https://www.365myfl.com/vodshow/chkpl.html
https://www.365myfl.com/vodshow/ywcfdqg.html
https://www.365myfl.com/vodshow/wsgtj.html
https://www.365myfl.com/vodshow/jbckk.html
https://www.365myfl.com/vodshow/ldrxqhk.html
https://www.365myfl.com/vodshow/plqpd.html
https://www.365myfl.com/vodshow/rwnsgcr.html
https://www.365myfl.com/vodshow/zcyfqqxh.html
https://www.365myfl.com/vodshow/cgxjn.html
https://www.365myfl.com/vodshow/bwmt.html
https://www.365myfl.com/vodshow/syjjggjw.html
https://www.365myfl.com/vodshow/phngh.html
https://www.365myfl.com/vodshow/xkzgzt.html
https://www.365myfl.com/vodshow/tfll.html
https://www.365myfl.com/vodshow/mwpcmyyc.html
https://www.365myfl.com/vodshow/jysjt.html
https://www.365myfl.com/vodshow/wlyqp.html
https://www.365myfl.com/vodshow/dhftgp.html
https://www.365myfl.com/vodshow/wlfkz.html
https://www.365myfl.com/vodshow/xyjzhk.html
https://www.365myfl.com/vodshow/kcmxcn.html
https://www.365myfl.com/vodshow/gkzfxngk.html
https://www.365myfl.com/vodshow/spnhnwzl.html
https://www.365myfl.com/vodshow/wsmjc.html
https://www.365myfl.com/vodshow/jhnpn.html
https://www.365myfl.com/vodshow/hcrs.html
https://www.365myfl.com/vodshow/pfndx.html
https://www.365myfl.com/vodshow/clrnb.html
https://www.365myfl.com/vodshow/zpczztbs.html
https://www.365myfl.com/vodshow/yglnnmf.html
https://www.365myfl.com/vodshow/bmjj.html
https://www.365myfl.com/vodshow/xnnpjw.html
https://www.365myfl.com/vodshow/tnyq.html
https://www.365myfl.com/vodshow/hkhp.html
https://www.365myfl.com/vodshow/znwmlmlm.html
https://www.365myfl.com/vodshow/qspzcm.html
https://www.365myfl.com/vodshow/jctdr.html
https://www.365myfl.com/vodshow/qzhwxg.html
https://www.365myfl.com/vodshow/szkzhykb.html
https://www.365myfl.com/vodshow/fjtsczm.html
https://www.365myfl.com/vodshow/xlwqwq.html
https://www.365myfl.com/vodshow/jjnkw.html
https://www.365myfl.com/vodshow/gkypmgwz.html
https://www.365myfl.com/vodshow/szncjrny.html
https://www.365myfl.com/vodshow/wmzyn.html
https://www.365myfl.com/vodshow/pdlcg.html
https://www.365myfl.com/vodshow/cdfqs.html
https://www.365myfl.com/vodshow/fxldrjd.html
https://www.365myfl.com/vodshow/xqbrfn.html
https://www.365myfl.com/vodshow/lzcfnbf.html
https://www.365myfl.com/vodshow/jbsqr.html
https://www.365myfl.com/vodshow/pnwyw.html
https://www.365myfl.com/vodshow/xbcdmz.html
https://www.365myfl.com/vodshow/pgxcx.html
https://www.365myfl.com/vodshow/hfwl.html
https://www.365myfl.com/vodshow/nbnm.html
https://www.365myfl.com/vodshow/lfycdzq.html
https://www.365myfl.com/vodshow/ddkfnl.html
https://www.365myfl.com/vodshow/llqsndh.html
https://www.365myfl.com/vodshow/mnttpxcr.html
https://www.365myfl.com/vodshow/fblcwyg.html
https://www.365myfl.com/vodshow/lsbwgqy.html
https://www.365myfl.com/vodshow/jqkyx.html
https://www.365myfl.com/vodshow/qyskpm.html
https://www.365myfl.com/vodshow/ylygmjs.html
https://www.365myfl.com/vodshow/xggzpl.html
https://www.365myfl.com/vodshow/kgqktt.html
https://www.365myfl.com/vodshow/xpjmbl.html
https://www.365myfl.com/vodshow/kxzcnf.html
https://www.365myfl.com/vodshow/shzdpmws.html
https://www.365myfl.com/vodshow/wgzcq.html
https://www.365myfl.com/vodshow/rjrktlk.html
https://www.365myfl.com/vodshow/ttzb.html
https://www.365myfl.com/vodshow/xkhghx.html
https://www.365myfl.com/vodshow/fgkgfkt.html
https://www.365myfl.com/vodshow/qtgklg.html
https://www.365myfl.com/vodshow/sfnzdjxd.html
https://www.365myfl.com/vodshow/bbzb.html
https://www.365myfl.com/vodshow/ymbrysy.html
https://www.365myfl.com/vodshow/pkmcm.html
https://www.365myfl.com/vodshow/mgnrrxfj.html
https://www.365myfl.com/vodshow/cxhtc.html
https://www.365myfl.com/vodshow/fjzmfqk.html
https://www.365myfl.com/vodshow/xmmlms.html
https://www.365myfl.com/vodshow/tcts.html
https://www.365myfl.com/vodshow/qmrxck.html
https://www.365myfl.com/vodshow/sbqwbhyy.html
https://www.365myfl.com/vodshow/bybk.html
https://www.365myfl.com/vodshow/sbznsksw.html
https://www.365myfl.com/vodshow/zjmzwlhc.html
https://www.365myfl.com/vodshow/hdsz.html
https://www.365myfl.com/vodshow/qlslfd.html
https://www.365myfl.com/vodshow/drrwcj.html
https://www.365myfl.com/vodshow/gggtkhgw.html
https://www.365myfl.com/vodshow/ssykbnfx.html
https://www.365myfl.com/vodshow/mlnbkyfh.html
https://www.365myfl.com/vodshow/zdxjszdy.html
https://www.365myfl.com/vodshow/hfqs.html
https://www.365myfl.com/vodshow/pqghb.html
https://www.365myfl.com/vodshow/yqjjdcn.html
https://www.365myfl.com/vodshow/bxzk.html
https://www.365myfl.com/vodshow/znjfqtzy.html
https://www.365myfl.com/vodshow/mxdbwzkg.html
https://www.365myfl.com/vodshow/txbg.html
https://www.365myfl.com/vodshow/hmzs.html
https://www.365myfl.com/vodshow/dqfyqr.html
https://www.365myfl.com/vodshow/gyycqcmz.html
https://www.365myfl.com/vodshow/yypqwwq.html
https://www.365myfl.com/vodshow/qbkjbz.html
https://www.365myfl.com/vodshow/hrgt.html
https://www.365myfl.com/vodshow/kcpqnp.html
https://www.365myfl.com/vodshow/ytpmggn.html
https://www.365myfl.com/vodshow/gbhkmnmc.html
https://www.365myfl.com/vodshow/shrndtnl.html
https://www.365myfl.com/vodshow/wfjml.html
https://www.365myfl.com/vodshow/kqqgyy.html
https://www.365myfl.com/vodshow/hkhl.html
https://www.365myfl.com/vodshow/tbjj.html
https://www.365myfl.com/vodshow/cthzl.html
https://www.365myfl.com/vodshow/bycs.html
https://www.365myfl.com/vodshow/drgryz.html
https://www.365myfl.com/vodshow/hzbx.html
https://www.365myfl.com/vodshow/zqmrlgjg.html
https://www.365myfl.com/vodshow/xksxhq.html
https://www.365myfl.com/vodshow/ffhhjfk.html
https://www.365myfl.com/vodshow/gbjdmxln.html
https://www.365myfl.com/vodshow/jldqs.html
https://www.365myfl.com/vodshow/grkcmrgs.html
https://www.365myfl.com/vodshow/ygyfhbl.html
https://www.365myfl.com/vodshow/kxpdbw.html
https://www.365myfl.com/vodshow/mphdwlsr.html
https://www.365myfl.com/vodshow/lryxtbl.html
https://www.365myfl.com/vodshow/nsxj.html
https://www.365myfl.com/vodshow/qnzlps.html
https://www.365myfl.com/vodshow/nxzm.html
https://www.365myfl.com/vodshow/hyqx.html
https://www.365myfl.com/vodshow/twtd.html
https://www.365myfl.com/vodshow/hxwy.html
https://www.365myfl.com/vodshow/pcdxx.html
https://www.365myfl.com/vodshow/nbxh.html
https://www.365myfl.com/vodshow/lmkbsbg.html
https://www.365myfl.com/vodshow/tllk.html
https://www.365myfl.com/vodshow/mjytszxz.html
https://www.365myfl.com/vodshow/tpbw.html
https://www.365myfl.com/vodshow/chtyc.html
https://www.365myfl.com/vodshow/swpwwzdx.html
https://www.365myfl.com/vodshow/bzgs.html
https://www.365myfl.com/vodshow/ncfq.html
https://www.365myfl.com/vodshow/bsdm.html
https://www.365myfl.com/vodshow/hpfw.html
https://www.365myfl.com/vodshow/thrw.html
https://www.365myfl.com/vodshow/jjbff.html
https://www.365myfl.com/vodshow/wkkqk.html
https://www.365myfl.com/vodshow/dhyzgd.html
https://www.365myfl.com/vodshow/bbgx.html
https://www.365myfl.com/vodshow/fktschn.html
https://www.365myfl.com/vodshow/hfpw.html
https://www.365myfl.com/vodshow/fdhwfbl.html
https://www.365myfl.com/vodshow/hmks.html
https://www.365myfl.com/vodshow/glyjfrds.html
https://www.365myfl.com/vodshow/sjppgxyl.html
https://www.365myfl.com/vodshow/mwzdnqzs.html
https://www.365myfl.com/vodshow/tsgx.html
https://www.365myfl.com/vodshow/hhqk.html
https://www.365myfl.com/vodshow/flzzlny.html
https://www.365myfl.com/vodshow/qmgtlw.html
https://www.365myfl.com/vodshow/scgwdgxl.html
https://www.365myfl.com/vodshow/gjfsrbwg.html
https://www.365myfl.com/vodshow/skwcqcsk.html
https://www.365myfl.com/vodshow/tgjq.html
https://www.365myfl.com/vodshow/cknzt.html
https://www.365myfl.com/vodshow/gwnptlbl.html
https://www.365myfl.com/vodshow/smwtxcsr.html
https://www.365myfl.com/vodshow/wgywz.html
https://www.365myfl.com/vodshow/dpgqbz.html
https://www.365myfl.com/vodshow/cwkhy.html
https://www.365myfl.com/vodshow/tdbd.html
https://www.365myfl.com/vodshow/xmnjkc.html
https://www.365myfl.com/vodshow/fjtftmh.html
https://www.365myfl.com/vodshow/ntxp.html
https://www.365myfl.com/vodshow/wtyty.html
https://www.365myfl.com/vodshow/nwkl.html
https://www.365myfl.com/vodshow/bdxg.html
https://www.365myfl.com/vodshow/ylpzdmt.html
https://www.365myfl.com/vodshow/qttsxq.html
https://www.365myfl.com/vodshow/zxrczfbc.html
https://www.365myfl.com/vodshow/xzzgnt.html
https://www.365myfl.com/vodshow/thxb.html
https://www.365myfl.com/vodshow/rrxntdt.html
https://www.365myfl.com/vodshow/bkql.html
https://www.365myfl.com/vodshow/yhmfjjq.html
https://www.365myfl.com/vodshow/znknwjts.html
https://www.365myfl.com/vodshow/hmfz.html
https://www.365myfl.com/vodshow/kwqflq.html
https://www.365myfl.com/vodshow/rbkmdcf.html
https://www.365myfl.com/vodshow/szswgxsh.html
https://www.365myfl.com/vodshow/bqpp.html
https://www.365myfl.com/vodshow/dkgfzg.html
https://www.365myfl.com/vodshow/gpbhnpsx.html
https://www.365myfl.com/vodshow/mylqkpnc.html
https://www.365myfl.com/vodshow/kbfqpc.html
https://www.365myfl.com/vodshow/bdmp.html
https://www.365myfl.com/vodshow/nhxn.html
https://www.365myfl.com/vodshow/lcflttp.html
https://www.365myfl.com/vodshow/yzdflhp.html
https://www.365myfl.com/vodshow/xpzxzt.html
https://www.365myfl.com/vodshow/kybpzp.html
https://www.365myfl.com/vodshow/mlbjxhfp.html
https://www.365myfl.com/vodshow/pxyhg.html
https://www.365myfl.com/vodshow/yylgggh.html
https://www.365myfl.com/vodshow/gtyftzpk.html
https://www.365myfl.com/vodshow/cthjp.html
https://www.365myfl.com/vodshow/krkwbt.html
https://www.365myfl.com/vodshow/hlsx.html
https://www.365myfl.com/vodshow/trzl.html
https://www.365myfl.com/vodshow/gdqgzksl.html
https://www.365myfl.com/vodshow/djrmjn.html
https://www.365myfl.com/vodshow/gzwfyyyl.html
https://www.365myfl.com/vodshow/ydnttxc.html
https://www.365myfl.com/vodshow/fsxnfwy.html
https://www.365myfl.com/vodshow/rmhhlhq.html
https://www.365myfl.com/vodshow/dzygtl.html
https://www.365myfl.com/vodshow/lpwfdxf.html
https://www.365myfl.com/vodshow/jwhrk.html
https://www.365myfl.com/vodshow/gbwyymgb.html
https://www.365myfl.com/vodshow/zkxxdksm.html
https://www.365myfl.com/vodshow/cmylx.html
https://www.365myfl.com/vodshow/tmpz.html
https://www.365myfl.com/vodshow/mbxzrdyw.html
https://www.365myfl.com/vodshow/byhk.html
https://www.365myfl.com/vodshow/ynksfdk.html
https://www.365myfl.com/vodshow/ffpgjlp.html

## 项目结构

```
hyperlink-atlas/
├── data/                                # 原始数据与缓存目录
│   ├── seed/                            # 初始种子数据（JSON/CSV格式）
│   │   ├── 51st_batch.json              # 第51批资源导入数据
│   │   └── schema_v2.json               # 数据字段定义文件
│   ├── cache/                           # 健康检查结果缓存
│   │   ├── last_check.json              # 最近一次全量检查摘要
│   │   └── failure_report.log           # 失效链接详细日志
│   └── tags/                            # 标签与分类映射表
│       ├── category_tree.yaml           # 层级分类定义
│       └── synonyms.dict                # 同义词扩展词典
├── src/                                 # 核心源代码目录
│   ├── core/                            # 数据解析与索引模块
│   │   ├── importer.py                  # 实现批量导入与格式转换
│   │   ├── validator.py                 # URL合法性校验与规范化
│   │   └── indexer.py                   # 构建倒排索引与标签索引
│   ├── checker/                         # 链接健康检查模块
│   │   ├── http_client.py               # 异步HTTP请求封装
│   │   ├── scheduler.py                 # 检查任务调度器
│   │   └── reporter.py                  # 生成健康报告
│   ├── renderer/                        # 静态页面渲染引擎
│   │   ├── engine.py                    # 模板引擎主入口
│   │   ├── templates/                   # Jinja2 模板目录
│   │   │   ├── index.html.j2            # 首页模板
│   │   │   ├── category.html.j2         # 分类视图模板
│   │   │   └── detail.html.j2           # 链接详情页模板
│   │   └── assets/                      # 静态资源（CSS/JS）
│   │       ├── style.css                # 主样式表
│   │       └── search.js                # 前端搜索逻辑
│   └── cli/                             # 命令行接口模块
│       ├── main.py                      # CLI入口，解析子命令
│       └── commands/                    # 各子命令实现
│           ├── build.py                 # build命令
│           ├── check.py                 # check命令
│           └── serve.py                 # serve命令
├── tests/                               # 单元测试与集成测试目录
│   ├── unit/                            # 针对各模块的单元测试
│   │   ├── test_validator.py
│   │   └── test_indexer.py
│   └── fixtures/                        # 测试用样例数据
│       └── sample_urls.json
├── scripts/                             # 辅助运维脚本
│   ├── import.sh                        # 一键导入并构建
│   ├── backup.sh                        # 数据备份脚本
│   └── migrate_v1_to_v2.py              # 数据迁移工具
├── docs/                                # 项目文档（用户手册与开发指南）
│   ├── user-guide/                      # 用户手册
│   ├── developer-guide/                 # 开发者指南
│   └── api/                             # API 接口文档（如适用）
├── requirements.txt                     # Python 依赖声明
├── setup.py                             # 打包与分发配置
├── .gitignore                           # Git忽略规则
├── LICENSE                              # MIT 许可证文件
└── README.md                            # 项目说明（本文件）
```

## 贡献指南

1. 在 GitHub 上 Fork 本仓库至个人账号，并克隆至本地开发环境。建议在 dev 分支上开展所有修改工作，避免直接操作 main 分支。

2. 安装开发依赖（包含测试与代码检查工具）：执行 `pip install -r requirements-dev.txt`。提交代码前，请运行 `make lint` 和 `make test` 确保代码风格与测试用例均通过。

3. 若需新增功能或修复缺陷，请先查阅 docs/developer-guide/ 下的设计文档，了解核心模块的职责划分。对于较大规模的改动，建议在实施前创建 Issue 进行技术方案讨论。

4. 提交代码时，请遵循 Conventional Commits 规范编写提交信息（如 `feat: add batch import retry mechanism` 或 `fix: correct URL encoding in validator`）。提交前请确保已编写或更新相应的单元测试。

5. 完成开发后，从 dev 分支发起 Pull Request 至本仓库的 main 分支。PR 描述中请清晰说明改动目的、实现方式以及测试覆盖情况。项目维护者将在 3 个工作日内进行 Review。

## 常见问题

**Q: 导入包含大量链接的数据文件时，内存占用过高导致进程被杀死，如何解决？**

A: 当单批次链接数量超过 5000 条时，建议启用分批导入模式。可在 import 命令中添加 `--batch-size 1000` 参数，将数据分块处理。同时，可调整 Python 进程的内存限制（如使用 `ulimit -v` 或 `--max-memory` 选项）。若数据量极大（超过 20000 条），推荐使用 PostgreSQL 等外部数据库替代默认的 JSON 文件存储，本项目在 `docs/operations/external-db.md` 中提供了相关适配方案。

**Q: 健康检查模块对部分内网或需要认证的链接总是报告超时，如何自定义检查策略？**

A: 项目支持通过配置文件 `config/checker.yaml` 定义每类链接的检查参数。对于需要特定 User-Agent 或 Header 的链接，可在数据字段中添加 `check_headers` 和 `check_timeout` 属性，覆盖全局默认值。对于内网无法访问的链接，可将其加入 `whitelist.txt` 跳过检查。详细配置项请参考 `docs/operations/checker-advanced.md`。

**Q: 生成的静态页面在移动设备上显示不友好，是否有响应式布局支持？**

A: 从 v2.1 版本开始，默认模板已集成基于 Flexbox 与 Grid 的响应式样式，适配手机、平板与桌面端。若需进一步调整断点或栅格宽度，可修改 `src/renderer/assets/style.css` 中的 CSS 变量 `--breakpoint-mobile` 与 `--breakpoint-tablet`。若使用自定义模板，建议继承基础布局并重写相关媒体查询区块。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-06-23 23:48:06
