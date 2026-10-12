# OA / ERP 统一仓库

本仓库统一管理 OA 与 ERP 两个项目，并保留双方原始 Git 提交历史。目前仅完成仓库整合，两个项目仍独立构建和运行。

## 目录

- `oa/`：原 RuoYi-OA-demo 项目，开发约定见 `oa/AGENTS.md`，项目说明见 `oa/README.md`。
- `erp/`：原 RuoYi-ERP-demo 项目，开发约定见 `erp/AGENTS.md`，项目说明见 `erp/README.md`。

构建和启动命令应在对应项目目录执行；前端命令分别在 `oa/ruoyi-ui/`、`erp/ruoyi-ui/` 执行。本次没有合并模块、前端、配置或数据库，也没有解决原有服务端口冲突。

新工作区仅包含原仓库 Git 跟踪的文件。本地依赖、构建产物、日志和被忽略的配置仍留在旧目录，使用新工作区前需按项目要求准备环境。引用旧绝对路径的外部脚本或 IDE 配置需要另行检查。原项目的 `.github/` 保留在各自子目录中，GitHub 不会自动识别这些子目录下的 Actions workflows。

## Git 历史与远程

统一仓库的远程 `origin` 为 `git@github.com:ShiroWei/RuoYi-OA-demo.git`。本次仅完成本地提交，未推送。

- OA 合并前基线：`628d7399`。
- ERP 合并前基线：`e4662fa0`。
- OA 通过目录移动提交放入 `oa/`。
- ERP 使用未压缩历史的 `git subtree add` 放入 `erp/`；双方原始提交 ID 均保留。

查看全部历史：`git log --graph --oneline`。查看移动前的文件历史，可使用 `git log --follow -- oa/文件路径`；也可直接通过原始提交 ID 查看原仓库布局下的代码。

审核后的备份清理事项记录在本地 `tasks/todo.md`，该目录已被 Git 忽略。
