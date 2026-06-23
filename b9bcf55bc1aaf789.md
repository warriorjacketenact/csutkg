# Gzzhly Stream Resource Aggregator

Gzzhly Stream Resource Aggregator 是一个面向技术调研、数据采集和内容聚合场景的高密度外链资源汇总系统。本项目定位于为开发者、数据分析师、SEO 研究人员以及自动化运维工程师提供一套结构化、可扩展的流式资源索引，通过统一的基础域名与短路径模式，将大量分散的外部数据源整合为便于程序化调用的列表形态。

本项目解决的核心痛点在于：当需要从大量固定格式的 URL 中批量获取特定数据片段或监控资源状态时，手工整理和维护链接列表成本极高且容易出错。Gzzhly Stream 通过提供标准化的资源清单、清晰的分类索引以及开箱即用的快速启动脚本，帮助用户在三分钟内建立自己的资源探测或数据拉取任务。

目标用户包括但不限于：使用 Python 或 Shell 进行批量数据抓取的工程师、维护大量外部依赖检查列表的运维人员、需要进行竞品内容监控的产品经理、以及研究网络资源生命周期管理的学术研究者。项目本身不提供具体的业务数据，而是以高质量、高可读性的资源索引为核心资产，并配套完整的工具链说明，让用户能够快速将这些资源纳入自身的业务流程。

## 功能概览

- **统一路径前缀的资源清单**：所有资源均基于 https://www.gzzhly.com/stream/ 这一基础路径，仅通过末尾的三字母或三字符短码区分不同条目，便于进行正则匹配、批量拼接和自动化遍历。

- **批量健康状态检查脚本**：项目内置基于 curl 和 HTTP 状态码的简易探活脚本，可对列表中全部或指定范围的 URL 执行连通性测试，并输出结构化报告。

- **分类标签与元数据扩展支持**：尽管原始 URL 未携带分类信息，项目提供了可选的 metadata.csv 映射机制，用户可根据短码自行标记类型、优先级或所属项目，实现个性化管理。

- **低依赖、高可移植性的运行环境**：仅依赖标准的 POSIX 兼容 Shell 环境与 curl/wget，无需额外安装复杂的运行时或数据库，可在 Linux、macOS 及 Windows WSL 上无缝运行。

- **可编程的 API 模拟端点**：项目提供了一个极简的 Python HTTP 服务器示例，可将资源列表以 JSON 格式对外暴露，方便其他服务或前端界面进行动态查询。

- **自动化报告生成器**：支持将探活结果生成为 Markdown 表格或 CSV 文件，便于存档或发送至监控告警系统。

- **灵活的白名单与黑名单过滤机制**：用户可通过简单的正则表达式配置文件，在运行任务时动态包含或排除特定短码前缀的资源，适配不同业务场景。

- **Docker 容器化交付**：提供官方 Dockerfile，确保在任何支持容器运行的环境中，资源列表和工具链的行为完全一致，消除环境差异带来的干扰。

## 应用场景

**场景一：数据采集管道的初始种子生成**
在构建每日定时抓取任务时，用户需要从固定的数百个数据源拉取页面或 API 响应。本项目的资源列表可作为采集任务的输入种子文件，配合项目提供的批处理框架，可快速构建出第一版数据流水线原型。用户只需实现自己的数据解析逻辑，其余遍历、重试和日志记录均可复用项目基础库。

**场景二：外部服务依赖的可用性监控**
企业内部的监控系统通常需要对外部第三方接口或合作伙伴的页面进行定期探测，以确保服务链路正常。管理员可将本项目的资源列表导入 Prometheus Blackbox Exporter 或自定义监控脚本，针对每个 URL 配置告警规则。当某个短码对应的资源响应异常时，即可触发通知，帮助团队第一时间发现上游故障。

**场景三：SEO 关键词排名与竞品内容变化追踪**
SEO 从业者常常需要跟踪大量页面中的特定关键词密度或结构化数据变更。通过将本项目中的资源链接作为目标池，运维人员可以编写每日差异对比脚本，抓取页面内容后计算哈希值或提取元标签，从而监控页面是否发生重大改动，为搜索引擎排名波动提供数据支撑。

**场景四：学术研究中的网络资源时效性分析**
在网络测量或信息扩散研究领域，学者需要长时间观察一批固定页面的可访问性、内容长度变化或响应头字段。本项目的资源列表提供了现成的观察样本集合，研究者可直接基于列表设计长期追踪实验，无需从零开始搜集分散的 URL。

**场景五：CDN 或边缘节点的性能测试**
由于所有资源均位于同一主域名下，用户可以通过本项目的资源列表模拟对同一站点下不同路径的并发请求，测试本地网络环境到目标服务器的延迟分布和吞吐量表现，辅助决策是否使用特定区域的边缘加速服务。

## 快速开始

以下步骤将帮助您在三分钟内完成项目的克隆、环境准备和首次运行。

```bash
# 第一步：克隆项目仓库到本地
git clone https://github.com/example/gzzhly-stream-aggregator.git
cd gzzhly-stream-aggregator

# 第二步：安装必需的系统工具（若尚未安装）
# 对于 Debian/Ubuntu 系
sudo apt update && sudo apt install -y curl wget jq moreutils

# 对于 RedHat/CentOS 系
sudo yum install -y curl wget jq moreutils

# 第三步：执行快速启动脚本，生成资源清单并测试前 10 个链接
bash scripts/quick_start.sh --limit 10 --output report.md

# 若希望测试全部链接，可执行
bash scripts/full_health_check.sh --parallel 20 --timeout 5 --report csv
```

## 安装要求

本项目对运行环境的要求较低，旨在覆盖绝大多数主流开发与运维机器。具体依赖如下表所示：

| 依赖项 | 必需版本 | 说明 |
| :--- | :--- | :--- |
| Bash | 4.0 及以上 | 用于执行核心管理脚本，macOS 默认 Zsh 可通过 bash 命令调用 |
| curl | 7.58.0 及以上 | 用于发送 HTTP 请求进行健康检查，支持 HTTPS 及重定向跟踪 |
| wget | 1.20.0 及以上 | 备选下载工具，部分脚本提供 wget 作为 curl 的降级方案 |
| Python | 3.6 及以上 | 可选，用于运行 JSON API 模拟服务器和高级数据处理脚本 |
| Docker | 18.09 及以上 | 可选，用于容器化部署，保证环境一致性 |
| jq | 1.5 及以上 | 用于解析和格式化 JSON 输出，增强脚本的链式处理能力 |
| git | 2.20 及以上 | 用于克隆仓库和获取版本更新 |
| coreutils | 8.30 及以上 | 提供基础文件操作命令，如 sort、uniq、xargs 等，通常系统预装 |

## 文档导航

为了帮助不同角色的用户快速找到所需信息，项目文档按照使用层面进行了细致的划分。下表列出了各个文档目录及其核心职责：

| 层面 | 目录 | 回答的问题 |
| :--- | :--- | :--- |
| 用户入门 | docs/getting-started.md | 如何安装、配置和第一次运行健康检查？如何理解输出报告的各项指标？ |
| 运维参考 | docs/operations.md | 如何自定义监控频率？如何集成到 Prometheus 或 Zabbix？如何配置告警阈值？ |
| 开发指南 | docs/development.md | 如何扩展新的资源分类？如何修改 JSON API 的字段结构？如何提交补丁？ |
| 故障排查 | docs/troubleshooting.md | 常见错误码含义、网络超时处理方案、SSL 证书问题解决办法。 |
| 最佳实践 | docs/best-practices.md | 在大规模并行检查时如何控制资源占用？如何避免被目标站点封禁？ |
| 版本日志 | CHANGELOG.md | 每个版本的更新内容、新增功能及向后兼容性说明。 |

## 资源列表

本节按照协议类型与路径特征，将全部原始 URL 分为 HTTPS 主域下的短码资源集合。所有条目均严格保持用户提供的原始格式，未做任何改写或补全。

### 主域短码资源

以下资源均基于 https://www.gzzhly.com/stream/ 前缀，后接三位字符短码：

https://www.gzzhly.com/stream/upl
https://www.gzzhly.com/stream/qoq
https://www.gzzhly.com/stream/yxj
https://www.gzzhly.com/stream/aqi
https://www.gzzhly.com/stream/cnh
https://www.gzzhly.com/stream/tpv
https://www.gzzhly.com/stream/mqt
https://www.gzzhly.com/stream/rzz
https://www.gzzhly.com/stream/ttv
https://www.gzzhly.com/stream/icu
https://www.gzzhly.com/stream/qjg
https://www.gzzhly.com/stream/vpj
https://www.gzzhly.com/stream/qng
https://www.gzzhly.com/stream/ber
https://www.gzzhly.com/stream/yvz
https://www.gzzhly.com/stream/vgt
https://www.gzzhly.com/stream/szh
https://www.gzzhly.com/stream/lwp
https://www.gzzhly.com/stream/ylr
https://www.gzzhly.com/stream/udj
https://www.gzzhly.com/stream/szi
https://www.gzzhly.com/stream/wol
https://www.gzzhly.com/stream/paw
https://www.gzzhly.com/stream/qfw
https://www.gzzhly.com/stream/cvv
https://www.gzzhly.com/stream/xai
https://www.gzzhly.com/stream/fsf
https://www.gzzhly.com/stream/qla
https://www.gzzhly.com/stream/lqt
https://www.gzzhly.com/stream/cfw
https://www.gzzhly.com/stream/dbb
https://www.gzzhly.com/stream/drr
https://www.gzzhly.com/stream/suw
https://www.gzzhly.com/stream/qlq
https://www.gzzhly.com/stream/nip
https://www.gzzhly.com/stream/zab
https://www.gzzhly.com/stream/mtq
https://www.gzzhly.com/stream/yjn
https://www.gzzhly.com/stream/dvu
https://www.gzzhly.com/stream/tra
https://www.gzzhly.com/stream/uwy
https://www.gzzhly.com/stream/gwn
https://www.gzzhly.com/stream/wgw
https://www.gzzhly.com/stream/qpz
https://www.gzzhly.com/stream/nxi
https://www.gzzhly.com/stream/job
https://www.gzzhly.com/stream/pdn
https://www.gzzhly.com/stream/krp
https://www.gzzhly.com/stream/oer
https://www.gzzhly.com/stream/wgd
https://www.gzzhly.com/stream/eai
https://www.gzzhly.com/stream/fin
https://www.gzzhly.com/stream/vjs
https://www.gzzhly.com/stream/wry
https://www.gzzhly.com/stream/ngt
https://www.gzzhly.com/stream/uqa
https://www.gzzhly.com/stream/cvp
https://www.gzzhly.com/stream/cab
https://www.gzzhly.com/stream/iqe
https://www.gzzhly.com/stream/fqw
https://www.gzzhly.com/stream/oed
https://www.gzzhly.com/stream/gzc
https://www.gzzhly.com/stream/ega
https://www.gzzhly.com/stream/jpx
https://www.gzzhly.com/stream/oxv
https://www.gzzhly.com/stream/ynm
https://www.gzzhly.com/stream/jim
https://www.gzzhly.com/stream/osx
https://www.gzzhly.com/stream/mrv
https://www.gzzhly.com/stream/sqy
https://www.gzzhly.com/stream/btd
https://www.gzzhly.com/stream/ver
https://www.gzzhly.com/stream/oxb
https://www.gzzhly.com/stream/fgj
https://www.gzzhly.com/stream/dcw
https://www.gzzhly.com/stream/xmq
https://www.gzzhly.com/stream/ads
https://www.gzzhly.com/stream/ymx
https://www.gzzhly.com/stream/cqh
https://www.gzzhly.com/stream/oxe
https://www.gzzhly.com/stream/aim
https://www.gzzhly.com/stream/fuz
https://www.gzzhly.com/stream/dse
https://www.gzzhly.com/stream/xhf
https://www.gzzhly.com/stream/qgc
https://www.gzzhly.com/stream/awe
https://www.gzzhly.com/stream/ail
https://www.gzzhly.com/stream/rei
https://www.gzzhly.com/stream/mvf
https://www.gzzhly.com/stream/zui
https://www.gzzhly.com/stream/wrc
https://www.gzzhly.com/stream/chf
https://www.gzzhly.com/stream/wbl
https://www.gzzhly.com/stream/sdm
https://www.gzzhly.com/stream/crd
https://www.gzzhly.com/stream/lhy
https://www.gzzhly.com/stream/pbc
https://www.gzzhly.com/stream/qey
https://www.gzzhly.com/stream/xsj
https://www.gzzhly.com/stream/fbi
https://www.gzzhly.com/stream/llo
https://www.gzzhly.com/stream/omj
https://www.gzzhly.com/stream/gxa
https://www.gzzhly.com/stream/knj
https://www.gzzhly.com/stream/npu
https://www.gzzhly.com/stream/udk
https://www.gzzhly.com/stream/pqj
https://www.gzzhly.com/stream/eae
https://www.gzzhly.com/stream/jkf
https://www.gzzhly.com/stream/rrr
https://www.gzzhly.com/stream/owk
https://www.gzzhly.com/stream/cbf
https://www.gzzhly.com/stream/aqd
https://www.gzzhly.com/stream/nwg
https://www.gzzhly.com/stream/rth
https://www.gzzhly.com/stream/owp
https://www.gzzhly.com/stream/qfx
https://www.gzzhly.com/stream/vtr
https://www.gzzhly.com/stream/spk
https://www.gzzhly.com/stream/fsj
https://www.gzzhly.com/stream/ore
https://www.gzzhly.com/stream/tmu
https://www.gzzhly.com/stream/fzl
https://www.gzzhly.com/stream/pyr
https://www.gzzhly.com/stream/xws
https://www.gzzhly.com/stream/egi
https://www.gzzhly.com/stream/hiz
https://www.gzzhly.com/stream/lnv
https://www.gzzhly.com/stream/jll
https://www.gzzhly.com/stream/ttp
https://www.gzzhly.com/stream/tjq
https://www.gzzhly.com/stream/zua
https://www.gzzhly.com/stream/qvy
https://www.gzzhly.com/stream/btz
https://www.gzzhly.com/stream/gsi
https://www.gzzhly.com/stream/xsl
https://www.gzzhly.com/stream/nci
https://www.gzzhly.com/stream/rtt
https://www.gzzhly.com/stream/rsb
https://www.gzzhly.com/stream/zet
https://www.gzzhly.com/stream/edf
https://www.gzzhly.com/stream/ihl
https://www.gzzhly.com/stream/czq
https://www.gzzhly.com/stream/rom
https://www.gzzhly.com/stream/stm
https://www.gzzhly.com/stream/vug
https://www.gzzhly.com/stream/oto
https://www.gzzhly.com/stream/gff
https://www.gzzhly.com/stream/aez
https://www.gzzhly.com/stream/vym
https://www.gzzhly.com/stream/wzj
https://www.gzzhly.com/stream/tbr
https://www.gzzhly.com/stream/ssc
https://www.gzzhly.com/stream/rkq
https://www.gzzhly.com/stream/iqr
https://www.gzzhly.com/stream/zzb
https://www.gzzhly.com/stream/gpv
https://www.gzzhly.com/stream/acr
https://www.gzzhly.com/stream/bxu
https://www.gzzhly.com/stream/jvv
https://www.gzzhly.com/stream/frn
https://www.gzzhly.com/stream/yyc
https://www.gzzhly.com/stream/jac
https://www.gzzhly.com/stream/uny
https://www.gzzhly.com/stream/omw
https://www.gzzhly.com/stream/ebl
https://www.gzzhly.com/stream/ajp
https://www.gzzhly.com/stream/yvu
https://www.gzzhly.com/stream/cct
https://www.gzzhly.com/stream/vdl
https://www.gzzhly.com/stream/bby
https://www.gzzhly.com/stream/qbx
https://www.gzzhly.com/stream/ccp
https://www.gzzhly.com/stream/xpt
https://www.gzzhly.com/stream/vjj
https://www.gzzhly.com/stream/qkl
https://www.gzzhly.com/stream/rca
https://www.gzzhly.com/stream/hhl
https://www.gzzhly.com/stream/xef
https://www.gzzhly.com/stream/rva
https://www.gzzhly.com/stream/ajf
https://www.gzzhly.com/stream/dif
https://www.gzzhly.com/stream/hrd
https://www.gzzhly.com/stream/tkl
https://www.gzzhly.com/stream/tad
https://www.gzzhly.com/stream/wzz
https://www.gzzhly.com/stream/vtt
https://www.gzzhly.com/stream/rau
https://www.gzzhly.com/stream/yoe
https://www.gzzhly.com/stream/rsc
https://www.gzzhly.com/stream/kdv
https://www.gzzhly.com/stream/qux
https://www.gzzhly.com/stream/jqd
https://www.gzzhly.com/stream/qtx
https://www.gzzhly.com/stream/auj
https://www.gzzhly.com/stream/fmk
https://www.gzzhly.com/stream/vwa
https://www.gzzhly.com/stream/rbz
https://www.gzzhly.com/stream/tci
https://www.gzzhly.com/stream/mhn
https://www.gzzhly.com/stream/vun
https://www.gzzhly.com/stream/iao
https://www.gzzhly.com/stream/cbb
https://www.gzzhly.com/stream/ipz
https://www.gzzhly.com/stream/jjo
https://www.gzzhly.com/stream/mka
https://www.gzzhly.com/stream/yrb
https://www.gzzhly.com/stream/oyu
https://www.gzzhly.com/stream/roe
https://www.gzzhly.com/stream/onn
https://www.gzzhly.com/stream/rfw
https://www.gzzhly.com/stream/qrh
https://www.gzzhly.com/stream/ive
https://www.gzzhly.com/stream/jow
https://www.gzzhly.com/stream/ljr
https://www.gzzhly.com/stream/dgq
https://www.gzzhly.com/stream/sdt
https://www.gzzhly.com/stream/hux
https://www.gzzhly.com/stream/mau
https://www.gzzhly.com/stream/zxd
https://www.gzzhly.com/stream/xih
https://www.gzzhly.com/stream/fxu
https://www.gzzhly.com/stream/wbg
https://www.gzzhly.com/stream/uxl
https://www.gzzhly.com/stream/fei
https://www.gzzhly.com/stream/hwq
https://www.gzzhly.com/stream/ost
https://www.gzzhly.com/stream/juo
https://www.gzzhly.com/stream/zdr
https://www.gzzhly.com/stream/fes
https://www.gzzhly.com/stream/vau
https://www.gzzhly.com/stream/zbm
https://www.gzzhly.com/stream/ahy
https://www.gzzhly.com/stream/ygj
https://www.gzzhly.com/stream/opl
https://www.gzzhly.com/stream/htj
https://www.gzzhly.com/stream/ogw
https://www.gzzhly.com/stream/dmv
https://www.gzzhly.com/stream/lvq
https://www.gzzhly.com/stream/rqd
https://www.gzzhly.com/stream/qzb
https://www.gzzhly.com/stream/elb
https://www.gzzhly.com/stream/qqz
https://www.gzzhly.com/stream/xym
https://www.gzzhly.com/stream/drs
https://www.gzzhly.com/stream/wew
https://www.gzzhly.com/stream/zbt
https://www.gzzhly.com/stream/fuf
https://www.gzzhly.com/stream/hri
https://www.gzzhly.com/stream/bao

## 项目结构

项目采用标准化的目录布局，兼顾脚本的易用性与模块的可维护性。以下为完整的 ASCII 目录树及每个部分的职责说明：

```
gzzhly-stream-aggregator/
├── bin/                                 # 可执行脚本入口，加入 PATH 后可直接调用
│   ├── gzz-check                        # 主健康检查入口，支持 --limit 和 --format
│   └── gzz-server                       # 启动 JSON API 服务，默认监听 8080 端口
├── scripts/                             # 核心功能脚本，供 bin 和用户直接调用
│   ├── quick_start.sh                   # 首次运行向导，生成基础报告
│   ├── full_health_check.sh             # 全量并发检查，含重试与超时控制
│   ├── report_generator.py              # 将原始结果转换为 Markdown/CSV/JSON
│   └── filter_engine.sh                 # 基于正则表达式的黑白名单过滤实现
├── conf/                                # 配置文件目录，用户可按需修改
│   ├── resources.lst                    # 纯文本资源列表，每行一个短码
│   ├── filter_whitelist.conf            # 白名单正则，一行一个模式
│   ├── filter_blacklist.conf            # 黑名单正则，优先级高于白名单
│   └── logging.yml                      # 日志级别、输出路径及轮转策略配置
├── data/                                # 运行时生成的数据与报告存储目录
│   ├── archive/                         # 历史报告归档，按 YYYY-MM-DD 存放
│   ├── current_report.json              # 最近一次全量检查的原始 JSON 结果
│   └── current_report.md                # 最近一次检查的人类可读 Markdown 报告
├── docs/                                # 项目文档，涵盖用户与开发者手册
│   ├── getting-started.md               # 快速入门指南
│   ├── operations.md                    # 运维与监控集成说明
│   ├── development.md                   # 扩展开发与二次定制指南
│   ├── troubleshooting.md               # 常见故障诊断与解决方案
│   └── best-practices.md                # 性能调优与防封禁策略
├── docker/                              # 容器化相关文件
│   ├── Dockerfile                       # 基于 Alpine Linux 的轻量镜像构建文件
│   └── docker-compose.yml               # 编排服务，含健康检查与日志收集侧车
├── tests/                               # 单元测试与集成测试套件
│   ├── test_checker.sh                  # 对核心检查函数的 Bats 测试用例
│   ├── test_filter.sh                   # 过滤逻辑的边界条件测试
│   └── fixtures/                        # 测试用的模拟响应与预期输出
├── .github/                             # GitHub Actions 工作流配置
│   └── workflows/
│       ├── ci.yml                       # 提交时自动运行测试与 lint
│       └── nightly.yml                  # 每日定时执行全量资源检查，生成快照
├── Makefile                             # 统一构建入口，支持 install、test、clean
├── README.md                            # 项目总览与核心文档入口（即本文件）
└── LICENSE                              # MIT 许可证全文
```

## 贡献指南

我们欢迎并鼓励社区成员为本项目贡献代码、文档或新的资源分类建议。请遵循以下流程以保证协作的顺畅与代码质量的稳定：

1.  **报告问题或建议**：首先在 GitHub Issues 中搜索是否已有类似话题。若没有，请新建一个 Issue，使用我们提供的模板详细描述您遇到的问题或期望的新特性，并附上可复现的步骤或场景示例。

2.  **派生项目并创建特性分支**：从主仓库的主分支（main）派生一份代码到您的个人账户下，然后在本地切换到新分支，分支命名建议使用 feature/xxx 或 fix/xxx 格式，例如 feature/add-timeout-config。

3.  **编写或修改代码，并补充测试**：所有的逻辑变更或新功能都需要包含对应的测试用例，确保 tests/ 目录下的相关套件通过。同时，请更新 docs/ 目录下受影响的文档，保证文档与实际行为一致。

4.  **提交前执行自检**：在本地运行 make test 和 make lint，确保所有检查通过且无格式化警告。若项目尚未配置自动化 lint，请人工检查缩进、变量命名和注释风格是否符合现有代码范式。

5.  **发起拉取请求**：将您的分支推送到 GitHub 后，在主仓库中发起 Pull Request。在描述中关联对应的 Issue 编号，并简要说明改动内容、测试结果以及是否影响向后兼容性。维护者将在三个工作日内进行审阅，并可能提出修改意见。

## 常见问题

**问：健康检查脚本出现大量超时错误，该如何调整？**

答：超时错误通常由网络环境不稳定或目标服务器响应缓慢引起。您可以通过修改 scripts/full_health_check.sh 脚本顶部的 TIMEOUT 变量（默认 5 秒）来增加等待时间，例如调整为 10 秒。同时，建议降低并行度，将 --parallel 参数从 20 调整为 5 或 10，以减少本地网络连接的并发压力。若问题持续存在，请检查本地防火墙或代理设置，确保 curl 能够正常访问外网。

**问：如何只检查资源列表中的部分链接，而不是全部？**

答：项目提供了多种过滤方式。最直接的是使用 quick_start.sh 的 --limit 参数，例如 --limit 50 将只处理前 50 个短码。若需要跳过特定前缀，可在 conf/filter_blacklist.conf 中添加一行正则表达式，如 ^(bad|test).*，脚本运行时会自动忽略匹配的条目。此外，您也可以直接编辑 conf/resources.lst 文件，注释掉不需要的行（行首加 #），但请注意这会影响所有脚本的默认行为。

**问：项目是否支持 Windows 原生环境（非 WSL）运行？**

答：本项目核心脚本基于 Bash 和 POSIX 工具链，因此原生 Windows（cmd 或 PowerShell）无法直接运行。推荐使用 Windows Subsystem for Linux (WSL) 安装 Ubuntu 或 Debian 发行版，在该环境中执行所有命令。或者，您也可以使用 Docker for Windows 拉取项目镜像，在容器内运行检查任务，从而完全绕过操作系统差异。我们暂不提供 PowerShell 或 Batch 版本的原生脚本，但欢迎社区贡献相关移植。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-06-23 23:54:42
