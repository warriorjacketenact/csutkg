# LinkVault 技术资源导航站

LinkVault 是一个面向开发者和技术研究人员的结构化外链资源汇总与导航系统。该项目致力于解决技术信息分散、优质外链难以系统化管理的问题，通过集中化的资源收录与分类索引机制，帮助用户快速定位特定领域的技术文档、案例分析与参考材料。

项目定位为轻量级的技术资源网关，适用于个人开发者、技术团队内部知识库构建以及开源社区的内容沉淀场景。LinkVault 不生产内容，而是提供一套标准化的外链收录、标注与检索框架，让分散在互联网各处的优质技术资料能够被有序组织和高效复用。

## 功能概览

**结构化资源收录**：基于预定义分类体系，将外链按技术领域、内容类型、适用阶段等维度进行标记与归档，支持多标签交叉检索。

**原始链接透传机制**：系统对用户提交的每一份原始 URL 进行完整保留与展示，确保资源来源的准确性和可追溯性，不做任何协议补全或域名改写。

**批量导入与解析**：支持通过文本列表或 CSV 文件批量导入外链，自动解析 URL 元信息，并生成预览摘要。

**自定义分类视图**：用户可根据自身需求创建分类标签与视图层级，将全局资源库映射为个人化的导航面板。

**只读镜像部署模式**：支持生成静态站点版本，适用于内网文档站或只读知识库的快速搭建。

**链接可用性监控**：周期性检查已收录链接的可访问状态，并标记异常项，辅助资源维护。

## 应用场景

技术团队内部知识库建设：团队可将日常开发中积累的参考文档、技术博客、API 手册等外链统一收录至 LinkVault，形成团队共享的技术雷达，降低信息孤岛与重复查找成本。

开源项目文档站配套：开源项目维护者可在项目文档中嵌入 LinkVault 生成的资源导航页，为贡献者与用户提供一站式外部参考资料入口。

个人技术学习路径管理：学习者可按主题（如分布式系统、前端工程化、数据库内核）整理收藏夹，配合分类视图追踪学习进度与拓展阅读材料。

技术会议与活动资料归档：在技术峰会或黑客松活动后，组织方可使用 LinkVault 汇总讲师 slides、相关论文、代码仓库链接，形成可长期访问的活动资料集。

## 快速开始

以下指令适用于 Linux / macOS 环境，Windows 用户建议通过 WSL 或 Git Bash 执行。

```bash
# 克隆代码仓库
git clone https://github.com/your-org/linkvault.git
cd linkvault

# 安装项目依赖（基于 Python 3.10+）
pip install -r requirements.txt

# 初始化数据库并导入示例资源列表
python manage.py initdb
python manage.py import --source ./data/sample_links.csv

# 启动本地开发服务器
python manage.py runserver --port 8080
```

启动成功后，访问 http://localhost:8080 即可看到资源导航主界面。如需生成静态站点，可执行 `python manage.py build --output ./dist`。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.10 或更高 | 核心运行环境，低于此版本将导致类型注解解析异常 |
| SQLite | 3.35 或更高 | 默认嵌入式数据库，用于存储资源条目与分类元数据 |
| Git | 2.25 或更高 | 仅开发阶段需要，用于版本管理与贡献代码拉取 |
| BeautifulSoup4 | 4.11.0 或更高 | 用于解析导入链接的 HTML 标题与描述信息 |
| requests | 2.28.0 或更高 | 处理链接可用性检查与远程资源元数据抓取 |
| markdown | 3.4.0 或更高 | 将资源注释与描述渲染为 HTML 格式（仅静态生成模式） |
| PyYAML | 6.0 或更高 | 解析分类配置文件与自定义视图定义 |
| gunicorn | 20.1.0 或更高 | 生产环境推荐部署服务器（Linux 平台） |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户指南 | /docs/user-guide/ | 如何添加资源、创建分类、导入导出数据、使用检索功能 |
| 管理员手册 | /docs/admin/ | 如何进行链接可用性检查、批量数据清洗、用户权限配置 |
| 开发者文档 | /docs/developer/ | API 接口定义、数据库表结构、自定义插件开发流程 |
| 部署运维 | /docs/deployment/ | 生产环境容器化部署、反向代理配置、静态站点生成策略 |

## 资源列表

本批次为第 528/1241 批资源导入，共计 250 条外链。以下列表按原始域名分组，所有链接均保持用户提交时的原始形式，未经任何协议补全或路径改写。

### 主域名资源（jiayingqiye.com 视频/详情路径）

https://www.jiayingqiye.com/vod/detail/mtjsmhbz.html
https://www.jiayingqiye.com/vod/detail/zybgcqgw.html
https://www.jiayingqiye.com/vod/detail/sfnrsmyq.html
https://www.jiayingqiye.com/vod/detail/bkqq.html
https://www.jiayingqiye.com/vod/detail/dkftkf.html
https://www.jiayingqiye.com/vod/detail/qsrnbx.html
https://www.jiayingqiye.com/vod/detail/fxthljg.html
https://www.jiayingqiye.com/vod/detail/mqsbtqjh.html
https://www.jiayingqiye.com/vod/detail/zqfjdrjl.html
https://www.jiayingqiye.com/vod/detail/cshrs.html
https://www.jiayingqiye.com/vod/detail/qbynxd.html
https://www.jiayingqiye.com/vod/detail/sfbsjxwb.html
https://www.jiayingqiye.com/vod/detail/rtsgxxs.html
https://www.jiayingqiye.com/vod/detail/zglxsckm.html
https://www.jiayingqiye.com/vod/detail/rkdycrs.html
https://www.jiayingqiye.com/vod/detail/pptdl.html
https://www.jiayingqiye.com/vod/detail/bttb.html
https://www.jiayingqiye.com/vod/detail/snngmwxx.html
https://www.jiayingqiye.com/vod/detail/gwhywkrp.html
https://www.jiayingqiye.com/vod/detail/nszc.html
https://www.jiayingqiye.com/vod/detail/pnmnq.html
https://www.jiayingqiye.com/vod/detail/xhfpsg.html
https://www.jiayingqiye.com/vod/detail/bkxq.html
https://www.jiayingqiye.com/vod/detail/ywkdgyf.html
https://www.jiayingqiye.com/vod/detail/qkxrkg.html
https://www.jiayingqiye.com/vod/detail/dwbpzh.html
https://www.jiayingqiye.com/vod/detail/cqgbl.html
https://www.jiayingqiye.com/vod/detail/thgp.html
https://www.jiayingqiye.com/vod/detail/hffx.html
https://www.jiayingqiye.com/vod/detail/pdgsw.html
https://www.jiayingqiye.com/vod/detail/nctr.html
https://www.jiayingqiye.com/vod/detail/bqzd.html
https://www.jiayingqiye.com/vod/detail/pdydc.html
https://www.jiayingqiye.com/vod/detail/cnrqq.html
https://www.jiayingqiye.com/vod/detail/kxwdkm.html
https://www.jiayingqiye.com/vod/detail/cxpzs.html
https://www.jiayingqiye.com/vod/detail/splqwbsf.html
https://www.jiayingqiye.com/vod/detail/wcytn.html
https://www.jiayingqiye.com/vod/detail/stmkyjlf.html
https://www.jiayingqiye.com/vod/detail/qcwmst.html
https://www.jiayingqiye.com/vod/detail/hwgw.html
https://www.jiayingqiye.com/vod/detail/zrgcqsfn.html
https://www.jiayingqiye.com/vod/detail/sknhypjw.html
https://www.jiayingqiye.com/vod/detail/bmmq.html
https://www.jiayingqiye.com/vod/detail/ddljlz.html
https://www.jiayingqiye.com/vod/detail/qmltxk.html
https://www.jiayingqiye.com/vod/detail/pcqrl.html
https://www.jiayingqiye.com/vod/detail/xwcblq.html
https://www.jiayingqiye.com/vod/detail/pwrfr.html
https://www.jiayingqiye.com/vod/detail/rhzwbhx.html
https://www.jiayingqiye.com/vod/detail/qyxmkb.html
https://www.jiayingqiye.com/vod/detail/yckrzck.html
https://www.jiayingqiye.com/vod/detail/xtmykn.html
https://www.jiayingqiye.com/vod/detail/ztfgcxsp.html
https://www.jiayingqiye.com/vod/detail/rtnxjrz.html
https://www.jiayingqiye.com/vod/detail/plpkc.html
https://www.jiayingqiye.com/vod/detail/qjslhm.html
https://www.jiayingqiye.com/vod/detail/yhzqlpl.html
https://www.jiayingqiye.com/vod/detail/lyxpqbp.html
https://www.jiayingqiye.com/vod/detail/jsbyb.html
https://www.jiayingqiye.com/vod/detail/tgtc.html
https://www.jiayingqiye.com/vod/detail/xssqkd.html
https://www.jiayingqiye.com/vod/detail/wtddb.html
https://www.jiayingqiye.com/vod/detail/smhwmsmk.html
https://www.jiayingqiye.com/vod/detail/qxwzdc.html
https://www.jiayingqiye.com/vod/detail/jdgsz.html
https://www.jiayingqiye.com/vod/detail/mlcfrdhh.html
https://www.jiayingqiye.com/vod/detail/plnjw.html
https://www.jiayingqiye.com/vod/detail/rrhnjhl.html
https://www.jiayingqiye.com/vod/detail/kbkwhz.html
https://www.jiayingqiye.com/vod/detail/jzswk.html
https://www.jiayingqiye.com/vod/detail/lrnjkxt.html
https://www.jiayingqiye.com/vod/detail/qmfpsh.html
https://www.jiayingqiye.com/vod/detail/ncdw.html
https://www.jiayingqiye.com/vod/detail/ldmcwgd.html
https://www.jiayingqiye.com/vod/detail/sdgjbfqk.html
https://www.jiayingqiye.com/vod/detail/xtxmgm.html
https://www.jiayingqiye.com/vod/detail/khcyyz.html
https://www.jiayingqiye.com/vod/detail/mflrfcdy.html
https://www.jiayingqiye.com/vod/detail/zwzfkygh.html
https://www.jiayingqiye.com/vod/detail/dpwqjc.html
https://www.jiayingqiye.com/vod/detail/bfky.html
https://www.jiayingqiye.com/vod/detail/ckdxx.html
https://www.jiayingqiye.com/vod/detail/ttnp.html
https://www.jiayingqiye.com/vod/detail/cgcff.html
https://www.jiayingqiye.com/vod/detail/fqqqwgk.html
https://www.jiayingqiye.com/vod/detail/bjhp.html
https://www.jiayingqiye.com/vod/detail/jwwdk.html
https://www.jiayingqiye.com/vod/detail/gfhdfwxk.html
https://www.jiayingqiye.com/vod/detail/ndbf.html
https://www.jiayingqiye.com/vod/detail/zphsxlnp.html
https://www.jiayingqiye.com/vod/detail/hstl.html
https://www.jiayingqiye.com/vod/detail/nhql.html
https://www.jiayingqiye.com/vod/detail/ltqbdrh.html
https://www.jiayingqiye.com/vod/detail/yslbxhs.html
https://www.jiayingqiye.com/vod/detail/gyyqdwkh.html
https://www.jiayingqiye.com/vod/detail/kshprn.html
https://www.jiayingqiye.com/vod/detail/hltm.html
https://www.jiayingqiye.com/vod/detail/tbjf.html
https://www.jiayingqiye.com/vod/detail/xwzytp.html
https://www.jiayingqiye.com/vod/detail/ldfyznl.html
https://www.jiayingqiye.com/vod/detail/sjqgsqjr.html
https://www.jiayingqiye.com/vod/detail/zxtslgcg.html
https://www.jiayingqiye.com/vod/detail/xqqbxr.html
https://www.jiayingqiye.com/vod/detail/pbjqn.html
https://www.jiayingqiye.com/vod/detail/xyjggx.html
https://www.jiayingqiye.com/vod/detail/nhzb.html
https://www.jiayingqiye.com/vod/detail/lkyrtzs.html
https://www.jiayingqiye.com/vod/detail/ntjr.html
https://www.jiayingqiye.com/vod/detail/qnwzgj.html
https://www.jiayingqiye.com/vod/detail/mrzkhnjs.html
https://www.jiayingqiye.com/vod/detail/ppwmt.html
https://www.jiayingqiye.com/vod/detail/wwndt.html
https://www.jiayingqiye.com/vod/detail/ydnzllg.html
https://www.jiayingqiye.com/vod/detail/wkhty.html
https://www.jiayingqiye.com/vod/detail/yycppzw.html
https://www.jiayingqiye.com/vod/detail/xjkyjh.html
https://www.jiayingqiye.com/vod/detail/ptcxz.html
https://www.jiayingqiye.com/vod/detail/xcphpd.html
https://www.jiayingqiye.com/vod/detail/flbzcsj.html
https://www.jiayingqiye.com/vod/detail/drlklc.html
https://www.jiayingqiye.com/vod/detail/lskqzcn.html
https://www.jiayingqiye.com/vod/detail/rdhthjr.html
https://www.jiayingqiye.com/vod/detail/ptkng.html
https://www.jiayingqiye.com/vod/detail/cmqbm.html
https://www.jiayingqiye.com/vod/detail/zfbfpcyb.html
https://www.jiayingqiye.com/vod/detail/wkbpp.html
https://www.jiayingqiye.com/vod/detail/jksym.html
https://www.jiayingqiye.com/vod/detail/wwwrx.html
https://www.jiayingqiye.com/vod/detail/ygzsczf.html
https://www.jiayingqiye.com/vod/detail/tywy.html
https://www.jiayingqiye.com/vod/detail/mqkqnlfk.html
https://www.jiayingqiye.com/vod/detail/jlsph.html
https://www.jiayingqiye.com/vod/detail/wjkcl.html
https://www.jiayingqiye.com/vod/detail/djscws.html
https://www.jiayingqiye.com/vod/detail/wlljd.html
https://www.jiayingqiye.com/vod/detail/flmknjm.html
https://www.jiayingqiye.com/vod/detail/ctnqz.html
https://www.jiayingqiye.com/vod/detail/zbnbyxfl.html
https://www.jiayingqiye.com/vod/detail/ccdhx.html
https://www.jiayingqiye.com/vod/detail/bsbx.html
https://www.jiayingqiye.com/vod/detail/ddbkms.html
https://www.jiayingqiye.com/vod/detail/ftrnmpn.html
https://www.jiayingqiye.com/vod/detail/rmqpbhd.html
https://www.jiayingqiye.com/vod/detail/kcstjk.html
https://www.jiayingqiye.com/vod/detail/chlgc.html
https://www.jiayingqiye.com/vod/detail/dqdbdq.html
https://www.jiayingqiye.com/vod/detail/bqjl.html
https://www.jiayingqiye.com/vod/detail/ycrrbrt.html
https://www.jiayingqiye.com/vod/detail/bytr.html
https://www.jiayingqiye.com/vod/detail/xfdsmp.html
https://www.jiayingqiye.com/vod/detail/tzhx.html
https://www.jiayingqiye.com/vod/detail/lczmsyn.html
https://www.jiayingqiye.com/vod/detail/jwdjl.html
https://www.jiayingqiye.com/vod/detail/wqymj.html
https://www.jiayingqiye.com/vod/detail/yqfdtlp.html
https://www.jiayingqiye.com/vod/detail/rzlxmcc.html
https://www.jiayingqiye.com/vod/detail/kkqpnc.html
https://www.jiayingqiye.com/vod/detail/xzshqb.html
https://www.jiayingqiye.com/vod/detail/kqflcw.html
https://www.jiayingqiye.com/vod/detail/npbk.html
https://www.jiayingqiye.com/vod/detail/qwyjqt.html
https://www.jiayingqiye.com/vod/detail/mmcfgtmg.html
https://www.jiayingqiye.com/vod/detail/ksjymp.html
https://www.jiayingqiye.com/vod/detail/xcdsjk.html
https://www.jiayingqiye.com/vod/detail/zcxmqngt.html
https://www.jiayingqiye.com/vod/detail/bknt.html
https://www.jiayingqiye.com/vod/detail/jrllg.html
https://www.jiayingqiye.com/vod/detail/wbbpm.html
https://www.jiayingqiye.com/vod/detail/yxngcwh.html
https://www.jiayingqiye.com/vod/detail/tkzl.html
https://www.jiayingqiye.com/vod/detail/cccdt.html
https://www.jiayingqiye.com/vod/detail/pgfyf.html
https://www.jiayingqiye.com/vod/detail/rzwswkg.html
https://www.jiayingqiye.com/vod/detail/fsdxwzr.html
https://www.jiayingqiye.com/vod/detail/xknyjr.html
https://www.jiayingqiye.com/vod/detail/sbrjzrlk.html
https://www.jiayingqiye.com/vod/detail/lzlxfqt.html
https://www.jiayingqiye.com/vod/detail/ymyhwzs.html
https://www.jiayingqiye.com/vod/detail/wpkhw.html
https://www.jiayingqiye.com/vod/detail/rjdmzcj.html
https://www.jiayingqiye.com/vod/detail/txpx.html
https://www.jiayingqiye.com/vod/detail/nnnn.html
https://www.jiayingqiye.com/vod/detail/ggslwycj.html
https://www.jiayingqiye.com/vod/detail/jkczl.html
https://www.jiayingqiye.com/vod/detail/qlrddj.html
https://www.jiayingqiye.com/vod/detail/kwryxg.html
https://www.jiayingqiye.com/vod/detail/cgklf.html
https://www.jiayingqiye.com/vod/detail/fsxmlxh.html
https://www.jiayingqiye.com/vod/detail/ctbwm.html
https://www.jiayingqiye.com/vod/detail/lqrhfdd.html
https://www.jiayingqiye.com/vod/detail/ywbjzzc.html
https://www.jiayingqiye.com/vod/detail/rfftwck.html
https://www.jiayingqiye.com/vod/detail/fwnhqbh.html
https://www.jiayingqiye.com/vod/detail/rkbhpwr.html
https://www.jiayingqiye.com/vod/detail/tymr.html
https://www.jiayingqiye.com/vod/detail/gglghxkm.html
https://www.jiayingqiye.com/vod/detail/sbygnbkf.html
https://www.jiayingqiye.com/vod/detail/lxpfwqx.html
https://www.jiayingqiye.com/vod/detail/jxsgn.html
https://www.jiayingqiye.com/vod/detail/zhhtlfrf.html
https://www.jiayingqiye.com/vod/detail/hmfn.html
https://www.jiayingqiye.com/vod/detail/qgshzf.html
https://www.jiayingqiye.com/vod/detail/ybxwxbf.html
https://www.jiayingqiye.com/vod/detail/wpjtg.html
https://www.jiayingqiye.com/vod/detail/scmwphrq.html
https://www.jiayingqiye.com/vod/detail/xrjzzp.html
https://www.jiayingqiye.com/vod/detail/pzjzq.html
https://www.jiayingqiye.com/vod/detail/rzbwycy.html
https://www.jiayingqiye.com/vod/detail/tznb.html
https://www.jiayingqiye.com/vod/detail/dkqcfl.html
https://www.jiayingqiye.com/vod/detail/wsypx.html
https://www.jiayingqiye.com/vod/detail/fpzwtwz.html
https://www.jiayingqiye.com/vod/detail/rdgshdw.html
https://www.jiayingqiye.com/vod/detail/zkrsnsnt.html
https://www.jiayingqiye.com/vod/detail/dmpqkx.html
https://www.jiayingqiye.com/vod/detail/gtcndqyw.html
https://www.jiayingqiye.com/vod/detail/dgkxkp.html
https://www.jiayingqiye.com/vod/detail/qrjmwf.html
https://www.jiayingqiye.com/vod/detail/hkyr.html
https://www.jiayingqiye.com/vod/detail/zjsqdttg.html
https://www.jiayingqiye.com/vod/detail/nljj.html
https://www.jiayingqiye.com/vod/detail/qhmhpz.html
https://www.jiayingqiye.com/vod/detail/scfgrzhm.html
https://www.jiayingqiye.com/vod/detail/qztfcs.html
https://www.jiayingqiye.com/vod/detail/pxhgx.html
https://www.jiayingqiye.com/vod/detail/rtbkwkw.html
https://www.jiayingqiye.com/vod/detail/pyhgy.html
https://www.jiayingqiye.com/vod/detail/csmrk.html
https://www.jiayingqiye.com/vod/detail/wgtqq.html
https://www.jiayingqiye.com/vod/detail/ywncdrz.html
https://www.jiayingqiye.com/vod/detail/rhwhmgg.html
https://www.jiayingqiye.com/vod/detail/zwgbrcqw.html
https://www.jiayingqiye.com/vod/detail/mwnntggj.html
https://www.jiayingqiye.com/vod/detail/txzw.html
https://www.jiayingqiye.com/vod/detail/qpfbzy.html
https://www.jiayingqiye.com/vod/detail/jjmqq.html
https://www.jiayingqiye.com/vod/detail/ghxggqgf.html
https://www.jiayingqiye.com/vod/detail/ysnnrwt.html
https://www.jiayingqiye.com/vod/detail/zgqdfypj.html
https://www.jiayingqiye.com/vod/detail/hfqj.html
https://www.jiayingqiye.com/vod/detail/bsgx.html
https://www.jiayingqiye.com/vod/detail/dnjwkm.html
https://www.jiayingqiye.com/vod/detail/gdlgypzk.html
https://www.jiayingqiye.com/vod/detail/jgcnl.html
https://www.jiayingqiye.com/vod/detail/ctnqk.html
https://www.jiayingqiye.com/vod/detail/zjdyhdxn.html
https://www.jiayingqiye.com/vod/detail/rmclzqb.html
https://www.jiayingqiye.com/vod/detail/psdyx.html
https://www.jiayingqiye.com/vod/detail/ygkjxzg.html

## 项目结构

```
linkvault/
├── cmd/
│   └── linkvault/                # 主程序入口与命令行工具
│       ├── main.go               # 服务启动入口
│       └── commands.go           # 子命令定义（import, build, check）
├── internal/
│   ├── core/                     # 核心业务逻辑模块
│   │   ├── link.go               # 链接实体结构与校验逻辑
│   │   ├── classifier.go         # 分类标签树管理
│   │   └── importer.go           # 批量导入解析器（支持 CSV / TSV）
│   ├── storage/                  # 持久化层
│   │   ├── sqlite.go             # SQLite 驱动适配与迁移
│   │   └── models.go             # 数据表模型定义
│   └── monitor/                  # 链接可用性监控模块
│       ├── checker.go            # HTTP 状态轮询与超时控制
│       └── reporter.go           # 异常记录与告警汇总
├── pkg/
│   ├── utils/                    # 通用工具函数库
│   │   ├── url.go                # URL 清洗、域名提取
│   │   └── hash.go               # 链接去重哈希计算
│   └── render/                   # 静态渲染引擎
│       ├── template.go           # 模板加载与缓存
│       └── page.go               # 分类视图与列表页生成
├── web/
│   ├── static/                   # 前端静态资产（CSS, JS）
│   │   ├── style.css
│   │   └── app.js
│   └── templates/                # 页面模板（Go template）
│       ├── index.html
│       ├── category.html
│       └── detail.html
├── config/
│   └── default.yaml              # 默认配置（端口、监控间隔、分类预设）
├── data/
│   ├── sample_links.csv          # 示例导入数据
│   └── migrations/               # 数据库迁移脚本
├── docs/                         # 完整文档目录（见文档导航章节）
├── go.mod                        # Go 模块依赖定义
├── go.sum
├── Makefile                      # 构建与测试自动化脚本
└── README.md                     # 本文件
```

## 贡献指南

1. 阅读项目行为准则与贡献者协议，确认知悉开源社区协作规范，并在首次提交 PR 时签署 CLA（Contributor License Agreement）。

2. 从 Issue 列表中选择标注为 `good-first-issue` 或 `help-wanted` 的任务，在评论中表明认领意向，等待维护者分配以避免重复工作。

3. 本地开发环境准备：Fork 主仓库至个人账号，克隆后创建以 `feature/` 或 `fix/` 为前缀的功能分支，遵循项目已配置的 golangci-lint 规则与测试覆盖率要求（不低于 80%）。

4. 提交变更时使用约定式提交格式（如 `feat: add batch import progress bar` 或 `fix: correct URL scheme normalization`），确保 commit message 清晰可追溯。

5. 发起 Pull Request 时填写变更摘要、测试结果、影响范围三部分内容，并关联相关 Issue 编号。PR 需要至少一名维护者审阅通过后合并。

## 常见问题

**Q：导入链接时提示“URL 格式无效”，但我的链接在浏览器中可以正常访问，是什么原因？**

A：LinkVault 默认对链接进行严格格式校验，要求必须包含协议头（http:// 或 https://）。如果您的链接为裸域名格式（如 `example.com`），请补全为 `https://example.com` 后再导入。同时，系统会拒绝包含未编码空格或非法字符的 URL，建议使用浏览器复制功能获取原始链接地址。

**Q：静态站点生成模式与动态服务模式有何区别？我应该如何选择？**

A：动态服务模式适用于需要频繁更新资源列表、使用分类管理后台或启用链接监控的场景，数据存储在 SQLite 中，支持在线编辑。静态站点生成模式则将所有页面预渲染为 HTML 文件，适合部署在对象存储或 CDN 上，不具备写入能力但访问速度更快、安全性更高。若您的资源列表相对稳定且访问量较大，推荐使用静态模式。

**Q：如何批量更新已有链接的分类标签？**

A：您可以通过 `import` 命令的 `--update` 参数重新导入一份包含相同链接但标签列不同的 CSV 文件。系统会依据链接哈希值匹配已有记录，仅覆盖分类字段，不新增重复条目。具体操作可参考 `/docs/admin/batch-update.md` 文档。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-06-23 23:56:04
