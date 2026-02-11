# GitHub Pages 部署说明

## 前提条件
- 项目已推送到GitHub仓库
- 仓库名称：`mind-map`（如果不是，请修改vue.config.js中的publicPath）

## 部署步骤

### 1. 启用GitHub Pages
1. 进入GitHub仓库的Settings页面
2. 在左侧菜单中找到"Pages"
3. 在"Source"部分选择"GitHub Actions"
4. 保存设置

### 2. 推送代码到GitHub
```bash
git add .
git commit -m "feat: 添加GitHub Pages自动部署"
git push origin master
```

### 3. 检查部署状态
1. 进入GitHub仓库的"Actions"标签页
2. 查看"Deploy to GitHub Pages"工作流是否运行成功
3. 部署成功后，访问：`https://[你的用户名].github.io/mind-map/`

## 配置说明

### publicPath配置
- 开发环境：`/`
- 生产环境：`/mind-map/`（根据您的仓库名称调整）

### GitHub Actions工作流
工作流会在每次推送到master分支时自动触发，完成以下步骤：
1. 检出代码
2. 设置Node.js环境
3. 安装依赖
4. 构建项目
5. 部署到GitHub Pages

## 注意事项
- 确保仓库名称为`mind-map`，否则需要修改vue.config.js中的publicPath
- 首次部署可能需要几分钟时间
- 如果部署失败，请检查GitHub Actions日志中的错误信息