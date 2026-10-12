# RuoYi-demo

基于若依（RuoYi）的练手与二次开发项目集合，用于持续维护若依相关修改，以及新增基于不同若依架构的系统。目前包含 OA 和 ERP 两个项目，各自独立构建和运行，并保留双方原始 Git 提交历史。

## 目录

- [OA 项目](oa/README.md)：位于 `oa/`，开发约定见 [oa/AGENTS.md](oa/AGENTS.md)。
- [ERP 项目](erp/README.md)：位于 `erp/`，开发约定见 [erp/AGENTS.md](erp/AGENTS.md)。

```text
RuoYi-demo/
├── oa/       # OA Maven 工程与前端
├── erp/      # ERP Maven 工程与前端
└── .git/     # 所有子项目共用的 Git 仓库
```

## 获取代码与开发入口

```bash
git clone git@github.com:ShiroWei/RuoYi-demo.git RuoYi-demo
cd RuoYi-demo
```

| 操作 | OA | ERP |
| --- | --- | --- |
| IDEA 打开 Maven 工程 | `oa/pom.xml` | `erp/pom.xml` |
| 后端构建工作目录 | `oa/` | `erp/` |
| 前端安装、开发、构建工作目录 | `oa/ruoyi-ui/` | `erp/ruoyi-ui/` |
| Windows 启动脚本（从统一仓库根目录调用） | `oa\bin\start-all.bat` | `erp\bin\start-all.bat` |
| 本地开发指南 | [OA 指南](oa/docs/本地开发环境配置.md) | [ERP 指南](erp/docs/本地开发环境配置.md) |

统一仓库根目录没有聚合 `pom.xml` 或前端 `package.json`，请在对应项目目录执行构建命令。

各子项目独立管理依赖、模块、前端、配置和数据库脚本。当前仅统一 Git 管理，运行时的共享基础设施和服务端口冲突仍按各项目开发指南处理。

工作区仅包含 Git 跟踪的文件。本地依赖、构建产物及被忽略的配置需按项目要求准备；外部脚本或 IDE 配置应使用当前目录路径。原项目的 `.github/FUNDING.yml` 保留在各自子目录中；当前没有 Actions workflows。GitHub 的仓库级配置需要放在根 `.github/` 才会被识别。

## 新增若依项目

新系统在仓库根目录建立独立子目录，与 `oa/`、`erp/` 同级，目录名称体现系统用途或架构。各子项目应提供自己的 README、开发约定和构建入口，并在本页目录与开发入口中登记。所有子项目共用根 `.git/`，不在子目录再次初始化 Git。是否共用代码或整合系统，应按具体需求另行决定。

## Git 历史与远程

仓库的远程 `origin` 为 `git@github.com:ShiroWei/RuoYi-demo.git`。

- OA 合并前基线：`628d7399`。
- ERP 合并前基线：`e4662fa0`。
- OA 通过目录移动提交放入 `oa/`。
- ERP 使用未压缩历史的 `git subtree add` 放入 `erp/`；双方原始提交 ID 均保留。

查看全部历史：`git log --graph --oneline`。查看移动前的文件历史，可使用 `git log --follow -- oa/文件路径`；也可直接通过原始提交 ID 查看原仓库布局下的代码。
