# MAINTAINING — 导入与日常维护

> 给「我」看的操作手册：仓库怎么上 GitHub、以后怎么加和改。不碰命令行也能全套做完。

updated: 2026-10-22

## 一、第一次导入（网页方式，零命令行）

1. 打开 github.com → 右上角 `+` → **New repository**
2. Repository name 填 `personal-context`
3. 选 **Public**（私有仓库别的 AI 不带 token 抓不到 raw 链接，等于白建）
4. **不要**勾 "Add a README file"（本地已有，会冲突）
5. 点 **Create repository**
6. 新仓库页面里点 **uploading an existing file**，把 `personal-context` 文件夹里**所有内容**拖进去 → **Commit changes**
7. 验证：浏览器打开
   `https://raw.githubusercontent.com/<你的用户名>/personal-context/main/README.md`
   能看到正文就是成功，404 就是路径或分支名不对
8. 打开 `README.md`，把里面的 `<你的 GitHub 用户名>` 换成真实用户名，再 commit 一次

拖拽要点：

- 打开资源管理器的「显示隐藏项目」，否则 `.gitignore` 和 `.gitattributes` 会被漏掉
- 拖**文件夹内的内容**，不要拖外层文件夹本身（否则会多一层目录）
- `topics/` 和 `projects/` 会按目录结构保留

## 二、命令行方式（命令行修好之后）

```powershell
cd C:\Users\何栋1\Documents\deepseek-harness\default-workspace\personal-context
git init -b main
git add .
git commit -m "init: personal context library"
git remote add origin https://github.com/<你的用户名>/personal-context.git
git push -u origin main
```

## 三、以后怎么加信息

### 改已有的内容

- **网页**：仓库里点开文件 → 右上角铅笔 → 改 → **Commit changes**。手机上也能做。
- **本地**：改 `.md` → `git add -A; git commit -m "update: 改了什么"; git push`

### 加一个新主题

在 `topics/` 下新建文件，头部这四行必须齐：

```markdown
# topics/数据库 — 一句话说这是什么

> 一句话摘要：这个文件回答什么问题。

updated: 2026-10-22

## 正文……
```

然后**去 `llms.txt` 的「主题」下面加一行**。不登记等于没发布——别的 AI 只会读 `llms.txt` 决定抓什么。

### 加一个新项目

1. 新建 `projects/<名字>.md`，写：目标 / 现状 / 技术栈 / 关键决定 / 坑 / 链接
2. `projects/README.md` 的表格加一行
3. `llms.txt` 的「项目」加一行

### 只是想记一句话

写进 `NOW.md`，别新建文件。**文件越少，AI 越好用**。

## 四、每次改完的 3 条自检

1. `updated:` 改成今天
2. 新增了文件？`llms.txt` 登记了吗？`README.md` 的地图要不要加？
3. 跑 `privacy.md` 里那条扫描命令，0 命中再推

## 五、GitHub Desktop（不想碰命令行的替代）

装 GitHub Desktop → `File` → `Add local repository` → 选 `personal-context` → 以后改完在左下角写一句说明 → `Commit to main` → `Push origin`。效果和命令行完全一样，只是点鼠标。

## 六、什么不该进来

见 `privacy.md`。一句话标准：**愿意让全世界和所有 AI 都看到的内容，才进来。**
