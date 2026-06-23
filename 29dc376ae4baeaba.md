# GXHY Resource Bridge

GXHY Resource Bridge 是一个面向技术社区与开发者群体的外链资源聚合与导航系统。该项目定位于将分散在各类技术论坛、讨论组与知识库中的高质量外部链接进行结构化整理与分类归档，帮助开发者快速定位与自身工作流相关的技术文档、工具链、解决方案与最佳实践案例。

本项目不生产内容，而是作为技术信息的索引层与路由层存在。目标用户包括运维工程师、后端开发者、前端工程师、数据科学家以及技术决策者。通过对海量外链的元数据提取、标签化与关系建模，GXHY Resource Bridge 能够显著降低信息检索的时间成本，提升技术调研与问题排查的效率。

## 功能概览

**外链元数据抽取**：自动抓取目标页面的标题、描述、关键词与发布时间，生成结构化索引记录。

**多维度分类体系**：按技术栈、应用场景、文档类型、目标受众与成熟度等级五个维度对每条链接进行标记。

**全文检索与过滤器**：支持基于标题关键词、标签组合与时间范围的混合检索，返回排序后的结果列表。

**定期健康检查**：对已收录链接进行可用性探测与内容变更检测，自动标记失效或重大更新的资源。

**用户自定义收藏夹**：允许注册用户将常用链接归入个人收藏集，并支持标签重命名与批量导出。

**开放数据导出接口**：提供 JSON 与 CSV 两种格式的完整索引导出，便于第三方工具集成与二次分析。

**管理后台审计日志**：记录所有资源的增删改操作，支持按操作者与时间范围回溯变更历史。

## 应用场景

技术选型与方案对比。当团队需要评估多个开源项目或商业产品时，可通过本系统快速收集相关的官方文档、社区讨论与性能测试报告，集中进行横向对比。

故障排查与问题定位。运维人员收到告警后，可在本系统中检索历史案例、解决方案帖与官方修复公告，缩短平均修复时间（MTTR）。

新人入职与知识传承。新加入团队的开发人员可以通过本系统访问预先整理的项目脚手架、编码规范与内部工具文档，加速环境搭建与业务理解。

技术雷达与趋势跟踪。技术负责人可以定期浏览本系统收录的最新资源，识别新兴技术框架与行业标准，调整团队的技术演进路线。

## 快速开始

以下指令适用于 Linux 与 macOS 环境，Windows 用户建议使用 WSL2 或 Git Bash。

```bash
# 克隆代码仓库
git clone https://github.com/gxhy/resource-bridge.git
cd resource-bridge

# 安装项目依赖（使用 Python 3.9+ 与 pip）
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# 初始化数据库并启动开发服务器
python manage.py migrate
python manage.py loaddata initial_links.json
python manage.py runserver 0.0.0.0:8000
```

生产环境部署请参考 `deploy` 目录下的 Ansible 剧本与 Docker Compose 配置文件。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 - 3.11 | 核心运行环境，推荐使用 pyenv 管理 |
| PostgreSQL | 12.0 及以上 | 主数据库，用于存储资源索引与用户数据 |
| Redis | 6.0 及以上 | 缓存与任务队列后端，用于健康检查任务调度 |
| Elasticsearch | 7.17 或 8.x | 可选组件，用于启用全文检索增强功能 |
| Node.js | 16.0 及以上 | 仅用于构建前端静态资源，运行时可省略 |
| Nginx | 1.20 及以上 | 生产环境反向代理与静态文件服务 |
| Supervisor | 4.0 及以上 | 进程守护工具，保证后台任务持续运行 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | `/docs/user-guide/` | 如何注册账号、添加收藏、进行检索与导出数据 |
| 管理员手册 | `/docs/admin-guide/` | 如何管理资源条目、审核用户提交、查看审计日志 |
| 开发指南 | `/docs/development/` | 如何配置本地开发环境、运行测试用例、提交代码变更 |
| API 参考 | `/docs/api/` | RESTful 接口的端点定义、请求参数与响应格式说明 |
| 架构设计 | `/docs/architecture/` | 系统模块划分、数据流图、扩展点与性能考量 |
| 运维手册 | `/docs/operations/` | 监控指标配置、日志采集、备份恢复与灾难预案 |

## 资源列表

本系统当前索引的资源均来自公开技术讨论区，按内容主题进行初步分类。所有链接保留原始格式。

技术文档与参考

https://www.gxhy.net/thread-280383-zELmD.html
https://www.gxhy.net/thread-933739-DWtKuL1.html
https://www.gxhy.net/thread-741448-2NdSzP6U.html
https://www.gxhy.net/thread-742618-EgDpu.html
https://www.gxhy.net/thread-799808-9ogoYc.html
https://www.gxhy.net/thread-073200-NC5U.html
https://www.gxhy.net/thread-971174-V8n1i9y.html
https://www.gxhy.net/thread-618544-FOmoZd.html
https://www.gxhy.net/thread-316347-me4Ae53.html
https://www.gxhy.net/thread-715041-ipTWO0vf.html
https://www.gxhy.net/thread-212184-KvOnfT.html
https://www.gxhy.net/thread-626662-4CVSB2iI.html
https://www.gxhy.net/thread-896860-xdZPsn.html
https://www.gxhy.net/thread-432661-LH1Gtcl.html
https://www.gxhy.net/thread-375391-sfZ6Z2sg.html
https://www.gxhy.net/thread-603182-Onow.html
https://www.gxhy.net/thread-521850-e7dKiaD.html
https://www.gxhy.net/thread-353018-UstoKvl8.html
https://www.gxhy.net/thread-388523-DHEDw.html
https://www.gxhy.net/thread-407366-n05i.html
https://www.gxhy.net/thread-263445-3bIJ.html
https://www.gxhy.net/thread-638277-pA1a9Aig.html
https://www.gxhy.net/thread-877883-efnLOS.html
https://www.gxhy.net/thread-351243-2ME4CB.html
https://www.gxhy.net/thread-124513-j1IBxHY.html
https://www.gxhy.net/thread-920495-HCYhm0l.html
https://www.gxhy.net/thread-360937-N0xFQ.html
https://www.gxhy.net/thread-444720-TAcPhWKi.html
https://www.gxhy.net/thread-141593-gmvL.html
https://www.gxhy.net/thread-111562-mGOmqNEe.html
https://www.gxhy.net/thread-360937-KTrEI.html
https://www.gxhy.net/thread-297745-0hDtD.html
https://www.gxhy.net/thread-436246-LQXu.html
https://www.gxhy.net/thread-039523-xQGx.html
https://www.gxhy.net/thread-509532-IeHVVDGQ.html
https://www.gxhy.net/thread-072409-yyFI.html
https://www.gxhy.net/thread-685181-q1FnMvr9.html
https://www.gxhy.net/thread-673832-KPPEaCrK.html
https://www.gxhy.net/thread-788612-Dbhpo0.html
https://www.gxhy.net/thread-105240-hL4TmI.html
https://www.gxhy.net/thread-100266-ne2QHt.html
https://www.gxhy.net/thread-884865-Xr4dUoCv.html
https://www.gxhy.net/thread-110480-mOQe.html
https://www.gxhy.net/thread-937693-Y7ZqGX9.html
https://www.gxhy.net/thread-897172-7YfE.html
https://www.gxhy.net/thread-500217-p1HoWRy.html
https://www.gxhy.net/thread-448691-rlbzC0.html
https://www.gxhy.net/thread-304006-p5l7X9.html
https://www.gxhy.net/thread-108428-gih8Kb.html
https://www.gxhy.net/thread-606439-kcRq.html
https://www.gxhy.net/thread-753814-0MMg2q.html
https://www.gxhy.net/thread-005679-k60oQ.html
https://www.gxhy.net/thread-628303-xg1Jfka.html
https://www.gxhy.net/thread-574452-pKRNCS.html
https://www.gxhy.net/thread-742032-s4wplJAK.html
https://www.gxhy.net/thread-823930-AZ7BmXtJ.html
https://www.gxhy.net/thread-058700-wnvIj8.html
https://www.gxhy.net/thread-163700-y1ct1mi.html
https://www.gxhy.net/thread-501800-HT8gR.html
https://www.gxhy.net/thread-952425-raaKwqe.html
https://www.gxhy.net/thread-211704-dvGBvYU3.html
https://www.gxhy.net/thread-049029-r9rjn.html
https://www.gxhy.net/thread-317268-IY81.html
https://www.gxhy.net/thread-879447-28Js7YIp.html
https://www.gxhy.net/thread-905115-oj4c.html
https://www.gxhy.net/thread-243152-aEJWHi8Q.html
https://www.gxhy.net/thread-706242-8PyjK.html
https://www.gxhy.net/thread-781626-C18iz.html
https://www.gxhy.net/thread-479504-jlNK.html
https://www.gxhy.net/thread-328757-JjIi.html
https://www.gxhy.net/thread-601677-37GGbJ7Q.html
https://www.gxhy.net/thread-014130-L30cE5tR.html
https://www.gxhy.net/thread-514746-4KJyXbu.html
https://www.gxhy.net/thread-003103-c20recD.html
https://www.gxhy.net/thread-175160-nHZc.html
https://www.gxhy.net/thread-909694-3liUen.html
https://www.gxhy.net/thread-686147-R4kWZ.html
https://www.gxhy.net/thread-910133-1enJ.html
https://www.gxhy.net/thread-728071-cUCz.html
https://www.gxhy.net/thread-521597-GVtYb.html
https://www.gxhy.net/thread-602195-EYVVNK.html
https://www.gxhy.net/thread-829126-cjHEWDOs.html
https://www.gxhy.net/thread-952320-dGs9.html
https://www.gxhy.net/thread-639673-DYss.html
https://www.gxhy.net/thread-647294-6e2oQF.html
https://www.gxhy.net/thread-378095-qzAyQ.html
https://www.gxhy.net/thread-330976-eesD.html
https://www.gxhy.net/thread-161193-wb5EJ0.html
https://www.gxhy.net/thread-459407-nWiW.html
https://www.gxhy.net/thread-805272-NfnFqrM.html
https://www.gxhy.net/thread-285425-VAxOs9c.html
https://www.gxhy.net/thread-244800-Zy7Z5B.html
https://www.gxhy.net/thread-021737-IEhcVD.html
https://www.gxhy.net/thread-820696-spnxsKjy.html
https://www.gxhy.net/thread-065700-p5uW.html
https://www.gxhy.net/thread-225717-V1eHLi.html
https://www.gxhy.net/thread-755486-3uQfjoPk.html
https://www.gxhy.net/thread-094041-L8ZS1Cm.html
https://www.gxhy.net/thread-361134-AT8PBhV.html
https://www.gxhy.net/thread-281007-mfps9q.html
https://www.gxhy.net/thread-375464-CUwf.html
https://www.gxhy.net/thread-652966-ghKfNquX.html
https://www.gxhy.net/thread-196326-vaqtM1dI.html
https://www.gxhy.net/thread-726697-jpVm.html
https://www.gxhy.net/thread-246088-QnPNt.html
https://www.gxhy.net/thread-222233-GB3e.html
https://www.gxhy.net/thread-765986-q12fpeyY.html
https://www.gxhy.net/thread-544318-Queo9oZH.html
https://www.gxhy.net/thread-377798-Jk9W.html
https://www.gxhy.net/thread-597569-RnjcQ6.html
https://www.gxhy.net/thread-469843-TJ6w.html
https://www.gxhy.net/thread-545568-TLI3CWq.html
https://www.gxhy.net/thread-003277-8s3RW.html
https://www.gxhy.net/thread-565255-sVbl3W.html
https://www.gxhy.net/thread-046355-5tMM.html
https://www.gxhy.net/thread-521946-P2BkZz.html
https://www.gxhy.net/thread-982317-TlpL.html
https://www.gxhy.net/thread-684199-ZM01fEic.html
https://www.gxhy.net/thread-977704-QKLQyC.html
https://www.gxhy.net/thread-338458-21Y5.html
https://www.gxhy.net/thread-536559-gAHiw.html
https://www.gxhy.net/thread-827252-6s5Ho.html
https://www.gxhy.net/thread-060621-vZ1f.html
https://www.gxhy.net/thread-815012-7FFIp.html
https://www.gxhy.net/thread-263059-mq17To5.html
https://www.gxhy.net/thread-532830-igPLC.html
https://www.gxhy.net/thread-864508-QwDPY.html
https://www.gxhy.net/thread-331764-wswFc8YK.html
https://www.gxhy.net/thread-582494-XCWECR.html
https://www.gxhy.net/thread-007568-BTvJBzzo.html
https://www.gxhy.net/thread-733164-tiKkSy5Z.html
https://www.gxhy.net/thread-931908-jsjhdldw.html
https://www.gxhy.net/thread-070887-AutW.html
https://www.gxhy.net/thread-104838-4m4HAG.html
https://www.gxhy.net/thread-899385-VV2h.html
https://www.gxhy.net/thread-419577-37mD8.html
https://www.gxhy.net/thread-234824-pT7n6.html
https://www.gxhy.net/thread-785589-v3ldO.html
https://www.gxhy.net/thread-987534-otb8D3.html
https://www.gxhy.net/thread-462509-oLzn.html
https://www.gxhy.net/thread-617155-WSaIbXLc.html
https://www.gxhy.net/thread-393435-mmB958tB.html
https://www.gxhy.net/thread-719908-B7ZC4oqO.html
https://www.gxhy.net/thread-718294-9JR2.html
https://www.gxhy.net/thread-525849-UGkJMhk.html
https://www.gxhy.net/thread-054750-EkrJJJA.html
https://www.gxhy.net/thread-477671-gJytcR.html
https://www.gxhy.net/thread-169274-EEKDtO.html
https://www.gxhy.net/thread-682577-HSWAsz.html
https://www.gxhy.net/thread-001626-dLpdZd.html
https://www.gxhy.net/thread-187649-vb3h.html
https://www.gxhy.net/thread-483065-fVNumVom.html
https://www.gxhy.net/thread-087242-QFmpK.html
https://www.gxhy.net/thread-846783-4MEJ7.html
https://www.gxhy.net/thread-776886-bxNx4e0A.html
https://www.gxhy.net/thread-279352-XCiMi.html
https://www.gxhy.net/thread-222189-vSCbFX1.html
https://www.gxhy.net/thread-623928-H0u1A.html
https://www.gxhy.net/thread-817332-YfXl.html
https://www.gxhy.net/thread-559420-quuKgi.html
https://www.gxhy.net/thread-918670-MxDG.html
https://www.gxhy.net/thread-444278-eYFUlq.html
https://www.gxhy.net/thread-327756-HBDLkI.html
https://www.gxhy.net/thread-149368-58XqtRA.html
https://www.gxhy.net/thread-093527-pfhb.html
https://www.gxhy.net/thread-475281-15jaeVb.html
https://www.gxhy.net/thread-158775-5zb3w49B.html
https://www.gxhy.net/thread-922646-zhpFVP7n.html
https://www.gxhy.net/thread-476650-4lsS.html
https://www.gxhy.net/thread-443113-8wZTLu93.html
https://www.gxhy.net/thread-886157-mbziOj.html
https://www.gxhy.net/thread-833138-AXbBnC4.html
https://www.gxhy.net/thread-645268-tgUPGD3.html
https://www.gxhy.net/thread-620253-XqsW.html
https://www.gxhy.net/thread-133119-iHOwIjO.html
https://www.gxhy.net/thread-553132-YddRk.html
https://www.gxhy.net/thread-662677-W11Dfgg.html
https://www.gxhy.net/thread-467122-K2grZpq.html
https://www.gxhy.net/thread-417361-3g1ufu5.html
https://www.gxhy.net/thread-728418-18eh8o2Y.html
https://www.gxhy.net/thread-093728-liGMlpJ.html
https://www.gxhy.net/thread-171842-JSARu.html
https://www.gxhy.net/thread-887291-SJfbwUQ.html
https://www.gxhy.net/thread-111898-2aEGZZO.html
https://www.gxhy.net/thread-332874-5G7D.html
https://www.gxhy.net/thread-742188-hHv0kkM8.html
https://www.gxhy.net/thread-538850-VCde.html
https://www.gxhy.net/thread-189377-HUsP.html
https://www.gxhy.net/thread-021532-C4BdCUX7.html
https://www.gxhy.net/thread-825088-GyL7.html
https://www.gxhy.net/thread-174285-s1cpWv.html
https://www.gxhy.net/thread-057513-y7FKFb.html
https://www.gxhy.net/thread-625069-l6jqaKu.html
https://www.gxhy.net/thread-260704-X8InyT.html
https://www.gxhy.net/thread-972647-y16gLaFj.html
https://www.gxhy.net/thread-969465-ArEv0L.html
https://www.gxhy.net/thread-974729-CaDz.html
https://www.gxhy.net/thread-268631-Y8tg47YC.html
https://www.gxhy.net/thread-601622-bKpwjAa.html
https://www.gxhy.net/thread-282694-V5cw.html
https://www.gxhy.net/thread-277832-hS9v2qwq.html
https://www.gxhy.net/thread-426220-N84T.html
https://www.gxhy.net/thread-806970-8LRM.html
https://www.gxhy.net/thread-558518-I4DXdP.html
https://www.gxhy.net/thread-416537-5yhbd1mH.html
https://www.gxhy.net/thread-864498-F4Vp.html
https://www.gxhy.net/thread-709924-t6be7.html
https://www.gxhy.net/thread-632644-Z20OBRY.html
https://www.gxhy.net/thread-183418-0Q0S2.html
https://www.gxhy.net/thread-387197-oDQQl.html
https://www.gxhy.net/thread-525817-midX.html
https://www.gxhy.net/thread-925445-gHpv.html
https://www.gxhy.net/thread-928839-BesC09.html
https://www.gxhy.net/thread-146219-Vhhak.html
https://www.gxhy.net/thread-269601-cx3iRwOf.html
https://www.gxhy.net/thread-774215-QSzw.html
https://www.gxhy.net/thread-233127-6tsSVaT.html
https://www.gxhy.net/thread-050318-Whmh.html
https://www.gxhy.net/thread-947179-f5glXBy.html
https://www.gxhy.net/thread-984836-xZ5l.html
https://www.gxhy.net/thread-672992-57J25E.html
https://www.gxhy.net/thread-248747-9BqHpCK9.html
https://www.gxhy.net/thread-528952-gR7Cp.html
https://www.gxhy.net/thread-507669-gQRsm7D.html
https://www.gxhy.net/thread-393379-5vMJ.html
https://www.gxhy.net/thread-754827-L9a9qBhF.html
https://www.gxhy.net/thread-774973-7cm08KHQ.html
https://www.gxhy.net/thread-305059-p53UHvA9.html
https://www.gxhy.net/thread-900261-cfC9R.html
https://www.gxhy.net/thread-071756-8jWsBs.html
https://www.gxhy.net/thread-352505-GjtCc.html
https://www.gxhy.net/thread-944624-UqhpJ.html
https://www.gxhy.net/thread-869465-NRflJed.html
https://www.gxhy.net/thread-372496-LOZPa.html
https://www.gxhy.net/thread-750624-MZSek.html
https://www.gxhy.net/thread-583454-irgu2Y4Y.html
https://www.gxhy.net/thread-304392-Af8jMg.html
https://www.gxhy.net/thread-798056-sYxoh.html
https://www.gxhy.net/thread-913222-11iYyo0p.html
https://www.gxhy.net/thread-502542-DELt3.html
https://www.gxhy.net/thread-733255-fAt2Qh1y.html
https://www.gxhy.net/thread-989642-T74b.html
https://www.gxhy.net/thread-504135-QTcNRVRH.html
https://www.gxhy.net/thread-252923-MPTE.html
https://www.gxhy.net/thread-231866-ZHYot.html
https://www.gxhy.net/thread-233425-Hacgfbcz.html
https://www.gxhy.net/thread-435708-fkNI9.html
https://www.gxhy.net/thread-471908-LhxQ.html
https://www.gxhy.net/thread-037432-mz3Zi.html
https://www.gxhy.net/thread-451366-oSoi7.html

## 项目结构

```
resource-bridge/
├── bridge/                                 # 主应用包
│   ├── __init__.py                         # 包初始化，版本号定义
│   ├── settings/                           # 环境配置目录
│   │   ├── base.py                         # 基础配置，适用于所有环境
│   │   ├── development.py                  # 开发环境配置，启用调试工具
│   │   └── production.py                   # 生产环境配置，关闭调试并优化性能
│   ├── urls.py                             # 根路由分发，映射至各个子应用
│   ├── wsgi.py                             # WSGI 入口，用于 Gunicorn / uWSGI
│   └── asgi.py                             # ASGI 入口，用于 Django Channels
├── apps/                                   # 功能模块子应用
│   ├── links/                              # 链接管理模块，核心业务逻辑
│   │   ├── models.py                       # Link, Tag, Category 数据模型
│   │   ├── views.py                        # API 视图与渲染视图
│   │   ├── serializers.py                  # DRF 序列化器，输出 JSON 结构
│   │   ├── tasks.py                        # Celery 定时任务，健康检查与摘要更新
│   │   └── utils.py                        # 链接解析、摘要生成辅助函数
│   ├── users/                              # 用户认证与权限管理
│   │   ├── models.py                       # 自定义用户模型，扩展 Profile
│   │   ├── backends.py                     # 邮箱/用户名双因子认证后端
│   │   └── permissions.py                  # 基于角色的访问控制类
│   └── search/                             # 检索与索引服务
│       ├── index.py                        # Elasticsearch 索引映射与重建逻辑
│       ├── queries.py                      # 复合查询构造器，支持布尔与范围过滤
│       └── signals.py                      # 模型信号，在保存时自动更新索引
├── static/                                 # 静态资源（CSS, JS, 图片）
│   ├── css/                                # 基于 Tailwind 编译的样式表
│   ├── js/                                 # 前端交互逻辑，Alpine.js + HTMX
│   └── images/                             # 图标与徽标文件
├── templates/                              # Django 模板文件
│   ├── base.html                           # 基础骨架，包含导航栏与全局脚本
│   ├── link_list.html                      # 链接列表页，支持分页与过滤器
│   └── link_detail.html                    # 详情页，展示完整元数据与相关链接
├── tests/                                  # 单元测试与集成测试
│   ├── test_models.py                      # 数据模型验证用例
│   ├── test_api.py                         # API 端点功能与状态码测试
│   └── test_tasks.py                       # 后台任务模拟与断言
├── scripts/                                # 运维与辅助脚本
│   ├── seed_db.py                          # 通过 CSV 文件批量导入初始链接
│   ├── export_links.py                     # 导出全量索引为 JSON / CSV
│   └── health_check.py                     # 独立运行的健康检查探测器
├── deploy/                                 # 生产部署工件
│   ├── docker-compose.yml                  # 编排 PostgreSQL, Redis, Elasticsearch, Nginx
│   ├── Dockerfile                          # 多阶段构建镜像，优化层缓存
│   ├── nginx.conf                          # 反向代理配置，包含静态文件缓存策略
│   └── supervisor.conf                     # 进程监控配置，管理 Gunicorn + Celery
├── requirements/                           # 依赖分拆文件
│   ├── base.txt                            # 核心依赖（Django, DRF, Celery）
│   ├── dev.txt                             # 开发辅助（pytest, ipdb, django-debug-toolbar）
│   └── prod.txt                            # 生产额外依赖（gunicorn, psycopg2-binary）
├── .env.example                            # 环境变量示例，含数据库连接串与密钥占位
├── manage.py                               # Django 管理入口
├── README.md                               # 项目说明文档（本文件）
├── LICENSE                                 # MIT 许可证全文
└── .gitignore                              # 忽略规则（venv, .pyc, .env, 日志文件）
```

## 贡献指南

我们欢迎社区贡献，无论是错误报告、功能建议还是代码提交。请遵循以下流程以确保协作顺畅。

第一，从 GitHub 仓库派生（Fork）本项目至个人账号，并克隆到本地开发环境。在开始任何工作前，请阅读 `docs/development/` 下的环境搭建指南，确保所有依赖与服务均正确启动。

第二，在提交代码前，请运行完整的测试套件（`pytest tests/`）与代码风格检查（`flake8` 与 `black`）。新增功能必须附带对应的单元测试用例，且覆盖率达到 85% 以上。

第三，提交信息（Commit Message）应采用约定式规范（Conventional Commits），例如 `feat: 添加链接批量导入接口` 或 `fix: 修复健康检查任务超时导致的队列阻塞`。每次 Pull Request 应仅关联一个 Issue 或一个明确的功能点。

第四，对于大型架构调整或破坏性变更，请先在 Issue 中发起设计讨论，待核心维护者确认后再进行开发。这样可避免重复工作并保持设计一致性。

第五，文档更新与代码变更需同步进行。所有新增 API 端点、配置项或环境变量必须在 `docs/` 对应章节中补充说明，确保用户手册与实现始终保持一致。

## 常见问题

Q：健康检查任务发现大量链接失效后，系统会自动删除这些条目吗？

A：不会自动删除。系统会标记失效链接的状态为 `unreachable`，并记录检查时间与 HTTP 状态码。管理员可以在后台面板中批量复查或手动移除。自动删除策略可能在未来版本中作为可选配置项引入。

Q：是否可以导入自定义的链接列表，而非仅使用系统初始数据？

A：可以。系统提供了 `scripts/seed_db.py` 脚本，接受 CSV 或 JSON 格式的文件路径作为参数。导入时需包含必要字段（URL、标题、标签列表），否则脚本会跳过不合规行并输出错误日志。详细格式示例参见 `docs/admin-guide/bulk-import.md`。

Q：部署到生产环境后，检索功能响应缓慢，应如何优化？

A：首先检查 Elasticsearch 索引是否已正确创建并包含有效数据。其次，调整 `settings/production.py` 中的 `SEARCH_RESULTS_PER_PAGE` 与 `CACHE_TTL` 参数，减小单次查询的负载。如果数据量超过 10 万条，建议增加 Elasticsearch 节点或启用 Redis 查询缓存层。具体调优参数请参考 `docs/operations/performance-tuning.md`。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-06-23 23:51:39
