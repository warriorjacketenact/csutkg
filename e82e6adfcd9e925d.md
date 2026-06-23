# LinkVault Resource Aggregator

LinkVault is a high-performance, open-source URL resource aggregation and navigation system designed for technical documentation teams, open-source project maintainers, and content curators who need to manage large volumes of external reference links. The platform provides structured indexing, batch import capabilities, and automated link validation for resource collections spanning multiple categories and domains.

Targeting users who handle resource-intensive documentation workflows, LinkVault solves the problem of link rot, disorganized bookmark collections, and inefficient manual curation through a command-line interface and RESTful API that enables programmatic access to curated resource lists. The system supports batch operations, metadata tagging, and export functionality for integration with static site generators and knowledge management platforms.

## 功能概览

**批量资源导入** - 支持从 CSV、JSON 和纯文本格式批量导入 URL 列表，自动去重并识别重复条目。

**链接健康检查** - 定时对存储的 URL 执行 HTTP 状态检测，标记失效链接并生成报告，支持自定义检查间隔。

**分类标签系统** - 为每个资源条目分配多级标签和分类，支持按项目、主题、优先级等多维度筛选查询。

**全文检索功能** - 基于资源标题、描述和标签的轻量级全文搜索，支持模糊匹配和拼音检索。

**RESTful API 接口** - 提供完整的 JSON API 用于资源的增删改查、批量操作和状态查询，便于与其他系统集成。

**数据导出工具** - 支持将资源列表导出为 Markdown 表格、JSON 结构数据或 HTML 导航页面格式。

**访问统计仪表板** - 记录每个资源的访问频次和引用次数，生成热度排行和使用趋势分析。

**命令行交互模式** - 提供交互式 Shell 环境用于快速查询、添加和管理资源，支持管道和重定向操作。

## 应用场景

**开源项目文档站外链接管理** - 技术文档中往往包含大量指向外部依赖、参考文章和工具站点的超链接。LinkVault 可为文档团队提供集中的链接仓库，在文档生成时通过 API 动态拉取链接列表，确保所有外链均经过有效性验证，避免读者遇到 404 页面。

**个人知识库资源索引** - 研究员、技术博主和终身学习者在日常阅读中积累大量书签和参考链接。LinkVault 可作为知识库的补充组件，对收藏的 URL 进行分类标注，配合检索功能快速定位特定主题下的历史资料，提高信息复用效率。

**社区贡献资源汇总** - 开源社区通常需要维护外部资源列表供贡献者参考，包括学习资料、开发工具和同类项目。LinkVault 支持多人协作编辑资源库，通过提交 PR 或 API 调用新增条目，由维护者审核后合并，保持资源列表的更新和权威性。

**自动化测试用例数据源** - 在 Web 应用和爬虫项目的测试流程中，需要大量真实 URL 作为测试输入。LinkVault 可提供可编程的 URL 数据源接口，测试框架在运行时从系统中获取批量链接，用于页面加载测试、响应时间监控和内容抓取验证。

## 快速开始

```bash
# 克隆项目仓库
git clone https://github.com/yourorg/linkvault.git

# 进入项目目录
cd linkvault

# 安装依赖（使用 pip 和 npm）
pip install -r requirements.txt
npm install --prefix frontend

# 初始化数据库
python scripts/init_db.py

# 运行开发服务器
python app.py --host 0.0.0.0 --port 8080
```

## 安装要求

| 依赖 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 及以上 | 核心后端运行环境，提供 API 服务和调度引擎 |
| SQLite / PostgreSQL | SQLite 3.35+ / PostgreSQL 13+ | 主数据存储，生产环境推荐 PostgreSQL |
| Node.js | 18.x LTS | 前端构建工具和开发服务器依赖 |
| npm 或 yarn | 8.x / 1.22+ | 前端包管理器，用于安装 UI 组件库 |
| Redis | 6.0 及以上 | 可选，用于缓存查询结果和任务队列加速 |
| curl 或 wget | 任意版本 | 用于健康检查模块的 HTTP 请求发送 |
| git | 2.30 及以上 | 版本控制，用于克隆仓库和提交贡献 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | docs/user-guide/ | 如何安装配置、导入资源、使用查询和导出功能？ |
| 开发者指南 | docs/developer/ | API 接口规范、插件机制、如何扩展健康检查器？ |
| 运维手册 | docs/operations/ | 如何部署到生产环境、配置日志轮转、监控系统状态？ |
| 设计文档 | docs/design/ | 系统架构图、数据库 ER 模型、数据流与模块划分说明 |

## 资源列表

### 影视资源分类索引

https://www.szeyes.com/index.php/vod/jyhch.html

https://www.szeyes.com/index.php/vod/wgccq.html

https://www.szeyes.com/index.php/vod/tqzq.html

https://www.szeyes.com/index.php/vod/rtczkbz.html

https://www.szeyes.com/index.php/vod/kmmzxq.html

https://www.szeyes.com/index.php/vod/hwhl.html

https://www.szeyes.com/index.php/vod/qscfgj.html

https://www.szeyes.com/index.php/vod/nkcw.html

https://www.szeyes.com/index.php/vod/zjppthzn.html

https://www.szeyes.com/index.php/vod/rrlrwwm.html

https://www.szeyes.com/index.php/vod/fqplbtd.html

https://www.szeyes.com/index.php/vod/xcxpby.html

https://www.szeyes.com/index.php/vod/sbndbrbp.html

https://www.szeyes.com/index.php/vod/wljff.html

https://www.szeyes.com/index.php/vod/jmckw.html

https://www.szeyes.com/index.php/vod/lnslpqn.html

https://www.szeyes.com/index.php/vod/mxhbrtmf.html

https://www.szeyes.com/index.php/vod/fkyyrcy.html

https://www.szeyes.com/index.php/vod/xchbbd.html

https://www.szeyes.com/index.php/vod/tcqm.html

https://www.szeyes.com/index.php/vod/mktxlmqz.html

https://www.szeyes.com/index.php/vod/tdyl.html

https://www.szeyes.com/index.php/vod/bcqm.html

https://www.szeyes.com/index.php/vod/nssy.html

https://www.szeyes.com/index.php/vod/qgllpj.html

https://www.szeyes.com/index.php/vod/njzw.html

https://www.szeyes.com/index.php/vod/zmzbgsjd.html

https://www.szeyes.com/index.php/vod/rmfhhty.html

https://www.szeyes.com/index.php/vod/ltrkmtk.html

https://www.szeyes.com/index.php/vod/nbgg.html

https://www.szeyes.com/index.php/vod/qhrfyk.html

https://www.szeyes.com/index.php/vod/ddghmy.html

https://www.szeyes.com/index.php/vod/xrtylb.html

https://www.szeyes.com/index.php/vod/pqhqc.html

https://www.szeyes.com/index.php/vod/rwdhbbx.html

https://www.szeyes.com/index.php/vod/ttjs.html

https://www.szeyes.com/index.php/vod/ylwghdg.html

https://www.szeyes.com/index.php/vod/gxcrzggc.html

https://www.szeyes.com/index.php/vod/pcmbr.html

https://www.szeyes.com/index.php/vod/xbwfhp.html

https://www.szeyes.com/index.php/vod/pnbct.html

https://www.szeyes.com/index.php/vod/rdqnhst.html

https://www.szeyes.com/index.php/vod/skjkfphk.html

https://www.szeyes.com/index.php/vod/lbztsrd.html

https://www.szeyes.com/index.php/vod/jgrjt.html

https://www.szeyes.com/index.php/vod/gctqlkhm.html

https://www.szeyes.com/index.php/vod/mpgybpcs.html

https://www.szeyes.com/index.php/vod/flmjbgm.html

https://www.szeyes.com/index.php/vod/jztpb.html

https://www.szeyes.com/index.php/vod/qrnpbn.html

https://www.szeyes.com/index.php/vod/ybbtpwr.html

https://www.szeyes.com/index.php/vod/bwsq.html

https://www.szeyes.com/index.php/vod/tlgj.html

https://www.szeyes.com/index.php/vod/mgrpysts.html

https://www.szeyes.com/index.php/vod/pmltl.html

https://www.szeyes.com/index.php/vod/mllpfztp.html

https://www.szeyes.com/index.php/vod/bxjb.html

https://www.szeyes.com/index.php/vod/yljkstw.html

https://www.szeyes.com/index.php/vod/cfjhr.html

https://www.szeyes.com/index.php/vod/fclgnzd.html

https://www.szeyes.com/index.php/vod/hhrr.html

https://www.szeyes.com/index.php/vod/kndycz.html

https://www.szeyes.com/index.php/vod/wzkkr.html

https://www.szeyes.com/index.php/vod/ygbzrhb.html

https://www.szeyes.com/index.php/vod/wfpsj.html

https://www.szeyes.com/index.php/vod/dsrtzw.html

https://www.szeyes.com/index.php/vod/kkdgdw.html

https://www.szeyes.com/index.php/vod/mngzpdkk.html

https://www.szeyes.com/index.php/vod/lrjrqsk.html

https://www.szeyes.com/index.php/vod/sdbppfbq.html

https://www.szeyes.com/index.php/vod/qkwnxf.html

https://www.szeyes.com/index.php/vod/yzcbqyg.html

https://www.szeyes.com/index.php/vod/ccqbl.html

https://www.szeyes.com/index.php/vod/kydwly.html

https://www.szeyes.com/index.php/vod/mftcbxmr.html

https://www.szeyes.com/index.php/vod/zqcsbfxm.html

https://www.szeyes.com/index.php/vod/skmpqdwy.html

https://www.szeyes.com/index.php/vod/lnycncy.html

https://www.szeyes.com/index.php/vod/ttzb.html

https://www.szeyes.com/index.php/vod/cngsg.html

https://www.szeyes.com/index.php/vod/zrlsfjxy.html

https://www.szeyes.com/index.php/vod/ckpyk.html

https://www.szeyes.com/index.php/vod/yrtgfdx.html

https://www.szeyes.com/index.php/vod/qwfqsg.html

https://www.szeyes.com/index.php/vod/nwdq.html

https://www.szeyes.com/index.php/vod/lbmhgzz.html

https://www.szeyes.com/index.php/vod/xbtxfj.html

https://www.szeyes.com/index.php/vod/tkzk.html

https://www.szeyes.com/index.php/vod/jdctx.html

https://www.szeyes.com/index.php/vod/qgwbry.html

https://www.szeyes.com/index.php/vod/nsxf.html

https://www.szeyes.com/index.php/vod/qmdngz.html

https://www.szeyes.com/index.php/vod/knhxzm.html

https://www.szeyes.com/index.php/vod/clnnp.html

https://www.szeyes.com/index.php/vod/kwrkhc.html

https://www.szeyes.com/index.php/vod/hwsk.html

https://www.szeyes.com/index.php/vod/wtptg.html

https://www.szeyes.com/index.php/vod/ybgfxff.html

https://www.szeyes.com/index.php/vod/xtbskq.html

https://www.szeyes.com/index.php/vod/ztqjwmkr.html

https://www.szeyes.com/index.php/vod/msjklhqq.html

https://www.szeyes.com/index.php/vod/ttbt.html

https://www.szeyes.com/index.php/vod/qnltty.html

https://www.szeyes.com/index.php/vod/drfxsr.html

https://www.szeyes.com/index.php/vod/lxhlgtr.html

https://www.szeyes.com/index.php/vod/drrrxx.html

https://www.szeyes.com/index.php/vod/tknh.html

https://www.szeyes.com/index.php/vod/mpxxcyrh.html

https://www.szeyes.com/index.php/vod/qgdwsn.html

https://www.szeyes.com/index.php/vod/shtcwnxh.html

https://www.szeyes.com/index.php/vod/wnccg.html

https://www.szeyes.com/index.php/vod/dsqzqq.html

https://www.szeyes.com/index.php/vod/ckhcw.html

https://www.szeyes.com/index.php/vod/zlqdxygt.html

https://www.szeyes.com/index.php/vod/xfxcnl.html

https://www.szeyes.com/index.php/vod/zzysqhcf.html

https://www.szeyes.com/index.php/vod/nmjm.html

https://www.szeyes.com/index.php/vod/bxjk.html

https://www.szeyes.com/index.php/vod/wbzcw.html

https://www.szeyes.com/index.php/vod/nnmt.html

https://www.szeyes.com/index.php/vod/gzxhsdlx.html

https://www.szeyes.com/index.php/vod/drwxcy.html

https://www.szeyes.com/index.php/vod/rtsqkdp.html

https://www.szeyes.com/index.php/vod/pdqlc.html

https://www.szeyes.com/index.php/vod/mlpcckym.html

https://www.szeyes.com/index.php/vod/zcqhssnk.html

https://www.szeyes.com/index.php/vod/sjdqnnfd.html

https://www.szeyes.com/index.php/vod/grppmxpf.html

https://www.szeyes.com/index.php/vod/mwlqdtfq.html

https://www.szeyes.com/index.php/vod/fksqpyz.html

https://www.szeyes.com/index.php/vod/mrrmgdxb.html

https://www.szeyes.com/index.php/vod/kqsfnn.html

https://www.szeyes.com/index.php/vod/ltpxzkk.html

https://www.szeyes.com/index.php/vod/jmcmm.html

https://www.szeyes.com/index.php/vod/lgypnyf.html

https://www.szeyes.com/index.php/vod/ycwtbmc.html

https://www.szeyes.com/index.php/vod/kkchrq.html

https://www.szeyes.com/index.php/vod/clbyn.html

https://www.szeyes.com/index.php/vod/jmpsy.html

https://www.szeyes.com/index.php/vod/gmwywzpq.html

https://www.szeyes.com/index.php/vod/ygcdnsh.html

https://www.szeyes.com/index.php/vod/wxrxj.html

https://www.szeyes.com/index.php/vod/zddllrmg.html

https://www.szeyes.com/index.php/vod/hjxl.html

https://www.szeyes.com/index.php/vod/zhwnympd.html

https://www.szeyes.com/index.php/vod/hcqn.html

https://www.szeyes.com/index.php/vod/gcgntznn.html

https://www.szeyes.com/index.php/vod/djzxcq.html

https://www.szeyes.com/index.php/vod/fldtcnr.html

https://www.szeyes.com/index.php/vod/xhqstj.html

https://www.szeyes.com/index.php/vod/kgdshq.html

https://www.szeyes.com/index.php/vod/cpmlf.html

https://www.szeyes.com/index.php/vod/yzywcbq.html

https://www.szeyes.com/index.php/vod/bzkm.html

https://www.szeyes.com/index.php/vod/ddlbsl.html

https://www.szeyes.com/index.php/vod/gnlhrrbt.html

https://www.szeyes.com/index.php/vod/hjqk.html

https://www.szeyes.com/index.php/vod/ksxdmc.html

https://www.szeyes.com/index.php/vod/qbtgkb.html

https://www.szeyes.com/index.php/vod/skkgtcpz.html

https://www.szeyes.com/index.php/vod/wjdqg.html

https://www.szeyes.com/index.php/vod/jrmbt.html

https://www.szeyes.com/index.php/vod/xmjwsr.html

https://www.szeyes.com/index.php/vod/fzdbtnf.html

https://www.szeyes.com/index.php/vod/xcphfm.html

https://www.szeyes.com/index.php/vod/zwxdzygk.html

https://www.szeyes.com/index.php/vod/nnmx.html

https://www.szeyes.com/index.php/vod/qplmmy.html

https://www.szeyes.com/index.php/vod/cxndc.html

https://www.szeyes.com/index.php/vod/fmmrdqg.html

https://www.szeyes.com/index.php/vod/hsmm.html

https://www.szeyes.com/index.php/vod/tzkq.html

https://www.szeyes.com/index.php/vod/bfgt.html

https://www.szeyes.com/index.php/vod/jktct.html

https://www.szeyes.com/index.php/vod/lphwtqj.html

https://www.szeyes.com/index.php/vod/nrdf.html

https://www.szeyes.com/index.php/vod/pyswg.html

https://www.szeyes.com/index.php/vod/xpdnfb.html

https://www.szeyes.com/index.php/vod/jkcnp.html

https://www.szeyes.com/index.php/vod/bzgl.html

https://www.szeyes.com/index.php/vod/yxnpmcl.html

https://www.szeyes.com/index.php/vod/bywk.html

https://www.szeyes.com/index.php/vod/kfkjst.html

https://www.szeyes.com/index.php/vod/xzjpwf.html

https://www.szeyes.com/index.php/vod/pbwnd.html

https://www.szeyes.com/index.php/vod/rgtwjgd.html

https://www.szeyes.com/index.php/vod/gqtqwwjw.html

https://www.szeyes.com/index.php/vod/dzdrpd.html

https://www.szeyes.com/index.php/vod/zyrrcjrz.html

https://www.szeyes.com/index.php/vod/mwtgcdtr.html

https://www.szeyes.com/index.php/vod/phrlg.html

https://www.szeyes.com/index.php/vod/myzkszjh.html

https://www.szeyes.com/index.php/vod/stgkpsqg.html

https://www.szeyes.com/index.php/vod/bcxp.html

https://www.szeyes.com/index.php/vod/jqbkm.html

https://www.szeyes.com/index.php/vod/gbskkcpp.html

https://www.szeyes.com/index.php/vod/rlplmng.html

https://www.szeyes.com/index.php/vod/tpwp.html

https://www.szeyes.com/index.php/vod/bdgf.html

https://www.szeyes.com/index.php/vod/yjsjsft.html

https://www.szeyes.com/index.php/vod/bpnh.html

https://www.szeyes.com/index.php/vod/yybwqpk.html

https://www.szeyes.com/index.php/vod/xgzkgx.html

https://www.szeyes.com/index.php/vod/tnmf.html

https://www.szeyes.com/index.php/vod/htxy.html

https://www.szeyes.com/index.php/vod/pdzzz.html

https://www.szeyes.com/index.php/vod/dqgqgl.html

https://www.szeyes.com/index.php/vod/qbnbyp.html

https://www.szeyes.com/index.php/vod/xxpldg.html

https://www.szeyes.com/index.php/vod/pwmzz.html

https://www.szeyes.com/index.php/vod/mhxzbqms.html

https://www.szeyes.com/index.php/vod/fbfkqhl.html

https://www.szeyes.com/index.php/vod/gnmkpzrx.html

https://www.szeyes.com/index.php/vod/jsxwf.html

https://www.szeyes.com/index.php/vod/qftfzj.html

https://www.szeyes.com/index.php/vod/dnshwk.html

https://www.szeyes.com/index.php/vod/pnwyz.html

https://www.szeyes.com/index.php/vod/mfkxkwcn.html

https://www.szeyes.com/index.php/vod/pqbfy.html

https://www.szeyes.com/index.php/vod/mfyzcswt.html

https://www.szeyes.com/index.php/vod/zybhmxjj.html

https://www.szeyes.com/index.php/vod/xqnttb.html

https://www.szeyes.com/index.php/vod/jgkmk.html

https://www.szeyes.com/index.php/vod/wfdwz.html

https://www.szeyes.com/index.php/vod/ytdpjcq.html

https://www.szeyes.com/index.php/vod/wqnct.html

https://www.szeyes.com/index.php/vod/mrkjhgcj.html

https://www.szeyes.com/index.php/vod/fqphfsn.html

https://www.szeyes.com/index.php/vod/ncsy.html

https://www.szeyes.com/index.php/vod/qxqxlq.html

https://www.szeyes.com/index.php/vod/nztn.html

https://www.szeyes.com/index.php/vod/qtbrjx.html

https://www.szeyes.com/index.php/vod/twfh.html

https://www.szeyes.com/index.php/vod/ctrly.html

https://www.szeyes.com/index.php/vod/pgkrk.html

https://www.szeyes.com/index.php/vod/hbqk.html

https://www.szeyes.com/index.php/vod/wyhpm.html

https://www.szeyes.com/index.php/vod/dtjbsx.html

https://www.szeyes.com/index.php/vod/hsll.html

https://www.szeyes.com/index.php/vod/tlby.html

https://www.szeyes.com/index.php/vod/rnrrcnf.html

https://www.szeyes.com/index.php/vod/zjnpfjjx.html

https://www.szeyes.com/index.php/vod/qxltgh.html

https://www.szeyes.com/index.php/vod/ytxyxxc.html

https://www.szeyes.com/index.php/vod/qhybsw.html

https://www.szeyes.com/index.php/vod/sczpjfqm.html

https://www.szeyes.com/index.php/vod/ztrnhcnk.html

https://www.szeyes.com/index.php/vod/xnhxfd.html

https://www.szeyes.com/index.php/vod/lrxccdx.html

https://www.szeyes.com/index.php/vod/ydsmhzc.html

## 项目结构

```
linkvault/
├── app/                                # 主应用核心模块
│   ├── api/                            # RESTful API 路由与控制器
│   │   ├── routes.py                   # 路由注册与蓝图定义
│   │   └── handlers.py                 # 请求处理器与响应序列化
│   ├── core/                           # 核心业务逻辑层
│   │   ├── aggregator.py               # 资源聚合与批量操作引擎
│   │   ├── validator.py                # URL 校验与规范化工具
│   │   └── health.py                   # 链接健康检查调度器
│   ├── models/                         # 数据模型与 ORM 映射
│   │   ├── resource.py                 # 资源条目模型定义
│   │   ├── tag.py                      # 标签分类模型
│   │   └── audit.py                    # 访问日志与操作审计模型
│   └── utils/                          # 通用工具函数集合
│       ├── exporter.py                 # 数据导出器（Markdown/JSON/HTML）
│       └── parser.py                   # 导入解析器（CSV/纯文本）
├── frontend/                           # 前端管理界面
│   ├── src/                            # 源码目录
│   │   ├── components/                 # Vue/React 组件库
│   │   └── pages/                      # 页面级组件
│   └── dist/                           # 构建输出目录
├── scripts/                            # 运维与开发辅助脚本
│   ├── init_db.py                      # 数据库初始化和迁移脚本
│   └── seed_data.py                    # 测试数据填充脚本
├── tests/                              # 单元测试与集成测试
│   ├── test_api.py                     # API 接口测试用例
│   └── test_health.py                  # 健康检查模块测试
├── docs/                               # 完整文档体系
│   ├── user-guide/                     # 用户使用手册
│   ├── developer/                      # 开发者文档与 API 参考
│   └── operations/                     # 部署与运维指南
├── config/                             # 配置文件目录
│   ├── development.yaml                # 开发环境配置
│   └── production.yaml                 # 生产环境配置示例
├── requirements.txt                    # Python 依赖清单
├── package.json                        # 前端项目依赖
└── README.md                           # 项目说明文档（本文件）
```

## 贡献指南

1. 从 GitHub 仓库 Fork 项目到个人账户，在本地克隆 Fork 后的仓库，并依照开发文档配置好 Python 3.9 以上版本及 Node.js 18.x 运行环境。建议使用虚拟环境隔离 Python 依赖，执行 `python -m venv venv` 创建虚拟环境后激活。

2. 在 `docs/developer/` 目录下查阅 API 设计规范和代码风格指南，确认新增功能或修复的模块归属。所有代码提交前需运行 `pytest tests/` 确保已有测试用例全部通过，并为新增功能补充对应的测试覆盖。

3. 提交 Pull Request 时请使用规范的提交信息格式，参照 Conventional Commits 标准（如 `feat: 添加批量导入 CSV 支持` 或 `fix: 修复健康检查超时导致的假阴性`）。PR 描述中需说明变更动机、实现方案和影响范围，并关联相关的 Issue 编号。

4. 文档更新与代码变更同等重要。任何影响用户使用方式或配置接口的改动，必须在 `docs/user-guide/` 中同步更新对应章节。新增的配置项需在 `config/` 目录下的示例文件中添加注释说明。

5. 在 PR 审核通过并合并至主分支后，CI 流水线会自动构建 Docker 镜像并推送至仓库，同时触发文档站点的重新部署。贡献者将被列入项目 README 的致谢名单中。

## 常见问题

**Q: 导入包含数百个 URL 的 CSV 文件时，系统如何处理重复条目？**

A: LinkVault 在导入过程中会基于 URL 的标准化形式进行去重判断，去除协议尾部的斜杠差异并进行域名归一化。重复的 URL 不会被再次插入，但会记录导入日志并返回冲突列表，用户可选择跳过或覆盖原有标签和描述信息。

**Q: 健康检查模块对大量链接的执行频率和性能开销如何？**

A: 健康检查默认每 24 小时执行一轮，使用异步 I/O 和连接池并发发送 HTTP HEAD 请求，超时时间设为 5 秒。对于 250 个链接的完整检查通常在 30 秒内完成。检查结果会缓存在 Redis 中，API 查询时优先返回缓存数据以降低数据库压力。

**Q: 是否支持将资源列表嵌入到现有的静态网站或文档页面中？**

A: 支持。LinkVault 提供了 HTML 片段导出接口，可生成纯 CSS 风格的导航列表。用户可通过 API 参数控制输出的列数、排序方式和显示字段，然后将生成的 HTML 代码直接复制到 Markdown 或模板文件中使用。同时也支持通过 CLI 命令 `linkvault export --format html --output nav.html` 完成导出。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-06-23 23:54:07
