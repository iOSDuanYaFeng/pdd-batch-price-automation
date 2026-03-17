# 📤 GitHub上传指南 - 拼多多批量改价项目

## 📁 项目文件清单

### **核心项目文件（已打包）**
```
pdd-batch-price-project.tar.gz (约10MB)
包含以下目录结构：
pdd-batch-price-project/
├── 📄 README.md                    # 项目主文档
├── 🐍 verify_installation.py      # 环境验证脚本
├── 📂 scripts/
│   └── 🐍 excel_splitter.py       # Excel拆分核心脚本
├── 📂 data/                       # 测试数据目录
│   ├── test_data_120k.xlsx        # 12万行测试数据
│   └── split_files/               # 拆分后的文件示例
└── 📂 output/                     # 输出目录（运行时创建）
```

### **技能配置文件（需要创建）**
```markdown
# SKILL.md - 拼多多批量改价技能

## 技能概述
自动化处理拼多多批量改价任务，支持60万行Excel数据拆分和批量上传。

## 功能特性
1. Excel文件拆分（每5万行一个文件）
2. 拼多多后台自动登录
3. 批量文件上传和改价
4. 错误恢复和进度跟踪

## 依赖技能
- agent-browser (0.2.0+)
- excel-parser-skill (2.0.0+)
- excel-xlsx (1.0.2+)
- batch-processing-patterns (1.0.0+)
- pinduoduo-automation (2.0.2+)

## 安装命令
```bash
# 安装核心技能
skillhub install agent-browser
skillhub install excel-parser-skill
skillhub install excel-xlsx
skillhub install batch-processing-patterns
skillhub install pinduoduo-automation

# 安装Python依赖
pip install pandas openpyxl selenium playwright
```

## 使用方法
```bash
# 1. 验证安装
python3 verify_installation.py

# 2. 运行Excel拆分
python3 scripts/excel_splitter.py

# 3. 开始拼多多自动化
python3 scripts/pdd_automation.py
```

## 许可证
MIT License
```

## 🚀 GitHub上传步骤

### **方法一：使用GitHub网页界面**

#### **步骤1：创建新仓库**
1. 访问 https://github.com/new
2. 填写仓库信息：
   - **Repository name**: `pdd-batch-price-automation`
   - **Description**: 拼多多批量改价自动化系统
   - **Visibility**: Public (推荐) 或 Private
   - 勾选 "Add a README file"
   - 选择 MIT License

#### **步骤2：上传文件**
1. 在仓库页面点击 "Add file" → "Upload files"
2. 上传 `pdd-batch-price-project.tar.gz` 文件
3. 添加提交信息："初始提交：拼多多批量改价项目"
4. 点击 "Commit changes"

#### **步骤3：创建技能配置文件**
1. 在仓库中创建 `SKILL.md` 文件
2. 复制上面的技能配置内容
3. 提交文件

### **方法二：使用Git命令行**

#### **步骤1：初始化本地仓库**
```bash
# 1. 解压项目文件
cd /tmp
tar -xzf /root/pdd-batch-price-project.tar.gz

# 2. 进入项目目录
cd pdd-batch-price-project

# 3. 初始化Git仓库
git init
git add .
git commit -m "初始提交：拼多多批量改价项目"
```

#### **步骤2：连接到GitHub**
```bash
# 1. 添加远程仓库（需要你的GitHub用户名）
git remote add origin https://github.com/你的用户名/pdd-batch-price-automation.git

# 2. 创建并切换到main分支
git branch -M main

# 3. 推送到GitHub
git push -u origin main
```

#### **步骤3：设置仓库信息**
```bash
# 如果需要设置用户名和邮箱
git config --global user.name "你的用户名"
git config --global user.email "你的邮箱"

# 如果需要使用个人访问令牌
git remote set-url origin https://你的用户名:你的令牌@github.com/你的用户名/pdd-batch-price-automation.git
```

### **方法三：使用GitHub CLI（推荐）**

#### **步骤1：安装和登录**
```bash
# 安装GitHub CLI
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh

# 登录GitHub
gh auth login
```

#### **步骤2：创建仓库并上传**
```bash
# 创建仓库
gh repo create pdd-batch-price-automation --public --description "拼多多批量改价自动化系统"

# 进入项目目录
cd /root/pdd-batch-price-project

# 初始化并推送
git init
git add .
git commit -m "初始提交"
git branch -M main
git remote add origin https://github.com/你的用户名/pdd-batch-price-automation.git
git push -u origin main
```

## 🔑 GitHub个人访问令牌（PAT）创建

### **步骤1：生成PAT**
1. 访问 https://github.com/settings/tokens
2. 点击 "Generate new token" → "Generate new token (classic)"
3. 设置权限：
   - ✅ repo (全部仓库权限)
   - ✅ workflow (工作流权限)
   - ✅ delete_repo (删除仓库权限，可选)
4. 生成令牌并**立即复制保存**

### **步骤2：使用PAT**
```bash
# 设置Git使用PAT
git config --global credential.helper store
echo "https://你的用户名:你的令牌@github.com" >> ~/.git-credentials

# 或直接在命令中使用
git push https://你的用户名:你的令牌@github.com/你的用户名/pdd-batch-price-automation.git
```

## 📦 项目包内容详情

### **1. README.md**
- 项目概述和功能特性
- 安装指南和快速开始
- API文档和使用示例
- 贡献指南和许可证信息

### **2. verify_installation.py**
- 验证所有技能和依赖是否安装
- 检查Python包版本
- 输出验证报告
- 错误提示和修复建议

### **3. scripts/excel_splitter.py**
- 核心Excel拆分功能
- 支持60万行数据处理
- 按5万行自动拆分
- 测试数据生成和验证

### **4. 测试数据**
- 12万行模拟数据
- 包含当当ID、拼多多SPUID、拼多多ID、价格等字段
- 拆分结果示例

## 🎯 上传后的操作

### **1. 设置仓库页面**
- 添加项目描述
- 设置主题标签
- 添加徽章（构建状态、版本等）
- 配置GitHub Pages（可选）

### **2. 配置GitHub Actions**
```yaml
# .github/workflows/test.yml
name: Test
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: 安装Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'
      - name: 安装依赖
        run: pip install -r requirements.txt
      - name: 运行测试
        run: python3 verify_installation.py
```

### **3. 创建发布版本**
```bash
# 创建第一个版本
git tag v1.0.0
git push origin v1.0.0

# 在GitHub创建Release
# 1. 访问仓库的Releases页面
# 2. 点击 "Draft a new release"
# 3. 选择标签 v1.0.0
# 4. 添加发布说明
# 5. 上传项目包文件
```

## ⚠️ 上传注意事项

### **安全注意事项**
1. **不要上传敏感信息**：如API密钥、密码、个人数据
2. **检查.gitignore**：确保忽略临时文件和配置文件
3. **使用环境变量**：敏感信息通过环境变量传递
4. **定期更新依赖**：保持依赖包最新，修复安全漏洞

### **技术注意事项**
1. **文件大小限制**：GitHub单个文件限制100MB
2. **仓库大小限制**：免费账户1GB
3. **LFS使用**：大文件使用Git LFS
4. **分支保护**：设置main分支保护规则

### **法律注意事项**
1. **选择合适许可证**：MIT、Apache 2.0、GPL等
2. **遵守第三方许可**：确保依赖包许可证兼容
3. **版权声明**：添加适当的版权声明
4. **贡献者协议**：考虑添加CLA

## 📞 上传问题排查

### **常见问题及解决方案**

#### **问题1：权限被拒绝**
```bash
# 错误信息
fatal: Authentication failed

# 解决方案
# 1. 检查PAT是否有效
# 2. 重新生成PAT
# 3. 使用SSH密钥替代HTTPS
git remote set-url origin git@github.com:你的用户名/pdd-batch-price-automation.git
```

#### **问题2：文件太大**
```bash
# 错误信息
remote: error: File is too large

# 解决方案
# 1. 使用Git LFS
git lfs install
git lfs track "*.tar.gz"
git add .gitattributes
git add pdd-batch-price-project.tar.gz
git commit -m "添加大文件支持"
```

#### **问题3：仓库已存在**
```bash
# 错误信息
fatal: remote origin already exists

# 解决方案
# 1. 删除现有远程仓库
git remote remove origin
# 2. 添加新的远程仓库
git remote add origin https://github.com/你的用户名/新仓库名.git
```

## 🎉 上传完成后的操作

### **1. 验证上传**
```bash
# 克隆仓库验证
cd /tmp
git clone https://github.com/你的用户名/pdd-batch-price-automation.git
cd pdd-batch-price-automation
python3 verify_installation.py
```

### **2. 分享项目**
- 分享GitHub链接给团队成员
- 在README中添加使用示例
- 创建项目演示视频或截图
- 在技术社区分享项目

### **3. 维护项目**
- 定期更新依赖
- 修复问题和bug
- 添加新功能
- 更新文档

## 🔗 有用的链接

### **GitHub相关**
- [创建新仓库](https://github.com/new)
- [个人访问令牌](https://github.com/settings/tokens)
- [GitHub CLI文档](https://cli.github.com/)
- [Git LFS文档](https://git-lfs.github.com/)

### **项目相关**
- [OpenClaw技能开发](https://docs.openclaw.ai/skills/)
- [Python packaging](https://packaging.python.org/)
- [MIT许可证模板](https://choosealicense.com/licenses/mit/)
- [GitHub Actions文档](https://docs.github.com/actions)

### **社区支持**
- [OpenClaw社区](https://discord.com/invite/clawd)
- [GitHub社区论坛](https://github.com/orgs/community/discussions)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/github)

---

## 📤 立即上传！

你已经准备好了所有文件，现在可以选择以下方式之一上传：

### **简单方式**：使用GitHub网页上传 `pdd-batch-price-project.tar.gz`
### **专业方式**：使用Git命令行完整上传
### **推荐方式**：使用GitHub CLI一键创建和上传

<qqfile>/root/pdd-batch-price-project.tar.gz</qqfile>

**项目包已准备好！请按照上述指南上传到GitHub。需要我帮你执行具体的上传命令吗？**