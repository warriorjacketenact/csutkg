# ResourceBridge 技术外链聚合与引用管理系统

ResourceBridge 是一个面向技术团队、文档维护者与知识管理工程师的轻量级外链聚合与引用管理工具。项目定位为技术资源导航与外部参考链接的集中治理平台，主要解决技术文档、项目手册、法律合规资料以及研究笔记中外部链接分散、失效风险高、引用格式混乱、缺乏统一管理入口等问题。通过结构化的资源录入、分类索引与状态监控，ResourceBridge 帮助团队建立可维护、可追溯、可共享的外部信息资产池。

目标用户包括技术文档工程师、开源项目维护者、法律与合规事务专员、科研助理以及需要长期管理大量外链引用的内容运营人员。项目不提供复杂的数据库后端，而是基于静态目录结构与标记文件，配合自动化检查脚本，实现高透明度的链接资产管理方案。

## 功能概览

**批量链接导入与结构化存储** 支持通过 CSV 或 JSON 格式批量导入外部链接，自动解析 URL、标题、来源域名与采集时间，按项目批次与类别生成统一的存储条目。

**链接可用性自动巡检** 内置轻量级 HTTP 状态检查工具，可定期对全部已收录链接执行可达性测试，输出失效链接报表，辅助管理员及时更新或移除死链。

**多维度分类与标签系统** 允许用户为每条链接添加自定义标签（如 "判例"、"技术规范"、"官方文档"、"新闻稿"），支持按标签、域名、收录批次进行快速筛选与分组统计。

**引用格式标准化输出** 根据用户选择的引文风格（如 APA、MLA、GB/T 7714），将链接条目连同元数据一键转换为规范化的引用文本，方便插入技术报告或法律意见书。

**资源变更历史追踪** 记录每条链接的收录时间、最后检查时间、备注修改记录，所有变更以文本日志形式保存在项目目录下，便于审计与回溯。

**交互式命令行管理界面** 提供一组简洁的 Shell 命令与交互式提示，允许用户在不打开编辑器的情况下完成链接添加、删除、状态查看与导出操作，适合服务器端或远程运维场景。

## 应用场景

技术文档版本更新时的外部参考校验 当技术白皮书或用户手册发布新版时，文档维护者可运行 ResourceBridge 的链接检查功能，快速定位所有失效或变更的外部引用，确保印刷版或 PDF 版文档中的超链接准确有效。

法律案例与法规汇编整理 法律团队在处理多起案件时，可将相关裁判文书、法规条文、行政解释的 URL 统一录入系统，按案件编号或法律领域分类，在撰写法律意见书或诉讼材料时直接生成标准引用。

开源项目 README 与网站资源导航维护 开源项目维护者可使用 ResourceBridge 管理项目文档中列举的社区论坛、插件仓库、镜像站点、技术博客等外部链接，定期检查可用性，避免用户因访问失效链接而产生困惑。

学术研究文献外部数据集索引 科研人员在收集实验数据、开源代码仓库、预印本论文时，可通过 ResourceBridge 建立外部资源索引，并将索引快照随论文附件一并提交，提升研究的可重复性。

## 快速开始

以下命令序列演示从克隆仓库到启动基础服务的完整流程。

```bash
git clone https://github.com/yourorg/resourcebridge.git
cd resourcebridge
make install
./bin/rbctl init --batch 1038/1241
./bin/rbctl import --source data/links_1038.json
./bin/rbctl check --all
./bin/rbctl list --tag episode
```

若使用 Docker 运行，可替换为以下命令：

```bash
docker pull yourorg/resourcebridge:latest
docker run -v $(pwd)/data:/app/data -p 8080:8080 resourcebridge serve
```

## 安装要求

| 依赖 | 必需版本 | 说明 |
|------|----------|------|
| Python | 3.9 或更高 | 核心运行时，用于 CLI 工具与检查脚本 |
| Git | 2.25 或更高 | 仓库克隆与版本管理 |
| Make | 3.82 或更高 | 构建与安装任务自动化 |
| curl | 7.68 或更高 | 链接可达性检查底层工具 |
| jq | 1.6 或更高 | JSON 数据处理与格式化输出 |
| Docker | 20.10 或更高 | 容器化部署（可选） |
| SQLite | 3.31 或更高 | 本地元数据存储引擎 |
| rsync | 3.2 或更高 | 数据同步与备份辅助工具 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 用户指南 | docs/user-guide/ | 如何安装、配置、导入链接、执行检查与导出引用格式 |
| 管理员手册 | docs/admin/ | 如何自定义分类体系、调整检查频率、备份数据与迁移仓库 |
| 开发者文档 | docs/developer/ | 如何扩展检查器、增加新输出格式、编写单元测试与提交补丁 |
| 参考手册 | docs/reference/ | 命令行参数详解、配置文件 schema、JSON 导入格式规范与错误代码说明 |

## 资源列表

本批次（第 1038/1241 批）共收录 250 个外部链接，全部来源于技术文档、法律案例与行业资讯站点。所有链接按原始提供形式原样列出，未做任何协议或域名改写。

判例与法律文书类

https://www.tanchenglvshi.com/episode/cr4283.html
https://www.tanchenglvshi.com/episode/od1189.html
https://www.tanchenglvshi.com/episode/ut0402.html
https://www.tanchenglvshi.com/episode/hr5794.html
https://www.tanchenglvshi.com/episode/ev4854.html
https://www.tanchenglvshi.com/episode/qb3695.html
https://www.tanchenglvshi.com/episode/og9696.html
https://www.tanchenglvshi.com/episode/et2958.html
https://www.tanchenglvshi.com/episode/cd7600.html
https://www.tanchenglvshi.com/episode/vv0816.html
https://www.tanchenglvshi.com/episode/iy4097.html
https://www.tanchenglvshi.com/episode/aw6016.html
https://www.tanchenglvshi.com/episode/zr9594.html
https://www.tanchenglvshi.com/episode/uj4579.html
https://www.tanchenglvshi.com/episode/uw4891.html
https://www.tanchenglvshi.com/episode/hu9846.html
https://www.tanchenglvshi.com/episode/pv6589.html
https://www.tanchenglvshi.com/episode/jm0431.html
https://www.tanchenglvshi.com/episode/yc2269.html
https://www.tanchenglvshi.com/episode/bf4038.html
https://www.tanchenglvshi.com/episode/ui3433.html
https://www.tanchenglvshi.com/episode/qc8319.html
https://www.tanchenglvshi.com/episode/sq5256.html
https://www.tanchenglvshi.com/episode/ut8315.html
https://www.tanchenglvshi.com/episode/ms6780.html
https://www.tanchenglvshi.com/episode/tl4650.html
https://www.tanchenglvshi.com/episode/bv5106.html
https://www.tanchenglvshi.com/episode/gf9480.html
https://www.tanchenglvshi.com/episode/ef1089.html
https://www.tanchenglvshi.com/episode/nh7262.html
https://www.tanchenglvshi.com/episode/fu0541.html
https://www.tanchenglvshi.com/episode/ia2212.html
https://www.tanchenglvshi.com/episode/fb7526.html
https://www.tanchenglvshi.com/episode/ll0459.html
https://www.tanchenglvshi.com/episode/js6338.html
https://www.tanchenglvshi.com/episode/iw1603.html
https://www.tanchenglvshi.com/episode/ig0594.html
https://www.tanchenglvshi.com/episode/om5847.html
https://www.tanchenglvshi.com/episode/fu2368.html
https://www.tanchenglvshi.com/episode/jk7017.html
https://www.tanchenglvshi.com/episode/sv3000.html
https://www.tanchenglvshi.com/episode/rm4759.html
https://www.tanchenglvshi.com/episode/ub2350.html
https://www.tanchenglvshi.com/episode/zo7419.html
https://www.tanchenglvshi.com/episode/er8213.html
https://www.tanchenglvshi.com/episode/gm1089.html
https://www.tanchenglvshi.com/episode/wr9832.html
https://www.tanchenglvshi.com/episode/ln8653.html
https://www.tanchenglvshi.com/episode/ua3899.html
https://www.tanchenglvshi.com/episode/zi2001.html
https://www.tanchenglvshi.com/episode/pr1687.html
https://www.tanchenglvshi.com/episode/et9011.html
https://www.tanchenglvshi.com/episode/pv7761.html
https://www.tanchenglvshi.com/episode/kl1793.html
https://www.tanchenglvshi.com/episode/za2163.html
https://www.tanchenglvshi.com/episode/ix7518.html
https://www.tanchenglvshi.com/episode/dq6534.html
https://www.tanchenglvshi.com/episode/qv4592.html
https://www.tanchenglvshi.com/episode/ob7889.html
https://www.tanchenglvshi.com/episode/yt4656.html
https://www.tanchenglvshi.com/episode/qa7369.html
https://www.tanchenglvshi.com/episode/cv9299.html
https://www.tanchenglvshi.com/episode/bm6815.html
https://www.tanchenglvshi.com/episode/eo1961.html
https://www.tanchenglvshi.com/episode/ev1973.html
https://www.tanchenglvshi.com/episode/ou7812.html
https://www.tanchenglvshi.com/episode/av3900.html
https://www.tanchenglvshi.com/episode/db0388.html
https://www.tanchenglvshi.com/episode/vx7059.html
https://www.tanchenglvshi.com/episode/dc1958.html
https://www.tanchenglvshi.com/episode/nh1905.html
https://www.tanchenglvshi.com/episode/lu2303.html
https://www.tanchenglvshi.com/episode/bw6474.html
https://www.tanchenglvshi.com/episode/pw9369.html
https://www.tanchenglvshi.com/episode/ba5836.html
https://www.tanchenglvshi.com/episode/cx6325.html
https://www.tanchenglvshi.com/episode/rb5202.html
https://www.tanchenglvshi.com/episode/tq8903.html
https://www.tanchenglvshi.com/episode/je0885.html
https://www.tanchenglvshi.com/episode/ht2545.html
https://www.tanchenglvshi.com/episode/fk7433.html
https://www.tanchenglvshi.com/episode/lu1524.html
https://www.tanchenglvshi.com/episode/xl6278.html
https://www.tanchenglvshi.com/episode/dt8230.html
https://www.tanchenglvshi.com/episode/xg3609.html
https://www.tanchenglvshi.com/episode/is9160.html
https://www.tanchenglvshi.com/episode/bz4584.html
https://www.tanchenglvshi.com/episode/ef6059.html
https://www.tanchenglvshi.com/episode/pz8541.html
https://www.tanchenglvshi.com/episode/fk5217.html
https://www.tanchenglvshi.com/episode/ym2111.html
https://www.tanchenglvshi.com/episode/rk0957.html
https://www.tanchenglvshi.com/episode/of2532.html
https://www.tanchenglvshi.com/episode/qp0066.html
https://www.tanchenglvshi.com/episode/yz7127.html
https://www.tanchenglvshi.com/episode/gh5662.html
https://www.tanchenglvshi.com/episode/ac3499.html
https://www.tanchenglvshi.com/episode/lk7476.html
https://www.tanchenglvshi.com/episode/ct6549.html
https://www.tanchenglvshi.com/episode/io4649.html
https://www.tanchenglvshi.com/episode/wy6776.html
https://www.tanchenglvshi.com/episode/bj5517.html
https://www.tanchenglvshi.com/episode/oo5368.html
https://www.tanchenglvshi.com/episode/ca9173.html
https://www.tanchenglvshi.com/episode/da0916.html
https://www.tanchenglvshi.com/episode/kk0823.html
https://www.tanchenglvshi.com/episode/iz0522.html
https://www.tanchenglvshi.com/episode/ij3998.html
https://www.tanchenglvshi.com/episode/gg5513.html
https://www.tanchenglvshi.com/episode/lx7748.html
https://www.tanchenglvshi.com/episode/yc2505.html
https://www.tanchenglvshi.com/episode/cn8491.html
https://www.tanchenglvshi.com/episode/uy2406.html
https://www.tanchenglvshi.com/episode/qe6213.html
https://www.tanchenglvshi.com/episode/fk5529.html
https://www.tanchenglvshi.com/episode/wd1480.html
https://www.tanchenglvshi.com/episode/mz3761.html
https://www.tanchenglvshi.com/episode/ni6976.html
https://www.tanchenglvshi.com/episode/av2559.html
https://www.tanchenglvshi.com/episode/sh4572.html
https://www.tanchenglvshi.com/episode/nj8431.html
https://www.tanchenglvshi.com/episode/xh4588.html
https://www.tanchenglvshi.com/episode/ea0586.html
https://www.tanchenglvshi.com/episode/yq2483.html
https://www.tanchenglvshi.com/episode/ff3225.html
https://www.tanchenglvshi.com/episode/uj3752.html
https://www.tanchenglvshi.com/episode/wc2638.html
https://www.tanchenglvshi.com/episode/uk2014.html
https://www.tanchenglvshi.com/episode/ts9665.html
https://www.tanchenglvshi.com/episode/nt8910.html
https://www.tanchenglvshi.com/episode/oc1210.html
https://www.tanchenglvshi.com/episode/ue3935.html
https://www.tanchenglvshi.com/episode/zj7361.html
https://www.tanchenglvshi.com/episode/hn6164.html
https://www.tanchenglvshi.com/episode/dw3622.html
https://www.tanchenglvshi.com/episode/zk3980.html
https://www.tanchenglvshi.com/episode/bc2732.html
https://www.tanchenglvshi.com/episode/kx7284.html
https://www.tanchenglvshi.com/episode/tx9758.html
https://www.tanchenglvshi.com/episode/yi2188.html
https://www.tanchenglvshi.com/episode/wb4565.html
https://www.tanchenglvshi.com/episode/vh2972.html
https://www.tanchenglvshi.com/episode/ub5981.html
https://www.tanchenglvshi.com/episode/uc3414.html
https://www.tanchenglvshi.com/episode/kh5082.html
https://www.tanchenglvshi.com/episode/ve6134.html
https://www.tanchenglvshi.com/episode/yu8791.html
https://www.tanchenglvshi.com/episode/fj1513.html
https://www.tanchenglvshi.com/episode/he5758.html
https://www.tanchenglvshi.com/episode/en6990.html
https://www.tanchenglvshi.com/episode/pc7580.html
https://www.tanchenglvshi.com/episode/vy7781.html
https://www.tanchenglvshi.com/episode/fo6372.html
https://www.tanchenglvshi.com/episode/mu9178.html
https://www.tanchenglvshi.com/episode/ki5563.html
https://www.tanchenglvshi.com/episode/fv1701.html
https://www.tanchenglvshi.com/episode/ab6810.html
https://www.tanchenglvshi.com/episode/gp3699.html
https://www.tanchenglvshi.com/episode/gx4858.html
https://www.tanchenglvshi.com/episode/sl9954.html
https://www.tanchenglvshi.com/episode/wk8194.html
https://www.tanchenglvshi.com/episode/zr9081.html
https://www.tanchenglvshi.com/episode/vq5474.html
https://www.tanchenglvshi.com/episode/jo1166.html
https://www.tanchenglvshi.com/episode/oc1322.html
https://www.tanchenglvshi.com/episode/nh6497.html
https://www.tanchenglvshi.com/episode/ck5354.html
https://www.tanchenglvshi.com/episode/ik6603.html
https://www.tanchenglvshi.com/episode/os8279.html
https://www.tanchenglvshi.com/episode/rd0622.html
https://www.tanchenglvshi.com/episode/ir9204.html
https://www.tanchenglvshi.com/episode/vg3260.html
https://www.tanchenglvshi.com/episode/wr2337.html
https://www.tanchenglvshi.com/episode/kq6440.html
https://www.tanchenglvshi.com/episode/ml3735.html
https://www.tanchenglvshi.com/episode/qv7005.html
https://www.tanchenglvshi.com/episode/ce8268.html
https://www.tanchenglvshi.com/episode/md5398.html
https://www.tanchenglvshi.com/episode/ct5986.html
https://www.tanchenglvshi.com/episode/uu0141.html
https://www.tanchenglvshi.com/episode/zd1778.html
https://www.tanchenglvshi.com/episode/qo8614.html
https://www.tanchenglvshi.com/episode/fz0243.html
https://www.tanchenglvshi.com/episode/yx0490.html
https://www.tanchenglvshi.com/episode/lf4533.html
https://www.tanchenglvshi.com/episode/za8537.html
https://www.tanchenglvshi.com/episode/ol9407.html
https://www.tanchenglvshi.com/episode/iu7548.html
https://www.tanchenglvshi.com/episode/po2377.html
https://www.tanchenglvshi.com/episode/pr5105.html
https://www.tanchenglvshi.com/episode/as9463.html
https://www.tanchenglvshi.com/episode/fo0797.html
https://www.tanchenglvshi.com/episode/jr0757.html
https://www.tanchenglvshi.com/episode/ar4272.html
https://www.tanchenglvshi.com/episode/rx3110.html
https://www.tanchenglvshi.com/episode/sd0700.html
https://www.tanchenglvshi.com/episode/nm3102.html
https://www.tanchenglvshi.com/episode/pn6913.html
https://www.tanchenglvshi.com/episode/nv3648.html
https://www.tanchenglvshi.com/episode/zc3553.html
https://www.tanchenglvshi.com/episode/fy5521.html
https://www.tanchenglvshi.com/episode/zn1697.html
https://www.tanchenglvshi.com/episode/nu8432.html
https://www.tanchenglvshi.com/episode/ob7800.html
https://www.tanchenglvshi.com/episode/fp8316.html
https://www.tanchenglvshi.com/episode/xb1375.html
https://www.tanchenglvshi.com/episode/at0025.html
https://www.tanchenglvshi.com/episode/bg2097.html
https://www.tanchenglvshi.com/episode/ce5795.html
https://www.tanchenglvshi.com/episode/pj8076.html
https://www.tanchenglvshi.com/episode/jx2201.html
https://www.tanchenglvshi.com/episode/sv4004.html
https://www.tanchenglvshi.com/episode/jf9954.html
https://www.tanchenglvshi.com/episode/br8068.html
https://www.tanchenglvshi.com/episode/eg9651.html
https://www.tanchenglvshi.com/episode/xs2736.html
https://www.tanchenglvshi.com/episode/vz3170.html
https://www.tanchenglvshi.com/episode/hf2541.html
https://www.tanchenglvshi.com/episode/or0610.html
https://www.tanchenglvshi.com/episode/we5848.html
https://www.tanchenglvshi.com/episode/fu1099.html
https://www.tanchenglvshi.com/episode/qu5199.html
https://www.tanchenglvshi.com/episode/zn9792.html
https://www.tanchenglvshi.com/episode/wq7509.html
https://www.tanchenglvshi.com/episode/at7785.html
https://www.tanchenglvshi.com/episode/bj9922.html
https://www.tanchenglvshi.com/episode/ko2897.html
https://www.tanchenglvshi.com/episode/yx1423.html
https://www.tanchenglvshi.com/episode/zc6742.html
https://www.tanchenglvshi.com/episode/ab0670.html
https://www.tanchenglvshi.com/episode/be3484.html
https://www.tanchenglvshi.com/episode/pg6675.html
https://www.tanchenglvshi.com/episode/zw7357.html
https://www.tanchenglvshi.com/episode/fv3842.html
https://www.tanchenglvshi.com/episode/xd6414.html
https://www.tanchenglvshi.com/episode/yd8162.html
https://www.tanchenglvshi.com/episode/tq5000.html
https://www.tanchenglvshi.com/episode/ik8253.html
https://www.tanchenglvshi.com/episode/bp2752.html
https://www.tanchenglvshi.com/episode/te4188.html
https://www.tanchenglvshi.com/episode/pf4779.html
https://www.tanchenglvshi.com/episode/mi5374.html
https://www.tanchenglvshi.com/episode/zh2561.html
https://www.tanchenglvshi.com/episode/kv0548.html
https://www.tanchenglvshi.com/episode/wq9799.html
https://www.tanchenglvshi.com/episode/pr3230.html
https://www.tanchenglvshi.com/episode/ay7067.html
https://www.tanchenglvshi.com/episode/iw3948.html
https://www.tanchenglvshi.com/episode/qi6265.html
https://www.tanchenglvshi.com/episode/wy7840.html

## 项目结构

```
resourcebridge/
├── bin/                                 # 可执行脚本与 CLI 入口
│   ├── rbctl                           # 主控制命令，解析子命令并调用模块
│   └── rb-check                        # 独立链接检查工具，可被 cron 调用
├── config/                             # 配置文件目录
│   ├── default.yaml                    # 默认配置，包含检查间隔、超时时间、输出格式
│   └── schema.json                     # 配置项 JSON Schema，用于校验用户自定义配置
├── data/                               # 数据存储目录
│   ├── links/                          # 链接条目按批次存储为 JSON 文件
│   │   ├── batch_1038.json             # 第 1038 批链接元数据
│   │   └── batch_1241.json             # 第 1241 批链接元数据
│   ├── tags/                           # 标签定义与层级关系
│   │   └── taxonomy.yaml               # 分类树，定义 "判例"、"规范" 等标签结构
│   └── logs/                           # 操作日志与检查历史
│       ├── check_2026-06-24.log        # 每日检查记录
│       └── import_history.log          # 导入操作审计日志
├── docs/                               # 文档源文件
│   ├── user-guide/                     # 用户指南章节
│   ├── admin/                          # 管理员手册
│   ├── developer/                      # 开发者文档
│   └── reference/                      # 命令行参考
├── src/                                # Python 源代码
│   ├── core/                           # 核心逻辑模块
│   │   ├── importer.py                 # 导入器，解析 CSV/JSON 并写入存储
│   │   ├── checker.py                  # 检查器，调用 curl 进行状态检测
│   │   ├── formatter.py                # 格式化器，生成引用文本
│   │   └── tracker.py                  # 变更追踪器，维护日志记录
│   ├── cli/                            # 命令行接口模块
│   │   ├── main.py                     # 命令路由
│   │   └── commands/                   # 各子命令实现
│   └── utils/                          # 通用工具函数
│       ├── http.py                     # HTTP 请求辅助
│       └── fs.py                       # 文件系统操作辅助
├── tests/                              # 单元测试与集成测试
│   ├── test_importer.py
│   ├── test_checker.py
│   └── fixtures/                       # 测试用固定数据
├── Makefile                            # 构建入口，包含 install、test、check 等目标
├── README.md                           # 本文件
└── LICENSE                             # MIT 许可证
```

## 贡献指南

欢迎社区贡献者参与 ResourceBridge 的开发与维护。请遵循以下流程提交变更。

提交问题报告或功能请求 访问 GitHub Issues 页面，检查是否已有类似议题。若无，请使用提供的模板新建议题，详细描述复现步骤、预期行为与实际行为，并附上相关日志片段或配置文件。

派生仓库并创建功能分支 将主仓库派生至个人账户，克隆派生仓库至本地，基于 main 分支创建新分支，分支命名遵循 feature/xxx 或 fix/xxx 模式，确保分支名称简洁描述变更内容。

编写或更新测试用例 针对新增功能或修复的缺陷，在 tests/ 目录下补充相应的单元测试或集成测试。所有测试须在本地通过 make test 验证，确保未破坏已有功能。

提交代码并签署开发者原产地证书 提交信息采用约定式提交格式（如 feat: 添加批量导出功能），每个提交须包含 Signed-off-by 行，表明您同意开发者原产地证书 1.1 的条款。

创建拉取请求并等待审阅 推送分支至派生仓库，在主仓库中创建拉取请求，填写 PR 模板中的变更描述、测试结果与相关议题编号。维护者将在 7 个工作日内进行审阅，必要时会要求修改。

## 常见问题

如何迁移已有的大量书签或收藏夹数据到 ResourceBridge
ResourceBridge 支持导入 Netscape HTML 书签导出格式以及通用 CSV 格式。您可以从浏览器导出书签为 HTML 文件，然后使用 rbctl import --type bookmarks --file bookmarks.html 命令进行转换导入。对于 CSV 格式，需包含 url、title、tags 三列，可选 added_date 列。导入前建议使用 rbctl validate 命令预先校验文件格式是否符合预期。

链接检查误报失效或超时如何处理
检查工具默认超时时间为 10 秒，并发数为 5。若目标服务器响应较慢或存在反爬策略，可通过修改 config/default.yaml 中的 check.timeout 和 check.concurrency 参数进行调整。同时支持设置 check.user_agent 模拟不同浏览器标识。对于已知会频繁变动的链接，可在链接条目标注 metadata.unstable: true，检查器将降低其告警优先级。

如何与其他团队共享部分链接列表而不暴露全部数据
使用 rbctl export --filter 'tag=判例' --format markdown 命令可根据标签筛选条目并导出为 Markdown 列表或 JSON 摘要。导出文件仅包含 URL、标题和标签，不包含内部备注或日志信息。若需周期性共享，可配合 rsync 将导出文件同步至指定服务器。同时支持设置 export.redact_fields 配置项，在导出时自动遮盖敏感备注字段。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-06-24 00:04:15
