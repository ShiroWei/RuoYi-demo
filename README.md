# OA / ERP 统一仓库

本仓库统一管理 OA 与 ERP 两个项目，并保留双方原始 Git 提交历史。目前仅完成仓库整合，两个项目仍独立构建和运行。

## 目录

- [OA 项目](oa/README.md)：位于 `oa/`，开发约定见 [oa/AGENTS.md](oa/AGENTS.md)。
- [ERP 项目](erp/README.md)：位于 `erp/`，开发约定见 [erp/AGENTS.md](erp/AGENTS.md)。

```text
oa-demo/
├── oa/       # OA Maven 工程与前端
├── erp/      # ERP Maven 工程与前端
└── .git/     # 两个项目共用的 Git 仓库
```

## 获取代码与开发入口

以下克隆命令适用于统一仓库改动推送之后：

```bash
git clone git@github.com:ShiroWei/RuoYi-OA-demo.git oa-demo
cd oa-demo
```

| 操作 | OA | ERP |
| --- | --- | --- |
| IDEA 打开 Maven 工程 | `oa/pom.xml` | `erp/pom.xml` |
| 后端构建工作目录 | `oa/` | `erp/` |
| 前端安装、开发、构建工作目录 | `oa/ruoyi-ui/` | `erp/ruoyi-ui/` |
| Windows 启动脚本（从统一仓库根目录调用） | `oa\bin\start-all.bat` | `erp\bin\start-all.bat` |
| 本地开发指南 | [OA 指南](oa/docs/本地开发环境配置.md) | [ERP 指南](erp/docs/本地开发环境配置.md) |

统一仓库根目录没有聚合 `pom.xml` 或前端 `package.json`，请在对应项目目录执行构建命令。

构建和启动命令应在对应项目目录执行；前端命令分别在 `oa/ruoyi-ui/`、`erp/ruoyi-ui/` 执行。本次没有合并模块、前端、配置或数据库，也没有解决原有服务端口冲突。

新工作区仅包含原仓库 Git 跟踪的文件。本地依赖、构建产物、日志和被忽略的配置仍保留在 `../oa-demo-backup/`、`../erp-demo/`，使用新工作区前需按项目要求准备环境。引用旧绝对路径的外部脚本或 IDE 配置需要另行检查。原项目的 `.github/FUNDING.yml` 保留在各自子目录中；当前没有 Actions workflows。GitHub 的仓库级配置需要放在根 `.github/` 才会被识别，本次没有整合这些配置。

## Git 历史与远程

统一仓库的远程 `origin` 为 `git@github.com:ShiroWei/RuoYi-OA-demo.git`。本次仅完成本地提交，未推送。

- OA 合并前基线：`628d7399`。
- ERP 合并前基线：`e4662fa0`。
- OA 通过目录移动提交放入 `oa/`。
- ERP 使用未压缩历史的 `git subtree add` 放入 `erp/`；双方原始提交 ID 均保留。

查看全部历史：`git log --graph --oneline`。查看移动前的文件历史，可使用 `git log --follow -- oa/文件路径`；也可直接通过原始提交 ID 查看原仓库布局下的代码。

审核后的备份清理事项记录在本地 `tasks/todo.md`，该目录已被 Git 忽略。用户审查并推送统一仓库后，需明确批准才能删除 `../oa-demo-backup/` 和 `../erp-demo/`。
