# Nexus Index

Nexus Index 是一个面向技术研究、数据挖掘与内容聚合场景的高密度外链资源索引站。项目定位于将分散在互联网各处的垂直领域视频入口、专题页面与资料库地址进行结构化整理，以纯静态目录形式对外提供稳定、可机读的链接集合。主要服务对象为需要批量获取特定分类视频源地址的研究人员、内容运营团队以及自动化采集系统的开发者。

项目本身不存储任何媒体内容，仅维护 URL 映射关系与分类元数据。通过扁平化的目录结构与规范化的命名规则，Nexus Index 能够帮助用户在数百个资源地址中快速定位目标条目，并支持通过脚本批量读取索引文件以完成后续处理流程。当前批次为第 416/1241 批，共收录 250 个资源链接，覆盖影视、教育、科技、生活等多个主题分类。

## 功能概览

- **批量链接导入**：支持一次性载入数百条外链记录，自动完成格式校验与去重处理，生成标准化索引条目。

- **分类标签系统**：每条记录均可关联一个或多个主题标签，支持按标签筛选与聚合，便于构建自定义分类视图。

- **链接状态巡检**：内置 HTTP 状态码检测模块，可定期检查索引中链接的可访问性，输出失效链接报告。

- **元数据扩展字段**：支持为每条链接附加备注信息，包括来源描述、更新日期、内容摘要等，丰富索引维度。

- **多格式导出**：索引数据可导出为 JSON、CSV 或纯文本列表格式，适配不同下游系统的数据消费需求。

- **版本化变更追踪**：每次索引更新均生成变更日志，记录新增、删除与修改的条目，支持回溯历史版本。

- **搜索与过滤**：提供基于关键词的快速搜索功能，支持按 URL 片段、标签、备注内容进行全文检索。

## 应用场景

- **视频资源专题整理**：内容运营人员可将某一主题相关的视频播放页地址集中收录至索引中，配合分类标签形成专题目录，便于团队成员共享与查阅。

- **采集任务源管理**：数据采集系统的开发者可将索引作为种子源列表，通过脚本批量读取 URL 并下发至采集节点，实现源地址的集中配置与动态更新。

- **链接有效性监控**：运维人员可利用索引的状态巡检功能，定期对收录的链接进行可达性检测，及时发现失效资源并触发告警或自动剔除。

- **研究资料归档**：研究人员可将项目过程中积累的参考链接按类别录入索引，形成可检索、可导出的个人知识库，降低资料散落丢失的风险。

## 快速开始

以下命令演示了如何从代码仓库克隆项目、安装依赖并启动本地索引服务。

```bash
git clone https://github.com/nexus-index/nexus-index.git
cd nexus-index
npm install
npm run build
npm start
```

执行完成后，索引服务默认运行于 127.0.0.1:3000。访问根路径可查看索引总览页面，访问 /api/index 可获取完整的 JSON 格式索引数据。

## 安装要求

| 依赖 | 必需 | 说明 |
|------|------|------|
| Node.js >= 18.0.0 | 是 | 运行时环境，用于执行服务端代码与构建脚本 |
| npm >= 9.0.0 | 是 | 包管理器，用于安装项目依赖 |
| SQLite >= 3.35.0 | 是 | 嵌入式数据库，用于存储索引条目与元数据 |
| Git >= 2.30.0 | 否 | 仅从源码构建时需要，用于克隆仓库 |
| Docker >= 20.10.0 | 否 | 可选容器化部署方式，便于快速启动生产环境 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 用户手册 | /docs/user-guide.md | 如何添加链接、编辑标签、导出数据、使用搜索功能 |
| 管理员指南 | /docs/admin-guide.md | 如何配置巡检参数、管理用户权限、查看系统日志 |
| API 参考 | /docs/api-reference.md | 索引查询接口、批量导入接口、状态检测接口的请求与响应格式 |
| 开发指引 | /docs/development.md | 项目目录结构、编码规范、测试流程、提交说明格式 |

## 资源列表

影视分类

https://www.szeyes.com/index.php/vod/zbwbscnt.html
https://www.szeyes.com/index.php/vod/cbhcx.html
https://www.szeyes.com/index.php/vod/jbhyh.html
https://www.szeyes.com/index.php/vod/qcxnns.html
https://www.szeyes.com/index.php/vod/sjzqfjdm.html
https://www.szeyes.com/index.php/vod/lxzkfrt.html
https://www.szeyes.com/index.php/vod/twww.html
https://www.szeyes.com/index.php/vod/xslrby.html
https://www.szeyes.com/index.php/vod/pjsrf.html
https://www.szeyes.com/index.php/vod/cpwsx.html
https://www.szeyes.com/index.php/vod/qdtxfm.html
https://www.szeyes.com/index.php/vod/yxtsldx.html
https://www.szeyes.com/index.php/vod/tkwt.html
https://www.szeyes.com/index.php/vod/mwpqcykj.html
https://www.szeyes.com/index.php/vod/pmrbj.html
https://www.szeyes.com/index.php/vod/xfsply.html
https://www.szeyes.com/index.php/vod/qqdfrg.html
https://www.szeyes.com/index.php/vod/jyrsx.html
https://www.szeyes.com/index.php/vod/bykc.html
https://www.szeyes.com/index.php/vod/rwqyxlq.html
https://www.szeyes.com/index.php/vod/tjqw.html
https://www.szeyes.com/index.php/vod/ggymbwmp.html
https://www.szeyes.com/index.php/vod/jffkf.html
https://www.szeyes.com/index.php/vod/bbdq.html
https://www.szeyes.com/index.php/vod/nfpq.html
https://www.szeyes.com/index.php/vod/hsrk.html
https://www.szeyes.com/index.php/vod/kjrdfj.html
https://www.szeyes.com/index.php/vod/xpkgyf.html
https://www.szeyes.com/index.php/vod/zyspzqbr.html
https://www.szeyes.com/index.php/vod/djftyr.html
https://www.szeyes.com/index.php/vod/wphhm.html
https://www.szeyes.com/index.php/vod/xbkfxt.html
https://www.szeyes.com/index.php/vod/tntf.html
https://www.szeyes.com/index.php/vod/hmkt.html
https://www.szeyes.com/index.php/vod/ktjbwy.html
https://www.szeyes.com/index.php/vod/gjgkyjhc.html
https://www.szeyes.com/index.php/vod/swzhdmjx.html
https://www.szeyes.com/index.php/vod/bwqc.html
https://www.szeyes.com/index.php/vod/jncbk.html
https://www.szeyes.com/index.php/vod/fhqpzfm.html
https://www.szeyes.com/index.php/vod/xhtgnw.html
https://www.szeyes.com/index.php/vod/ntcx.html
https://www.szeyes.com/index.php/vod/gkpnnffd.html
https://www.szeyes.com/index.php/vod/ngyr.html
https://www.szeyes.com/index.php/vod/bcmj.html
https://www.szeyes.com/index.php/vod/fqfhxbg.html
https://www.szeyes.com/index.php/vod/cclbz.html
https://www.szeyes.com/index.php/vod/tbsr.html
https://www.szeyes.com/index.php/vod/hwzh.html
https://www.szeyes.com/index.php/vod/qkpbhc.html
https://www.szeyes.com/index.php/vod/ypbywwm.html
https://www.szeyes.com/index.php/vod/tldg.html
https://www.szeyes.com/index.php/vod/rldyqnd.html
https://www.szeyes.com/index.php/vod/pmpxm.html
https://www.szeyes.com/index.php/vod/mdlbzfwy.html
https://www.szeyes.com/index.php/vod/ntps.html
https://www.szeyes.com/index.php/vod/qbnysz.html
https://www.szeyes.com/index.php/vod/ntjs.html
https://www.szeyes.com/index.php/vod/lnygmgz.html
https://www.szeyes.com/index.php/vod/cchnz.html
https://www.szeyes.com/index.php/vod/kgcwhz.html
https://www.szeyes.com/index.php/vod/thwy.html
https://www.szeyes.com/index.php/vod/hbmt.html
https://www.szeyes.com/index.php/vod/zcmgjkgm.html
https://www.szeyes.com/index.php/vod/xklzdr.html
https://www.szeyes.com/index.php/vod/nhxd.html
https://www.szeyes.com/index.php/vod/qkphyq.html
https://www.szeyes.com/index.php/vod/sktnmmjs.html
https://www.szeyes.com/index.php/vod/wrwph.html
https://www.szeyes.com/index.php/vod/rfwydkb.html
https://www.szeyes.com/index.php/vod/ffcfxdy.html
https://www.szeyes.com/index.php/vod/jnfnr.html
https://www.szeyes.com/index.php/vod/bpnr.html
https://www.szeyes.com/index.php/vod/nhdw.html
https://www.szeyes.com/index.php/vod/wygmf.html
https://www.szeyes.com/index.php/vod/kdxnxt.html
https://www.szeyes.com/index.php/vod/rjrmwmj.html
https://www.szeyes.com/index.php/vod/fbthjyt.html
https://www.szeyes.com/index.php/vod/rqgfpyh.html
https://www.szeyes.com/index.php/vod/qpnblk.html
https://www.szeyes.com/index.php/vod/ssychpwc.html
https://www.szeyes.com/index.php/vod/rrcslzz.html
https://www.szeyes.com/index.php/vod/ztfdmtct.html
https://www.szeyes.com/index.php/vod/hkty.html
https://www.szeyes.com/index.php/vod/zynxsdhz.html
https://www.szeyes.com/index.php/vod/wbltm.html
https://www.szeyes.com/index.php/vod/dhwznm.html
https://www.szeyes.com/index.php/vod/bysl.html
https://www.szeyes.com/index.php/vod/nqld.html
https://www.szeyes.com/index.php/vod/tmtl.html
https://www.szeyes.com/index.php/vod/xbkksn.html
https://www.szeyes.com/index.php/vod/qmdyzw.html
https://www.szeyes.com/index.php/vod/ndzy.html
https://www.szeyes.com/index.php/vod/lrctmxg.html
https://www.szeyes.com/index.php/vod/ntcl.html
https://www.szeyes.com/index.php/vod/clgpw.html
https://www.szeyes.com/index.php/vod/zkqfmpxr.html
https://www.szeyes.com/index.php/vod/cbzyx.html
https://www.szeyes.com/index.php/vod/zdbybxrl.html
https://www.szeyes.com/index.php/vod/nqhp.html
https://www.szeyes.com/index.php/vod/lcmgrhq.html
https://www.szeyes.com/index.php/vod/tthw.html
https://www.szeyes.com/index.php/vod/chdnx.html
https://www.szeyes.com/index.php/vod/zxwqwxgs.html
https://www.szeyes.com/index.php/vod/cjmmp.html
https://www.szeyes.com/index.php/vod/dlwrgt.html
https://www.szeyes.com/index.php/vod/bfds.html
https://www.szeyes.com/index.php/vod/djklsj.html
https://www.szeyes.com/index.php/vod/lhxtjzt.html
https://www.szeyes.com/index.php/vod/rzjhytz.html
https://www.szeyes.com/index.php/vod/fcqtrxb.html
https://www.szeyes.com/index.php/vod/dfdzgj.html
https://www.szeyes.com/index.php/vod/qmsfkw.html
https://www.szeyes.com/index.php/vod/skxqyclw.html
https://www.szeyes.com/index.php/vod/gltndchq.html
https://www.szeyes.com/index.php/vod/khxydc.html
https://www.szeyes.com/index.php/vod/mdfddtzh.html
https://www.szeyes.com/index.php/vod/fdjdnqf.html
https://www.szeyes.com/index.php/vod/xykftq.html
https://www.szeyes.com/index.php/vod/byhb.html
https://www.szeyes.com/index.php/vod/dxyqnw.html
https://www.szeyes.com/index.php/vod/rlqbmdw.html
https://www.szeyes.com/index.php/vod/zqkxhlpg.html
https://www.szeyes.com/index.php/vod/rngqzbw.html
https://www.szeyes.com/index.php/vod/kympsn.html
https://www.szeyes.com/index.php/vod/bkqb.html
https://www.szeyes.com/index.php/vod/sbmzlhmr.html
https://www.szeyes.com/index.php/vod/ldljjgp.html
https://www.szeyes.com/index.php/vod/ntbh.html
https://www.szeyes.com/index.php/vod/tfdb.html
https://www.szeyes.com/index.php/vod/cgwmr.html
https://www.szeyes.com/index.php/vod/lwxgxsz.html
https://www.szeyes.com/index.php/vod/jjtrz.html
https://www.szeyes.com/index.php/vod/bbwq.html
https://www.szeyes.com/index.php/vod/dxybhz.html
https://www.szeyes.com/index.php/vod/rsljzrq.html
https://www.szeyes.com/index.php/vod/zbfftdnn.html
https://www.szeyes.com/index.php/vod/cccnm.html
https://www.szeyes.com/index.php/vod/pgsbh.html
https://www.szeyes.com/index.php/vod/yrycyfb.html
https://www.szeyes.com/index.php/vod/bktr.html
https://www.szeyes.com/index.php/vod/plnhz.html
https://www.szeyes.com/index.php/vod/hypk.html
https://www.szeyes.com/index.php/vod/kwnjkd.html
https://www.szeyes.com/index.php/vod/hzph.html
https://www.szeyes.com/index.php/vod/sdrtkgyb.html
https://www.szeyes.com/index.php/vod/wplww.html
https://www.szeyes.com/index.php/vod/scflkhnd.html
https://www.szeyes.com/index.php/vod/qxjjxj.html
https://www.szeyes.com/index.php/vod/czfqm.html
https://www.szeyes.com/index.php/vod/pklgf.html
https://www.szeyes.com/index.php/vod/jkxyc.html
https://www.szeyes.com/index.php/vod/bspd.html
https://www.szeyes.com/index.php/vod/djflgj.html
https://www.szeyes.com/index.php/vod/gstkfrtg.html
https://www.szeyes.com/index.php/vod/fdbjdrr.html
https://www.szeyes.com/index.php/vod/rygrflc.html
https://www.szeyes.com/index.php/vod/pftnk.html
https://www.szeyes.com/index.php/vod/cqcrz.html
https://www.szeyes.com/index.php/vod/wjbnw.html
https://www.szeyes.com/index.php/vod/dqptgk.html
https://www.szeyes.com/index.php/vod/qhczwr.html
https://www.szeyes.com/index.php/vod/yfnqqmz.html
https://www.szeyes.com/index.php/vod/gwqchrjc.html
https://www.szeyes.com/index.php/vod/jmzlh.html
https://www.szeyes.com/index.php/vod/hzkg.html
https://www.szeyes.com/index.php/vod/pxrnq.html
https://www.szeyes.com/index.php/vod/cjdtq.html
https://www.szeyes.com/index.php/vod/tkbw.html
https://www.szeyes.com/index.php/vod/dfkwpb.html
https://www.szeyes.com/index.php/vod/wsmxq.html
https://www.szeyes.com/index.php/vod/cypxh.html
https://www.szeyes.com/index.php/vod/zswjmghf.html
https://www.szeyes.com/index.php/vod/xtcfjk.html
https://www.szeyes.com/index.php/vod/kdnryg.html
https://www.szeyes.com/index.php/vod/bkkp.html
https://www.szeyes.com/index.php/vod/njcn.html
https://www.szeyes.com/index.php/vod/qbsycl.html
https://www.szeyes.com/index.php/vod/jtslf.html
https://www.szeyes.com/index.php/vod/psrrj.html
https://www.szeyes.com/index.php/vod/csjlj.html
https://www.szeyes.com/index.php/vod/sfsnhzly.html
https://www.szeyes.com/index.php/vod/qmrfjw.html
https://www.szeyes.com/index.php/vod/dnctpj.html
https://www.szeyes.com/index.php/vod/lgkfdms.html
https://www.szeyes.com/index.php/vod/zmfdbdqs.html
https://www.szeyes.com/index.php/vod/hgpj.html
https://www.szeyes.com/index.php/vod/tsxl.html
https://www.szeyes.com/index.php/vod/hjkk.html
https://www.szeyes.com/index.php/vod/qggzpk.html
https://www.szeyes.com/index.php/vod/jrhkf.html
https://www.szeyes.com/index.php/vod/tmsd.html
https://www.szeyes.com/index.php/vod/hhhx.html
https://www.szeyes.com/index.php/vod/fjfwsgf.html
https://www.szeyes.com/index.php/vod/hplw.html
https://www.szeyes.com/index.php/vod/jwsjc.html
https://www.szeyes.com/index.php/vod/wrldm.html
https://www.szeyes.com/index.php/vod/ssgttbwx.html
https://www.szeyes.com/index.php/vod/qxjdmp.html
https://www.szeyes.com/index.php/vod/xzcjky.html
https://www.szeyes.com/index.php/vod/pcflq.html
https://www.szeyes.com/index.php/vod/bjgd.html
https://www.szeyes.com/index.php/vod/jncrl.html
https://www.szeyes.com/index.php/vod/bzpb.html
https://www.szeyes.com/index.php/vod/dcwyzx.html
https://www.szeyes.com/index.php/vod/hbzp.html
https://www.szeyes.com/index.php/vod/phskk.html
https://www.szeyes.com/index.php/vod/xwknnl.html
https://www.szeyes.com/index.php/vod/pzzbc.html
https://www.szeyes.com/index.php/vod/jksnj.html
https://www.szeyes.com/index.php/vod/gkjlbpyw.html
https://www.szeyes.com/index.php/vod/hgdn.html
https://www.szeyes.com/index.php/vod/flxfmsq.html
https://www.szeyes.com/index.php/vod/xllgqr.html
https://www.szeyes.com/index.php/vod/kxdmtb.html
https://www.szeyes.com/index.php/vod/lstbpkm.html
https://www.szeyes.com/index.php/vod/yhmfckn.html
https://www.szeyes.com/index.php/vod/bffg.html
https://www.szeyes.com/index.php/vod/snjzdkky.html
https://www.szeyes.com/index.php/vod/fwzrpfr.html
https://www.szeyes.com/index.php/vod/xfptdj.html
https://www.szeyes.com/index.php/vod/jnrkd.html
https://www.szeyes.com/index.php/vod/lgwhggt.html
https://www.szeyes.com/index.php/vod/dkwfkm.html
https://www.szeyes.com/index.php/vod/gdcbfsjd.html
https://www.szeyes.com/index.php/vod/kyjqfb.html
https://www.szeyes.com/index.php/vod/hlxd.html
https://www.szeyes.com/index.php/vod/ttrf.html
https://www.szeyes.com/index.php/vod/rgntnym.html
https://www.szeyes.com/index.php/vod/bpqc.html
https://www.szeyes.com/index.php/vod/dkdfdm.html
https://www.szeyes.com/index.php/vod/fjpcypy.html
https://www.szeyes.com/index.php/vod/xnzxff.html
https://www.szeyes.com/index.php/vod/kjlkqs.html
https://www.szeyes.com/index.php/vod/hlzj.html
https://www.szeyes.com/index.php/vod/dkxfct.html
https://www.szeyes.com/index.php/vod/grqmdstm.html
https://www.szeyes.com/index.php/vod/jwzdk.html
https://www.szeyes.com/index.php/vod/qmdlxm.html
https://www.szeyes.com/index.php/vod/rsbscdd.html
https://www.szeyes.com/index.php/vod/tcgg.html
https://www.szeyes.com/index.php/vod/gxfgdsjd.html
https://www.szeyes.com/index.php/vod/sqtszjqc.html
https://www.szeyes.com/index.php/vod/lrrdlzn.html
https://www.szeyes.com/index.php/vod/ngfd.html
https://www.szeyes.com/index.php/vod/cktcd.html
https://www.szeyes.com/index.php/vod/kmlpwq.html
https://www.szeyes.com/index.php/vod/rmkyqxd.html
https://www.szeyes.com/index.php/vod/fdtstzd.html
https://www.szeyes.com/index.php/vod/dqbppm.html

## 项目结构

```
nexus-index/
├── src/                           # 源代码主目录
│   ├── core/                      # 核心功能模块
│   │   ├── indexer.js             # 索引构建与更新逻辑
│   │   ├── validator.js           # URL 格式校验与规范化
│   │   └── deduper.js             # 链接去重与合并算法
│   ├── api/                       # HTTP 接口层
│   │   ├── routes.js              # 路由定义与请求分发
│   │   ├── controllers.js         # 控制器实现，处理请求与响应
│   │   └── middleware.js          # 鉴权、日志、限流中间件
│   ├── scheduler/                 # 定时任务调度
│   │   ├──巡检任务.js             # 链接可达性周期巡检
│   │   └──报告生成器.js           # 巡检结果汇总与通知
│   ├── utils/                     # 工具函数集
│   │   ├── logger.js              # 结构化日志输出
│   │   ├── config.js              # 配置读取与合并
│   │   └── exporter.js            # JSON/CSV 导出工具
│   └── cli/                       # 命令行入口
│       ├── import.js              # 批量导入命令
│       └── check.js               # 手动触发巡检命令
├── config/                        # 配置文件目录
│   ├── default.yaml               # 默认配置参数
│   └── production.yaml            # 生产环境覆盖配置
├── data/                          # 数据存储目录
│   ├── index.db                   # SQLite 主数据库文件
│   └── changelog/                 # 变更日志归档
├── docs/                          # 文档目录
│   ├── user-guide.md              # 用户手册
│   ├── admin-guide.md             # 管理员指南
│   └── api-reference.md           # API 接口文档
├── tests/                         # 测试套件
│   ├── unit/                      # 单元测试用例
│   └── integration/               # 集成测试用例
├── scripts/                       # 运维辅助脚本
│   ├── backup.sh                  # 数据库备份脚本
│   └── migrate.sh                 # 数据库迁移脚本
├── package.json                   # Node.js 项目清单
├── README.md                      # 项目说明文档
└── LICENSE                        # MIT 许可证文件
```

## 贡献指南

1. 在 GitHub 上 fork 本仓库至个人账户，随后 clone 到本地开发环境。建议在 dev 分支上开展所有修改工作，避免直接操作 main 分支。

2. 新增链接条目时，请遵循 data/import_template.json 中定义的格式规范，确保 URL 字段完整且不含多余空白字符。若需引入新分类，须同步更新分类枚举定义文件。

3. 提交代码前，请先执行 npm run test 确保所有单元测试与集成测试通过，同时运行 npm run lint 进行代码风格检查。测试不通过或存在 lint 错误的提交将不被合并。

4. 提交信息请遵循 Conventional Commits 规范，格式为 `<type>(<scope>): <subject>`，其中 type 可选值包括 feat、fix、docs、style、refactor、test、chore。

5. 完成开发后，从 dev 分支发起 Pull Request 到上游仓库的 dev 分支。PR 描述中请清晰说明变更目的、涉及的功能模块以及相关的 issue 编号。

## 常见问题

**问：索引中的链接如果失效了怎么办？**

系统巡检任务默认每 24 小时执行一次，会对索引内所有链接发起 HEAD 请求检测状态码。连续三次检测均返回非 2xx 或 3xx 状态码的链接，将被标记为「失效」并移出主索引，同时记录至失效链接归档表中。管理员可通过后台管理界面手动恢复被误判的链接。

**问：如何批量导入自定义的链接列表？**

项目支持通过命令行工具进行批量导入。将链接列表整理为 JSON 数组格式，每条记录包含 url 和 tags 字段，然后执行 npm run import -- --file ./my-list.json 即可。导入工具会自动进行格式校验、去重处理，并输出导入结果统计报告。

**问：能否将索引部署为纯静态页面而不依赖 Node.js 服务？**

可以。项目提供了静态导出功能，执行 npm run export -- --static 命令后，系统会读取当前索引数据并生成一组 HTML 页面和对应的 JSON 数据文件，输出至 dist 目录。这些静态文件可托管至任何支持 HTTP 服务的环境，如 Nginx、Apache 或 CDN。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-06-23 23:54:08
