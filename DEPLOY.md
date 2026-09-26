# RGX智能体 - 部署指南

## 项目信息
- **GitHub仓库**: https://github.com/tuoxiaoxiai-del/rgx-agents
- **目标域名**: rgx.show
- **本地项目**: `outputs/website-plan/p1-static-site/`

---

## 方法一：手动上传到GitHub（推荐）

### 步骤
1. 打开 https://github.com/tuoxiaoxiai-del/rgx-agents
2. 点击 **Add file** → **Upload files**
3. 拖拽以下文件到上传区域：
   - `index.html`
   - `README.md`
   - `DEPLOY.md`
   - `assets/wechat_qr.jpg`
   - `poster-conflict.png`
   - `poster-professional.png`
   - 所有 `books/b01/` 到 `books/b33/` 文件夹（每个文件夹至少包含 `app.html`）
4. 填写提交信息：`Initial commit: P1静态站 + 33本书智能体`
5. 点击 **Commit changes**

### 注意
- 单个文件不能超过100MB
- app.html 每个约27KB，可以正常上传
- PDF、PNG等大文件建议压缩后上传

---

## 方法二：使用Git命令（需要安装Git）

### 安装Git
下载：https://git-scm.com/download/win
安装时一路下一步即可

### 推送代码
```bash
# 1. 打开Git Bash（右键桌面 → Git Bash Here）
# 2. 进入项目目录
cd "C:/Users/13128/WorkBuddy/2026-09-25-13-56-00/outputs/website-plan/p1-static-site"

# 3. 初始化git
git init
git config user.name "RGX Agents"
git config user.email "tuoxiaoxiai@gmail.com"

# 4. 添加远程仓库
git remote add origin https://tuoxiaoxiai-del@github.com/tuoxiaoxiai-del/rgx-agents.git

# 5. 添加所有文件
git add .
git status

# 6. 提交
git commit -m "Initial commit: P1静态站 + 33本书智能体"

# 7. 推送到GitHub
git push -u origin main
```

---

## 方法三：使用Vercel CLI（最快）

### 安装Vercel
```bash
npm install -g vercel
```

### 部署
```bash
cd "C:/Users/13128/WorkBuddy/2026-09-25-13-56-00/outputs/website-plan/p1-static-site"
vercel login
vercel --prod
```

### 绑定域名
```bash
vercel domains add rgx.show
```

---

## 部署后验证

访问 https://rgx.show 检查：
- [ ] 首页正常加载
- [ ] 33本书的卡片显示正确
- [ ] 点击"立即学习"能打开对应的app.html
- [ ] 二维码图片显示
- [ ] 移动端适配正常

---

## 故障排查

### 问题：GitHub上传失败
- 检查Token权限（需要repo权限）
- 检查文件名是否包含特殊字符

### 问题：Vercel部署失败
- 检查是否有构建错误
- 查看Vercel日志

### 问题：域名无法访问
- 检查DNS配置
- 等待DNS生效（通常5-10分钟）

---

更新时间：2026-09-26
