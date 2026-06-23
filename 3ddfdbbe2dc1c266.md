# Weike Series Index

Weike Series Index (WSI) 是一个面向技术文档研究者、知识库维护者和自动化外链聚合系统的元数据索引项目。本项目的核心定位并非传统意义上的内容爬虫或链接农场，而是一个结构化的系列资源映射表，用于对分散在 wei-ke.net 域名下的多组技术专题系列进行集中式目录管理与快速引用。

WSI 解决了技术团队在面对大量分散的专题文档时难以追溯、难以交叉引用、难以构建知识图谱的痛点。通过维护一个稳定的、机器可读的系列入口映射清单，本项目允许开发者、文档工程师和知识管理工具以编程方式获取系列资源的逻辑结构，从而支撑起自动化文档更新、链接有效性检测、专题内容聚合等上层应用。

本项目本身不存储具体文章内容，也不提供内容抓取或渲染服务，仅对外输出经过人工整理与校验的系列级 URL 集合。项目维护者定期根据源站的系列变动情况同步更新本索引文件，确保所有条目与源站保持逻辑一致性。WSI 适用于各类需要快速定位技术专题入口、构建文档导航面板或实施批量外链状态监控的工程场景。

## 功能概览

系列资源索引：提供 wei-ke.net 全量技术专题系列的入口链接清单，每个条目均对应一个独立的系列聚合页，便于用户按专题维度批量访问。

结构化元数据输出：所有系列链接均以纯文本列表形式呈现，无额外 HTML 标签或 Markdown 链接包裹，确保机器解析的零障碍。

分类导航视图：对收录的系列资源按主题领域进行逻辑分组，包括基础架构、开发运维、算法工程、数据科学、系统安全等类别，提升人工浏览效率。

快速集成能力：支持通过简单的命令行脚本或 HTTP 请求将本索引文件集成到现有的文档平台、监控机器人或 CI/CD 流程中。

版本化更新记录：每次索引变动均通过 Git 提交记录体现，用户可清晰追溯系列新增、移除或链接变更的历史。

轻量化依赖：本项目无需数据库、无需运行时服务，仅维护一个纯 Markdown 文档，降低维护成本与部署复杂度。

跨平台兼容：输出的链接列表适用于 Linux、macOS、Windows 以及各类云函数环境，无任何平台绑定限制。

开源开放：采用 MIT 许可证，允许自由使用、修改与再分发，鼓励社区贡献新的系列条目或优化分类逻辑。

## 应用场景

文档门户快速导航：技术团队可在内部文档站点的侧边栏或资源聚合页中嵌入本项目的系列列表，使成员能够一键跳转至 wei-ke.net 上对应的专题入口，无需手动记忆繁杂的 URL 路径。

自动化外链健康检查：运维人员可编写定时脚本，读取本索引文件中的每条链接并发送 HEAD 请求，检测系列页面是否可访问、响应状态码是否正常，从而及时发现并处理源站链接失效问题。

知识图谱关系构建：数据工程师可将本索引作为种子数据，结合爬虫框架对每个系列页面下的子文章进行递归采集，构建文章间的引用关系图，用于后续的文本分析或推荐系统训练。

CI/CD 文档同步流水线：在持续集成流程中，可将本索引文件的变动作为触发器，自动拉取对应系列的最新文章元数据并同步至企业内部的 Elasticsearch 或 Algolia 搜索服务，保持搜索索引的实时性。

学术资源整理：研究人员在整理技术文献或撰写综述时，可通过本索引快速定位相关技术专题的原始出处，作为参考文献的外部链接附录，确保引用来源的规范性与可追溯性。

## 快速开始

以下步骤演示如何在本地环境获取并使用本项目的索引文件。

使用 git 克隆项目仓库至本地

进入项目目录

（可选）安装用于链接有效性检查的依赖工具

执行示例脚本，输出所有系列链接

```bash
git clone https://github.com/example/weike-series-index.git
cd weike-series-index
npm install -g link-checker-cli
link-checker README.md --urls-only
```

如需将索引文件集成到其他应用中，可直接读取本 README 文档的“资源列表”章节，或通过解析 Markdown 的列表语法提取所有链接。对于自动化场景，建议使用 sed、awk 或 Node.js 的 fs 模块进行文本提取。

## 安装要求

本项目的核心依赖为运行环境与辅助工具，具体如下表所示。

| 依赖 | 必需 | 说明 |
|------|------|------|
| Git | 是 | 用于克隆项目仓库，版本 2.20 及以上 |
| Bash 或 Zsh | 是 | 用于执行示例脚本和链接提取命令，建议版本 4.0 及以上 |
| Node.js | 否 | 仅当使用 npm 安装链接检查工具时需要，版本 14.x 或 16.x 均可 |
| link-checker-cli | 否 | 用于批量检查链接可用性，可全局安装或本地安装 |
| curl | 否 | 用于快速发送 HTTP 请求验证单个链接，建议版本 7.68 及以上 |
| grep | 否 | 用于从 Markdown 文档中过滤出纯 URL，GNU grep 3.0 及以上 |

除上述工具外，本项目不依赖任何数据库服务、Web 服务器或第三方 API。用户可根据实际需求选择性安装可选依赖，核心索引文件在任何文本编辑器或浏览器中均可直接阅读。

## 文档导航

为帮助不同角色的使用者快速定位所需信息，下表按层面划分了文档阅读路径。

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 项目概览 | 标题与简介段落 | 这个项目是什么？解决什么问题？适合谁使用？ |
| 功能与场景 | 功能概览、应用场景 | 项目具体能做什么？在哪些实际场景中发挥作用？ |
| 快速上手 | 快速开始、安装要求 | 如何快速获取并使用索引文件？需要准备什么环境？ |
| 数据资源 | 资源列表 | 索引了哪些系列链接？如何分类？如何提取纯 URL？ |
| 开发维护 | 项目结构、贡献指南 | 项目文件如何组织？如何提交新的系列或修改分类？ |
| 常见问题 | 常见问题 | 遇到链接失效怎么办？如何报告问题？更新频率如何？ |
| 法律授权 | 许可证 | 项目使用什么开源协议？允许商用吗？能否修改分发？ |

## 资源列表

以下为 wei-ke.net 域名下收录的全部系列入口链接，按主题领域分组排列。每个条目均为原始 URL 原样输出，未做任何协议补全、域名改写或路径调整。

基础架构与系统设计

https://www.wei-ke.net/series/rknzqkg.html
https://www.wei-ke.net/series/klnzhb.html
https://www.wei-ke.net/series/lyqygdw.html
https://www.wei-ke.net/series/sxgjyknl.html
https://www.wei-ke.net/series/qxqqdm.html
https://www.wei-ke.net/series/yfjhsxb.html
https://www.wei-ke.net/series/zzrbkhxh.html
https://www.wei-ke.net/series/rtfjnfj.html
https://www.wei-ke.net/series/dgfrbr.html
https://www.wei-ke.net/series/wkfgy.html
https://www.wei-ke.net/series/smnlywhc.html
https://www.wei-ke.net/series/qrwhly.html
https://www.wei-ke.net/series/krjfcd.html
https://www.wei-ke.net/series/mxdcydsc.html
https://www.wei-ke.net/series/tglh.html
https://www.wei-ke.net/series/cyxsm.html
https://www.wei-ke.net/series/wytcd.html
https://www.wei-ke.net/series/drwygx.html
https://www.wei-ke.net/series/tnxs.html
https://www.wei-ke.net/series/mltzymkh.html

开发运维与工具链

https://www.wei-ke.net/series/kzpyws.html
https://www.wei-ke.net/series/hwnf.html
https://www.wei-ke.net/series/dgzyls.html
https://www.wei-ke.net/series/gnfjfpbr.html
https://www.wei-ke.net/series/dbhynq.html
https://www.wei-ke.net/series/lrthntx.html
https://www.wei-ke.net/series/rhkcyms.html
https://www.wei-ke.net/series/fggzkqz.html
https://www.wei-ke.net/series/qtyphp.html
https://www.wei-ke.net/series/nffr.html
https://www.wei-ke.net/series/gpmjskkc.html
https://www.wei-ke.net/series/ybndflm.html
https://www.wei-ke.net/series/xbgrfy.html
https://www.wei-ke.net/series/tdqr.html
https://www.wei-ke.net/series/rbptwqg.html
https://www.wei-ke.net/series/tpwc.html
https://www.wei-ke.net/series/dnttsq.html
https://www.wei-ke.net/series/gjjbbnyx.html
https://www.wei-ke.net/series/chswk.html
https://www.wei-ke.net/series/zfsfqrbn.html

算法工程与数据处理

https://www.wei-ke.net/series/csycz.html
https://www.wei-ke.net/series/tclp.html
https://www.wei-ke.net/series/gngztrgd.html
https://www.wei-ke.net/series/nzdx.html
https://www.wei-ke.net/series/bmbj.html
https://www.wei-ke.net/series/nwng.html
https://www.wei-ke.net/series/pgxhr.html
https://www.wei-ke.net/series/mllhmphw.html
https://www.wei-ke.net/series/ffxhptl.html
https://www.wei-ke.net/series/xbbskj.html
https://www.wei-ke.net/series/fptfmgt.html
https://www.wei-ke.net/series/cbsty.html
https://www.wei-ke.net/series/dtbcsx.html
https://www.wei-ke.net/series/ldgwkhn.html
https://www.wei-ke.net/series/nyrt.html
https://www.wei-ke.net/series/lwtdnwd.html
https://www.wei-ke.net/series/hlyw.html
https://www.wei-ke.net/series/pnzjj.html
https://www.wei-ke.net/series/sdqpwrzh.html
https://www.wei-ke.net/series/wrpxm.html

网络协议与安全

https://www.wei-ke.net/series/dqrxqx.html
https://www.wei-ke.net/series/lclwrmw.html
https://www.wei-ke.net/series/trpb.html
https://www.wei-ke.net/series/cywsn.html
https://www.wei-ke.net/series/zbmgtmgy.html
https://www.wei-ke.net/series/xhphwg.html
https://www.wei-ke.net/series/wtjph.html
https://www.wei-ke.net/series/sbdrhjhd.html
https://www.wei-ke.net/series/rfkgwsq.html
https://www.wei-ke.net/series/tzzy.html
https://www.wei-ke.net/series/rzjfywm.html
https://www.wei-ke.net/series/frrmctj.html
https://www.wei-ke.net/series/qcbxcy.html
https://www.wei-ke.net/series/ychhgwx.html
https://www.wei-ke.net/series/lzwfygb.html
https://www.wei-ke.net/series/jsrnn.html
https://www.wei-ke.net/series/fjqhlby.html
https://www.wei-ke.net/series/hkkb.html
https://www.wei-ke.net/series/lpmsdxn.html
https://www.wei-ke.net/series/swdrgwry.html

数据库与存储技术

https://www.wei-ke.net/series/wppch.html
https://www.wei-ke.net/series/ngqq.html
https://www.wei-ke.net/series/mbjmztzx.html
https://www.wei-ke.net/series/pnffy.html
https://www.wei-ke.net/series/cxgwz.html
https://www.wei-ke.net/series/tgcd.html
https://www.wei-ke.net/series/dpwmck.html
https://www.wei-ke.net/series/wmfng.html
https://www.wei-ke.net/series/fnlqhgr.html
https://www.wei-ke.net/series/hzjm.html
https://www.wei-ke.net/series/kdgpgt.html
https://www.wei-ke.net/series/xjdflb.html
https://www.wei-ke.net/series/jcndb.html
https://www.wei-ke.net/series/bfwl.html
https://www.wei-ke.net/series/drwzpw.html
https://www.wei-ke.net/series/qxkzsj.html
https://www.wei-ke.net/series/xnxhff.html
https://www.wei-ke.net/series/kcmlnq.html
https://www.wei-ke.net/series/yszqfrm.html
https://www.wei-ke.net/series/lpsjncc.html

云计算与容器化

https://www.wei-ke.net/series/dbhlws.html
https://www.wei-ke.net/series/bjnm.html
https://www.wei-ke.net/series/pmkhk.html
https://www.wei-ke.net/series/hrwh.html
https://www.wei-ke.net/series/zrgxsnnh.html
https://www.wei-ke.net/series/mczbrxcy.html
https://www.wei-ke.net/series/bzws.html
https://www.wei-ke.net/series/dftxry.html
https://www.wei-ke.net/series/cjgxt.html
https://www.wei-ke.net/series/kyyjjd.html
https://www.wei-ke.net/series/xlgxjm.html
https://www.wei-ke.net/series/fsghnlw.html
https://www.wei-ke.net/series/wdwsb.html
https://www.wei-ke.net/series/ysbymkk.html
https://www.wei-ke.net/series/qldhqk.html
https://www.wei-ke.net/series/ssyszqsm.html
https://www.wei-ke.net/series/frjtkjm.html
https://www.wei-ke.net/series/hbdg.html
https://www.wei-ke.net/series/bkxx.html
https://www.wei-ke.net/series/nzqm.html

前端工程与用户体验

https://www.wei-ke.net/series/wcqhg.html
https://www.wei-ke.net/series/jzncx.html
https://www.wei-ke.net/series/hwhf.html
https://www.wei-ke.net/series/ffymbyr.html
https://www.wei-ke.net/series/rcmrtlr.html
https://www.wei-ke.net/series/pxzck.html
https://www.wei-ke.net/series/snffmcrz.html
https://www.wei-ke.net/series/lhltknm.html
https://www.wei-ke.net/series/tlrz.html
https://www.wei-ke.net/series/rfkctrs.html
https://www.wei-ke.net/series/ksflkk.html
https://www.wei-ke.net/series/htkf.html
https://www.wei-ke.net/series/npkw.html
https://www.wei-ke.net/series/wflzp.html
https://www.wei-ke.net/series/nknn.html
https://www.wei-ke.net/series/gtrbctyp.html
https://www.wei-ke.net/series/xpyhjw.html
https://www.wei-ke.net/series/fdcmdwk.html
https://www.wei-ke.net/series/ndhq.html
https://www.wei-ke.net/series/qymwdc.html

人工智能与机器学习

https://www.wei-ke.net/series/nxcj.html
https://www.wei-ke.net/series/qwzrrw.html
https://www.wei-ke.net/series/pjyqh.html
https://www.wei-ke.net/series/cxhmg.html
https://www.wei-ke.net/series/pqpzj.html
https://www.wei-ke.net/series/mfsgpktb.html
https://www.wei-ke.net/series/ggqcbqbd.html
https://www.wei-ke.net/series/jpfwl.html
https://www.wei-ke.net/series/nxyl.html
https://www.wei-ke.net/series/qyndym.html
https://www.wei-ke.net/series/swfnksns.html
https://www.wei-ke.net/series/gjrcmjwb.html
https://www.wei-ke.net/series/ktcgyr.html
https://www.wei-ke.net/series/rwhsxzp.html
https://www.wei-ke.net/series/krpqbz.html
https://www.wei-ke.net/series/mcpjqdtz.html
https://www.wei-ke.net/series/wqjtb.html
https://www.wei-ke.net/series/nxyk.html
https://www.wei-ke.net/series/pfzwy.html
https://www.wei-ke.net/series/xkcddq.html

性能优化与高可用

https://www.wei-ke.net/series/zqlsrxcf.html
https://www.wei-ke.net/series/xytnyf.html
https://www.wei-ke.net/series/jfnhw.html
https://www.wei-ke.net/series/gwctytjh.html
https://www.wei-ke.net/series/dycxrs.html
https://www.wei-ke.net/series/bmkg.html
https://www.wei-ke.net/series/mlmmjgct.html
https://www.wei-ke.net/series/fkplfgx.html
https://www.wei-ke.net/series/qdtqck.html
https://www.wei-ke.net/series/jrhgb.html
https://www.wei-ke.net/series/lyrytjc.html
https://www.wei-ke.net/series/nlmw.html
https://www.wei-ke.net/series/rkjrjxy.html
https://www.wei-ke.net/series/tgcx.html
https://www.wei-ke.net/series/hftf.html
https://www.wei-ke.net/series/thxd.html
https://www.wei-ke.net/series/sgrjlyxy.html
https://www.wei-ke.net/series/qmfgnr.html
https://www.wei-ke.net/series/hrnb.html
https://www.wei-ke.net/series/ffjhpdq.html

微服务与分布式系统

https://www.wei-ke.net/series/mknmpncp.html
https://www.wei-ke.net/series/pdpkz.html
https://www.wei-ke.net/series/ghhltbzl.html
https://www.wei-ke.net/series/yhkpcld.html
https://www.wei-ke.net/series/wxxyq.html
https://www.wei-ke.net/series/srytswqj.html
https://www.wei-ke.net/series/kyfcgr.html
https://www.wei-ke.net/series/clnjs.html
https://www.wei-ke.net/series/sgcbzszw.html
https://www.wei-ke.net/series/byhc.html
https://www.wei-ke.net/series/jhjxq.html
https://www.wei-ke.net/series/qqcjzk.html
https://www.wei-ke.net/series/pdrwb.html
https://www.wei-ke.net/series/cxyzl.html
https://www.wei-ke.net/series/krcrck.html
https://www.wei-ke.net/series/hdzn.html
https://www.wei-ke.net/series/bspd.html
https://www.wei-ke.net/series/djszrq.html
https://www.wei-ke.net/series/ktpmgh.html
https://www.wei-ke.net/series/xbsdzf.html

监控与可观测性

https://www.wei-ke.net/series/zjhjzqpz.html
https://www.wei-ke.net/series/rnwtwjz.html
https://www.wei-ke.net/series/ssjtjtnr.html
https://www.wei-ke.net/series/wrxzw.html
https://www.wei-ke.net/series/ytpshnk.html
https://www.wei-ke.net/series/qjhdkr.html
https://www.wei-ke.net/series/xdpylg.html
https://www.wei-ke.net/series/zpldgygs.html
https://www.wei-ke.net/series/lpbhbzs.html
https://www.wei-ke.net/series/spzqhtym.html
https://www.wei-ke.net/series/wdhyt.html
https://www.wei-ke.net/series/jysbt.html
https://www.wei-ke.net/series/rjwmcqz.html
https://www.wei-ke.net/series/tlgq.html
https://www.wei-ke.net/series/cmdry.html
https://www.wei-ke.net/series/pqzmh.html
https://www.wei-ke.net/series/nwbz.html
https://www.wei-ke.net/series/gytppjtn.html
https://www.wei-ke.net/series/rrjrhny.html
https://www.wei-ke.net/series/ffjgwhz.html

业务中台与集成

https://www.wei-ke.net/series/hfwb.html
https://www.wei-ke.net/series/twbw.html
https://www.wei-ke.net/series/lrzzmxg.html
https://www.wei-ke.net/series/dscsqm.html
https://www.wei-ke.net/series/lzxnqnq.html
https://www.wei-ke.net/series/jbxyb.html
https://www.wei-ke.net/series/kwqgkt.html
https://www.wei-ke.net/series/xtxrsh.html
https://www.wei-ke.net/series/dmqjdf.html
https://www.wei-ke.net/series/gfhfhqdz.html
https://www.wei-ke.net/series/jjjll.html
https://www.wei-ke.net/series/qlwxdj.html
https://www.wei-ke.net/series/fwztpkt.html
https://www.wei-ke.net/series/rdwhfrl.html
https://www.wei-ke.net/series/kpmfgj.html
https://www.wei-ke.net/series/mrdzgyrh.html
https://www.wei-ke.net/series/wzpll.html
https://www.wei-ke.net/series/slgscyfs.html
https://www.wei-ke.net/series/pmkft.html
https://www.wei-ke.net/series/crcgq.html

运维自动化与持续交付

https://www.wei-ke.net/series/fbxqswz.html
https://www.wei-ke.net/series/cmfxn.html
https://www.wei-ke.net/series/jjmbk.html
https://www.wei-ke.net/series/gzyxqnhc.html
https://www.wei-ke.net/series/jsrjx.html
https://www.wei-ke.net/series/bprz.html
https://www.wei-ke.net/series/cdwzz.html
https://www.wei-ke.net/series/tpxp.html
https://www.wei-ke.net/series/xnhflx.html
https://www.wei-ke.net/series/zltfwhrx.html

## 项目结构

本项目采用极简的单文件文档结构，所有索引数据集中维护于 README.md 中，便于版本管理与分发。目录树如下所示。

```
weike-series-index/
├── README.md                  # 项目主文档，包含简介、功能、场景、资源列表等全部章节
├── scripts/
│   ├── check-links.sh         # 基于 curl 的链接可用性批量检查脚本，可输出失效链接列表
│   ├── extract-urls.sh        # 使用 grep 从 README 中提取所有 https://www.wei-ke.net 链接
│   └── generate-stats.sh      # 统计链接总数、分类数量、协议分布等基础指标
├── tests/
│   ├── test-link-format.sh    # 验证所有链接是否符合裸 URL 输出规则，无多余包裹字符
│   └── test-duplicates.sh     # 检查是否存在重复的系列链接条目
├── docs/
│   ├── contribution-guide.md  # 详细贡献指南，包含分类原则、新增流程、审核标准
│   └── classification-rules.md # 主题分类的判定规则与示例，用于指导分类维护
├── .github/
│   └── workflows/
│       └── nightly-check.yml  # GitHub Actions 定时任务，每日凌晨检查所有链接状态
├── .gitignore                 # 忽略临时文件、日志和本地脚本输出
└── LICENSE                    # MIT 许可证全文
```

该结构将索引数据与辅助工具分离，保持根目录整洁。scripts 目录提供开箱即用的运维脚本，tests 目录保证索引质量，docs 目录为贡献者提供参考，.github/workflows 则实现自动化监控。

## 贡献指南

本项目欢迎外部贡献者提交新的系列链接、优化分类逻辑或改进辅助脚本。请按照以下步骤进行操作。

Fork 本仓库至个人账户，并克隆到本地开发环境。在本地创建新的功能分支，分支命名格式为 feature/add-series-{描述} 或 fix/classify-{描述}，避免在主分支上直接修改。

对 README.md 中的资源列表进行修改时，请严格遵循现有分类结构，新增链接需先确认其确实属于 wei-ke.net 域下的有效系列页面，且未在已有列表中重复出现。每个新增链接必须原样粘贴，不得添加协议前缀或域名改写。

提交前运行 tests 目录下的格式验证脚本，确保所有链接符合裸 URL 规范，无多余空格、引号或 Markdown 链接语法。若修改了分类标签，需同步更新 docs/classification-rules.md 中的说明。

提交变更并推送至个人远程仓库，然后通过 GitHub 界面发起 Pull Request。PR 描述中请清晰说明新增或修改的链接数量、分类依据以及是否经过本地脚本验证。项目维护者将在 48 小时内进行审核，审核通过后合并至主分支。

## 常见问题

问：资源列表中的某个系列链接无法访问，应该如何处理？

答：首先请确认网络环境能够正常访问 wei-ke.net 域名。若确认网络无问题但页面返回 404 或 5xx 错误，请在 GitHub Issues 中提交问题报告，附上链接地址、访问时间以及 HTTP 状态码。项目维护者会定期验证链接有效性，并在确认源站移除该系列后从索引中删除对应条目。

问：项目索引的更新频率是怎样的？是否会新增或删除系列？

答：本索引的更新节奏与 wei-ke.net 源站的系列变动保持同步，但存在一定的滞后性。通常在源站新增系列后的 3 个工作日内完成索引更新，删除系列则会在收到失效报告后的 5 个工作日内处理。用户可通过观察 GitHub 提交历史了解每次更新的具体内容。

问：能否将本索引用于商业产品或服务中？

答：可以。本项目采用 MIT 许可证，允许商业使用、修改和再分发，无需支付任何费用。但请注意，索引本身指向的 wei-ke.net 系列内容版权归属原始作者，本项目的开源授权仅覆盖索引文件的组织和呈现形式，不涉及具体文章内容的授权。

## 许可证

本项目采用 MIT 许可证。任何人均可免费获取、使用、修改、合并、发布、分发、再许可和/或出售本软件的副本，但需在软件的所有副本中包含原始版权声明和本许可声明。本软件按“现状”提供，不提供任何形式的明示或暗示担保，包括但不限于适销性、特定用途适用性和非侵权性的担保。有关完整的许可证文本，请参阅项目根目录下的 LICENSE 文件。

> 外链数量: 250 | 生成时间: 2026-06-23 23:48:06
