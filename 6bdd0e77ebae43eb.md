# ResourceLink Hub

ResourceLink Hub 是一个面向开发者、技术研究人员与内容创作者的轻量化外链资源归集与导航系统。该项目定位为技术资源的中转与整理层，不直接存储内容，而是通过结构化方式收录互联网上的公开节目、活动、文档与参考资料，帮助用户从大量分散的链接中快速定位自身关注的信息维度。

ResourceLink Hub 主要解决三类问题：第一，个人收藏夹无法支持多人协作与标签化检索；第二，团队内部共享的文档链接散落在聊天记录或邮件中，难以追溯；第三，开源项目或研究课题需要长期维护一份外部参考列表，且要求版本可追踪、格式可复用。本项目以纯静态 Markdown 与 JSON 为数据载体，配合轻量级脚本实现链接的可用性检查与分类统计，适合部署在任意支持静态托管的平台。

## 功能概览

**结构化外链入库** 支持通过命令行脚本将单个 URL 或批量 URL 导入到项目的资源索引中，自动生成唯一标识与时间戳记录。

**多维度标签分类** 每个资源条目可附加多个自定义标签，支持按主题、来源、格式或任意业务维度进行筛选与统计。

**链接可用性巡检** 内置基于 HTTP 状态码的链接检查功能，可定期输出失效链接报告，帮助维护者及时更新或移除异常条目。

**Markdown 原生渲染** 所有资源列表与文档均以纯 Markdown 格式存储，无需数据库，兼容 GitHub、GitLab 等主流代码托管平台的自动渲染。

**JSON 结构化导出** 支持将资源列表导出为 JSON 格式，便于集成到其他系统或用于自动化流程中，如定时同步、自定义前端展示等。

**增量更新与变更日志** 每次新增、修改或删除资源时，自动生成变更记录，方便团队追溯操作历史，降低维护成本。

**轻量级权限模拟** 通过 Git 分支管理与 Pull Request 流程，实现资源审核与发布分离，适合多人协作场景。

## 应用场景

开源项目文档站的外链维护
开源项目的 README 或官方文档中常需要引用大量外部参考链接，如规范标准、相关工具、社区讨论等。ResourceLink Hub 可作为子模块引入，将外链从主文档中分离，使文档主体更聚焦于项目本身，同时外链列表可单独维护与版本控制。

技术团队内部知识库的链接聚合
技术团队在日常工作中会积累大量有用的外部资源，如技术博客、视频教程、在线工具等。使用 ResourceLink Hub 可以建立团队共享的资源索引，避免知识沉淀在个人收藏夹中，新成员入职时也能快速了解团队常用的参考渠道。

研究课题的参考文献外部链接整理
对于需要进行文献调研或技术预研的课题，研究者需要长期跟踪大量外部页面。ResourceLink Hub 提供结构化的链接记录方式，支持标注每个链接的用途、关注状态与最后检查时间，便于研究过程中的回溯与整理。

个人书签的版本化替代方案
习惯使用浏览器书签的用户常面临跨设备同步不一致、分类层级混乱的问题。ResourceLink Hub 以纯文本方式管理书签，配合 Git 仓库可实现跨设备同步，同时保留每一次修改的历史记录，支持随时回退到任意时间点。

## 快速开始

以下命令适用于 Linux 与 macOS 环境，Windows 用户可使用 WSL 或 Git Bash 执行。

```bash
# 克隆项目仓库到本地
git clone https://github.com/resourcelink-hub/resourcelink-hub.git

# 进入项目目录
cd resourcelink-hub

# 安装依赖（基于 Python 3.9+）
pip install -r requirements.txt

# 运行初始化脚本，生成基础资源索引文件
python scripts/init_index.py

# 执行链接可用性检查，验证所有已收录的 URL
python scripts/check_links.py --source data/resources.json --output reports/broken_links.txt

# 启动本地预览服务（可选），通过浏览器访问 http://127.0.0.1:8000 查看渲染后的文档
python -m http.server 8000
```

## 安装要求

| 依赖 | 必需 | 说明 |
|------|------|------|
| Python 3.9 或更高版本 | 是 | 用于运行资源导入、检查、导出等核心脚本 |
| pip 22.0 或更高版本 | 是 | 管理 Python 依赖包，如 requests、click 等 |
| Git 2.25 或更高版本 | 是 | 用于克隆仓库、提交变更及与远程仓库同步 |
| requests 库 (Python) | 是 | 发送 HTTP 请求，用于链接可用性检查功能 |
| click 库 (Python) | 是 | 命令行参数解析，提供友好的 CLI 交互体验 |
| 磁盘空间 50 MB 以上 | 是 | 存储资源索引、日志与报告文件，不存储外部资源内容 |
| 可选：Node.js 18+ | 否 | 仅当需要使用前端预览面板或自定义 UI 时安装 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 用户入门 | docs/getting_started.md | 如何安装、初始化并第一次导入资源链接？ |
| 操作指南 | docs/usage/import.md | 如何批量导入 URL？如何添加标签与备注？ |
| 操作指南 | docs/usage/check.md | 如何检查链接是否仍然有效？如何解读报告？ |
| 操作指南 | docs/usage/export.md | 如何导出 JSON 格式的资源列表用于其他系统？ |
| 参考手册 | docs/reference/config.md | 配置文件各项参数的含义与默认值是什么？ |
| 参考手册 | docs/reference/api.md | 脚本模块的调用方式与函数签名说明 |
| 贡献文档 | docs/contributing.md | 如何提交新的资源链接、修改现有条目或报告问题？ |
| 维护策略 | docs/maintenance.md | 链接失效时的处理策略与定期巡检周期建议 |

## 资源列表

本项目当前收录的外部资源均来源于公开节目存档页面，按访问路径归类如下。所有 URL 均保留原始格式，未作任何协议补全或域名改写。

节目页面存档

https://www.emha-shows.org/programme/kbkcjl.html
https://www.emha-shows.org/programme/rbhkrym.html
https://www.emha-shows.org/programme/lncqfhx.html
https://www.emha-shows.org/programme/jymns.html
https://www.emha-shows.org/programme/lxhthmg.html
https://www.emha-shows.org/programme/ycqjhjk.html
https://www.emha-shows.org/programme/wwrbd.html
https://www.emha-shows.org/programme/dhdzdm.html
https://www.emha-shows.org/programme/mssctglb.html
https://www.emha-shows.org/programme/tdpb.html
https://www.emha-shows.org/programme/mfdmsrqd.html
https://www.emha-shows.org/programme/kmbmws.html
https://www.emha-shows.org/programme/dzrlsq.html
https://www.emha-shows.org/programme/gkmsyhnm.html
https://www.emha-shows.org/programme/cmzfd.html
https://www.emha-shows.org/programme/kfxxnj.html
https://www.emha-shows.org/programme/rsktnrm.html
https://www.emha-shows.org/programme/ttlh.html
https://www.emha-shows.org/programme/qkxwcg.html
https://www.emha-shows.org/programme/djckqc.html
https://www.emha-shows.org/programme/gcjrlhbx.html
https://www.emha-shows.org/programme/jgthx.html
https://www.emha-shows.org/programme/zrfyzfny.html
https://www.emha-shows.org/programme/mjzfhngl.html
https://www.emha-shows.org/programme/sbqygrgm.html
https://www.emha-shows.org/programme/gphwkhdq.html
https://www.emha-shows.org/programme/ymjtcxl.html
https://www.emha-shows.org/programme/lgmrkbf.html
https://www.emha-shows.org/programme/fmtlhfn.html
https://www.emha-shows.org/programme/clgfq.html
https://www.emha-shows.org/programme/tjny.html
https://www.emha-shows.org/programme/hdfk.html
https://www.emha-shows.org/programme/gzndqzlh.html
https://www.emha-shows.org/programme/nxww.html
https://www.emha-shows.org/programme/kpjzpf.html
https://www.emha-shows.org/programme/mphwwrmt.html
https://www.emha-shows.org/programme/tcns.html
https://www.emha-shows.org/programme/xzlhgh.html
https://www.emha-shows.org/programme/jpzsq.html
https://www.emha-shows.org/programme/gxgmnrft.html
https://www.emha-shows.org/programme/nzrx.html
https://www.emha-shows.org/programme/bxtr.html
https://www.emha-shows.org/programme/rthbgjn.html
https://www.emha-shows.org/programme/kdbsby.html
https://www.emha-shows.org/programme/lpsgscd.html
https://www.emha-shows.org/programme/yqdrkbm.html
https://www.emha-shows.org/programme/qhnhsy.html
https://www.emha-shows.org/programme/yqjbzlt.html
https://www.emha-shows.org/programme/rmjgzfp.html
https://www.emha-shows.org/programme/knkpwk.html
https://www.emha-shows.org/programme/mcffhktj.html
https://www.emha-shows.org/programme/znplzkcg.html
https://www.emha-shows.org/programme/dtcwlg.html
https://www.emha-shows.org/programme/lwzqpkj.html
https://www.emha-shows.org/programme/mbtpxslj.html
https://www.emha-shows.org/programme/tcrw.html
https://www.emha-shows.org/programme/ctxyx.html
https://www.emha-shows.org/programme/fykmppn.html
https://www.emha-shows.org/programme/qcsrpf.html
https://www.emha-shows.org/programme/nqxb.html
https://www.emha-shows.org/programme/lwhnjyh.html
https://www.emha-shows.org/programme/dspchm.html
https://www.emha-shows.org/programme/tjdz.html
https://www.emha-shows.org/programme/mlgkpfqq.html
https://www.emha-shows.org/programme/nfng.html
https://www.emha-shows.org/programme/whgnr.html
https://www.emha-shows.org/programme/gjycqhdn.html
https://www.emha-shows.org/programme/zrcbnxpq.html
https://www.emha-shows.org/programme/rzkrsdb.html
https://www.emha-shows.org/programme/ppxtf.html
https://www.emha-shows.org/programme/hsjw.html
https://www.emha-shows.org/programme/jwdky.html
https://www.emha-shows.org/programme/ptxbz.html
https://www.emha-shows.org/programme/mscbssxq.html
https://www.emha-shows.org/programme/zhrwyhpt.html
https://www.emha-shows.org/programme/hkdb.html
https://www.emha-shows.org/programme/yjscjjh.html
https://www.emha-shows.org/programme/qslytr.html
https://www.emha-shows.org/programme/nwwl.html
https://www.emha-shows.org/programme/glgpkjqt.html
https://www.emha-shows.org/programme/hbkr.html
https://www.emha-shows.org/programme/zcwqhfll.html
https://www.emha-shows.org/programme/lbtbfwj.html
https://www.emha-shows.org/programme/srwzxmdl.html
https://www.emha-shows.org/programme/lfrfhhl.html
https://www.emha-shows.org/programme/sjyfwcdc.html
https://www.emha-shows.org/programme/htmz.html
https://www.emha-shows.org/programme/pwkyt.html
https://www.emha-shows.org/programme/rqxmrtz.html
https://www.emha-shows.org/programme/txmb.html
https://www.emha-shows.org/programme/jgpnq.html
https://www.emha-shows.org/programme/lbytcsg.html
https://www.emha-shows.org/programme/mqrqhnsx.html
https://www.emha-shows.org/programme/thbz.html
https://www.emha-shows.org/programme/mzdwydjx.html
https://www.emha-shows.org/programme/thgq.html
https://www.emha-shows.org/programme/lbqxyjy.html
https://www.emha-shows.org/programme/sgdcxlkg.html
https://www.emha-shows.org/programme/lqyyzkn.html
https://www.emha-shows.org/programme/ntll.html
https://www.emha-shows.org/programme/tspk.html
https://www.emha-shows.org/programme/crdxm.html
https://www.emha-shows.org/programme/rxmxsrk.html
https://www.emha-shows.org/programme/tbyp.html
https://www.emha-shows.org/programme/mpntbbls.html
https://www.emha-shows.org/programme/tzkn.html
https://www.emha-shows.org/programme/wthgz.html
https://www.emha-shows.org/programme/sdknkdck.html
https://www.emha-shows.org/programme/wcnkp.html
https://www.emha-shows.org/programme/nkpr.html
https://www.emha-shows.org/programme/kqdjzm.html
https://www.emha-shows.org/programme/rkgwshn.html
https://www.emha-shows.org/programme/gjzbcpls.html
https://www.emha-shows.org/programme/jxnqt.html
https://www.emha-shows.org/programme/wklkw.html
https://www.emha-shows.org/programme/dkxlyh.html
https://www.emha-shows.org/programme/rcqqgsh.html
https://www.emha-shows.org/programme/pwmlr.html
https://www.emha-shows.org/programme/cynzn.html
https://www.emha-shows.org/programme/txmm.html
https://www.emha-shows.org/programme/dkpjbl.html
https://www.emha-shows.org/programme/brlp.html
https://www.emha-shows.org/programme/twyh.html
https://www.emha-shows.org/programme/mkbspwds.html
https://www.emha-shows.org/programme/ftcpbqt.html
https://www.emha-shows.org/programme/ctsqs.html
https://www.emha-shows.org/programme/dxgzjb.html
https://www.emha-shows.org/programme/bwph.html
https://www.emha-shows.org/programme/ydcnryk.html
https://www.emha-shows.org/programme/wlscc.html
https://www.emha-shows.org/programme/xkzzhy.html
https://www.emha-shows.org/programme/fkbdlqt.html
https://www.emha-shows.org/programme/nkdx.html
https://www.emha-shows.org/programme/bgsp.html
https://www.emha-shows.org/programme/sgcgtqpb.html
https://www.emha-shows.org/programme/lrmxkng.html
https://www.emha-shows.org/programme/ffynqxq.html
https://www.emha-shows.org/programme/xyxdyt.html
https://www.emha-shows.org/programme/kdjrqk.html
https://www.emha-shows.org/programme/cqxrj.html
https://www.emha-shows.org/programme/bltf.html
https://www.emha-shows.org/programme/yhyqylt.html
https://www.emha-shows.org/programme/rlrqhcw.html
https://www.emha-shows.org/programme/rdhgwhp.html
https://www.emha-shows.org/programme/zfhgdlwn.html
https://www.emha-shows.org/programme/lfmswmh.html
https://www.emha-shows.org/programme/jcrxq.html
https://www.emha-shows.org/programme/bnjx.html
https://www.emha-shows.org/programme/sfcnsbrz.html
https://www.emha-shows.org/programme/phhbb.html
https://www.emha-shows.org/programme/cwzdc.html
https://www.emha-shows.org/programme/wfdgx.html
https://www.emha-shows.org/programme/ywckxfm.html
https://www.emha-shows.org/programme/lrxwnwt.html
https://www.emha-shows.org/programme/syjbjdbc.html
https://www.emha-shows.org/programme/mblzmlmb.html
https://www.emha-shows.org/programme/kqkbhz.html
https://www.emha-shows.org/programme/ctzlc.html
https://www.emha-shows.org/programme/tkhs.html
https://www.emha-shows.org/programme/nnxw.html
https://www.emha-shows.org/programme/qyxkrb.html
https://www.emha-shows.org/programme/zftmmbzb.html
https://www.emha-shows.org/programme/chpry.html
https://www.emha-shows.org/programme/tclz.html
https://www.emha-shows.org/programme/hwml.html
https://www.emha-shows.org/programme/yrjtzfj.html
https://www.emha-shows.org/programme/qrkbwx.html
https://www.emha-shows.org/programme/jnjrd.html
https://www.emha-shows.org/programme/ljdnlhg.html
https://www.emha-shows.org/programme/hwcx.html
https://www.emha-shows.org/programme/fhtblwn.html
https://www.emha-shows.org/programme/jzrqq.html
https://www.emha-shows.org/programme/gqjjyjlf.html
https://www.emha-shows.org/programme/sfptgxsg.html
https://www.emha-shows.org/programme/bxdf.html
https://www.emha-shows.org/programme/ftznqyl.html
https://www.emha-shows.org/programme/rfdyhnd.html
https://www.emha-shows.org/programme/pwskh.html
https://www.emha-shows.org/programme/mztdkjzh.html
https://www.emha-shows.org/programme/qmbdkz.html
https://www.emha-shows.org/programme/dwswsj.html
https://www.emha-shows.org/programme/xhtlzd.html
https://www.emha-shows.org/programme/thsl.html
https://www.emha-shows.org/programme/mlcptxcf.html
https://www.emha-shows.org/programme/tdmx.html
https://www.emha-shows.org/programme/lbgzkbb.html
https://www.emha-shows.org/programme/jhqbx.html
https://www.emha-shows.org/programme/lrnkyyt.html
https://www.emha-shows.org/programme/jqqxy.html
https://www.emha-shows.org/programme/pjfzs.html
https://www.emha-shows.org/programme/xntmld.html
https://www.emha-shows.org/programme/wrmfr.html
https://www.emha-shows.org/programme/yfbkyzt.html
https://www.emha-shows.org/programme/lbrjcmk.html
https://www.emha-shows.org/programme/ymnjmdt.html
https://www.emha-shows.org/programme/mwsgprcb.html
https://www.emha-shows.org/programme/fnnfwsb.html
https://www.emha-shows.org/programme/xkwhkf.html
https://www.emha-shows.org/programme/pmyzs.html
https://www.emha-shows.org/programme/ylffxwt.html
https://www.emha-shows.org/programme/qgjrmd.html
https://www.emha-shows.org/programme/ymxbhtm.html
https://www.emha-shows.org/programme/lctglrz.html
https://www.emha-shows.org/programme/nxsb.html
https://www.emha-shows.org/programme/lmhhfsj.html
https://www.emha-shows.org/programme/kjwkyk.html
https://www.emha-shows.org/programme/hfsf.html
https://www.emha-shows.org/programme/zypgbjxc.html
https://www.emha-shows.org/programme/xmlcsn.html
https://www.emha-shows.org/programme/bbgw.html
https://www.emha-shows.org/programme/jrxrr.html
https://www.emha-shows.org/programme/flkzgdb.html
https://www.emha-shows.org/programme/mtxqwydj.html
https://www.emha-shows.org/programme/ppfsr.html
https://www.emha-shows.org/programme/hdkc.html
https://www.emha-shows.org/programme/nqcp.html
https://www.emha-shows.org/programme/qfnlwm.html
https://www.emha-shows.org/programme/nstg.html
https://www.emha-shows.org/programme/qdzqrr.html
https://www.emha-shows.org/programme/xghsmm.html
https://www.emha-shows.org/programme/txtr.html
https://www.emha-shows.org/programme/qgmhhb.html
https://www.emha-shows.org/programme/dbsxgn.html
https://www.emha-shows.org/programme/qnzhgp.html
https://www.emha-shows.org/programme/ncdf.html
https://www.emha-shows.org/programme/clkdq.html
https://www.emha-shows.org/programme/kpfzkx.html
https://www.emha-shows.org/programme/rbgdhyb.html
https://www.emha-shows.org/programme/fcwjglh.html
https://www.emha-shows.org/programme/ywbgdjn.html
https://www.emha-shows.org/programme/bykx.html
https://www.emha-shows.org/programme/cxnck.html
https://www.emha-shows.org/programme/fwswgbn.html
https://www.emha-shows.org/programme/xxcrdt.html
https://www.emha-shows.org/programme/klgmzf.html
https://www.emha-shows.org/programme/llmpnht.html
https://www.emha-shows.org/programme/skbknjzn.html
https://www.emha-shows.org/programme/lnnmzry.html
https://www.emha-shows.org/programme/ytxxwpb.html
https://www.emha-shows.org/programme/krzmcb.html
https://www.emha-shows.org/programme/rnjczzg.html
https://www.emha-shows.org/programme/jqfdn.html
https://www.emha-shows.org/programme/bzsr.html
https://www.emha-shows.org/programme/dhpqsw.html
https://www.emha-shows.org/programme/whzbr.html
https://www.emha-shows.org/programme/kjrbhj.html
https://www.emha-shows.org/programme/mywkkblz.html
https://www.emha-shows.org/programme/zsctgxpj.html
https://www.emha-shows.org/programme/rcsbmtm.html
https://www.emha-shows.org/programme/wfkfd.html

## 项目结构

```
resourcelink-hub/
├── README.md                       # 项目概述与快速入门
├── LICENSE                         # MIT 许可证文件
├── requirements.txt                # Python 依赖清单
├── .gitignore                      # Git 忽略规则
├── config/
│   └── settings.yaml               # 全局配置文件，含巡检超时、标签规则等
├── data/
│   ├── resources.json              # 主资源索引，含所有 URL 与元数据
│   ├── tags.json                   # 标签字典及使用频次统计
│   └── changelog.json              # 资源变更操作日志
├── scripts/
│   ├── init_index.py               # 初始化资源索引文件
│   ├── import_urls.py              # 批量导入 URL 并生成条目
│   ├── check_links.py              # 检查所有链接的可用性
│   ├── export_json.py              # 导出 JSON 格式资源列表
│   └── utils/
│       ├── http_client.py          # 封装 HTTP 请求与重试逻辑
│       └── validator.py            # URL 格式校验与规范化
├── docs/
│   ├── getting_started.md          # 新用户入门指南
│   ├── usage/
│   │   ├── import.md               # 导入操作详细说明
│   │   ├── check.md                # 链接检查操作说明
│   │   └── export.md               # 导出操作说明
│   ├── reference/
│   │   ├── config.md               # 配置项完整参考
│   │   └── api.md                  # 脚本函数接口说明
│   ├── contributing.md             # 贡献指南详细版
│   └── maintenance.md              # 日常维护策略与周期
├── reports/
│   └── broken_links.txt            # 链接检查报告输出目录
└── tests/
    ├── test_import.py              # 导入功能单元测试
    ├── test_check.py               # 链接检查功能单元测试
    └── test_export.py              # 导出功能单元测试
```

## 贡献指南

提交新的资源链接
在 data/resources.json 中按照既有格式新增条目，包含 URL、标题、标签和添加日期字段。提交前请运行 scripts/check_links.py 验证新链接的有效性，确保不会引入已失效的资源。

修改或更新现有条目
如果发现某个链接的标题或标签不准确，或者链接内容已迁移至新地址，请在 data/changelog.json 中记录变更原因，然后修改 resources.json 中的对应字段。变更说明应清晰描述修改前后的差异。

报告链接失效问题
使用 scripts/check_links.py 生成最新的失效链接报告，将报告文件附在 Issue 中提交。如果无权限运行脚本，也可以直接在 Issue 中列出失效 URL 并提供可替代的链接或说明。

完善文档与示例
欢迎改进 README、操作指南或 API 文档中的表述不清之处。文档修改请保持与技术实现一致，如有功能变更，应同步更新对应的文档章节。

提出新功能或改进建议
通过 Issue 描述当前流程中的痛点或期望新增的能力，建议附带使用场景说明。核心脚本的改动需通过单元测试，并确保不影响既有数据的兼容性。

## 常见问题

资源索引中的链接访问时返回 404 状态码，应该如何处理？
首先使用 scripts/check_links.py 确认链接状态。如果确认失效，建议先在原站点搜索是否有对应的新链接，若能找到则更新 resources.json 中的 URL 字段，并在 changelog.json 中记录。若无法找到替代链接，可考虑将该条目标记为已失效或直接移除，同时保留移除记录以便后续追溯。

如何批量导入大量 URL 而不需要手动编辑 JSON 文件？
使用 scripts/import_urls.py 脚本，可以通过命令行参数传入包含 URL 列表的文本文件，每行一个 URL。脚本会自动去重、校验格式并生成符合索引规范的条目，同时为缺失标题的链接自动提取页面标题（依赖网络访问）。

链接检查脚本运行速度较慢或超时，如何优化？
在 config/settings.yaml 中调整 request_timeout 参数（单位秒），建议根据网络环境设置为 5 至 15 秒。同时可以通过修改 concurrent_workers 参数控制并发请求数量，避免因网络拥塞导致大量超时。对于已知经常超时的站点，可将其加入 skip_domains 列表中，跳过检查或单独配置更长超时。

## 许可证

本项目采用 MIT 许可证。任何个人或组织均可自由使用、复制、修改、合并、发布、分发、再许可及销售本软件的副本，但需在软件的所有副本中保留版权声明与许可声明。本软件按“现状”提供，不提供任何形式的明示或暗示担保，包括但不限于适销性、特定用途适用性及非侵权性的担保。有关完整条款，请参阅项目根目录下的 LICENSE 文件。

> 外链数量: 250 | 生成时间: 2026-06-24 00:05:56
