# 作品集 GitHub 部署指南

> 创建于 2026-08-04 | 下次改动直接参考本文档即可

---

## 基本信息

| 项目 | 内容 |
|---|---|
| **作品集网址** | https://8f76-63bf.github.io/portfolio/ |
| **GitHub 仓库** | https://github.com/8F76-63BF/portfolio |
| **仓库类型** | 公开 (public) |
| **GitHub 用户** | `8F76-63BF` |
| **本地目录** | `d:\Vscode\project\` |
| **首页文件** | `index.html`（主入口，由 `portfolio.html` 同步而来） |
| **部署方式** | GitHub Pages，`main` 分支根目录 |

---

## 修改后如何同步到网站

打开终端（在 `d:\Vscode\project\` 目录下），依次执行：

```bash
# 1. 暂存所有改动
git add -A

# 2. 提交（修改引号内的描述）
git commit -m "更新作品集内容"

# 3. 推送（本地 master → 远程 main）
git push origin HEAD:main
```

推送后等 **1-2 分钟**，刷新网站即可看到更新。

---

## 文件结构

```
d:\Vscode\project\
├── index.html          ← GitHub Pages 首页（主文件）
├── portfolio.html      ← 作品集备份/源文件
├── xjl.html            ← 空白文件
├── _headers            ← 配置文件
└── images\             ← 封面图片
    ├── cover-01.jpg
    ├── cover-02.png
    ├── cover-03.png
    ├── cover-04.png
    ├── cover-05.png
    ├── cover-06.png
    ├── cover-07.png
    ├── cover-08.png
    └── cover-09.png
```

---

## GitHub 认证

本机已安装 GitHub CLI (`gh`)。下次推送如果认证过期，运行：

```bash
gh auth login
```

选 → `GitHub.com` → `HTTPS` → `Login with a web browser`，按提示操作即可。

> ⚠️ 不要用密码登录——GitHub 早已不支持。用 Token 或浏览器认证。

---

## 修改建议

- **换头像**：编辑 `index.html`，把第 746 行的 `<i class="fa-solid fa-camera">` 换成 `<img src="your-photo.jpg" alt="头像" style="width:100%;height:100%;object-fit:cover;border-radius:50%;">`
- **改名字**：把 `index.html` 中 `[xiongjiale]` 替换为真实姓名
- **改联系方式**：修改 `index.html` 第 996-1004 行的邮箱、电话、微信
- **改技能标签**：修改 `index.html` 第 757-770 行的标签
- **增删作品**：复制粘贴已有的 `<article class="work-card">` 块，修改 `data-bvid` 和描述即可
