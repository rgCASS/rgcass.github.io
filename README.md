# 智能体与社会仿真实验室 / 研究小组官方主页

> 研究小组官方网站，展示团队研究方向、成果、成员信息，助力招生宣传与对外交流。

## 📋 项目信息

- **项目地址**：https://github.com/rgcass/rgcass.github.io
- **线上访问**：https://rgcass.github.io （部署配置中...）
- **技术栈**：纯静态 HTML + TailwindCSS (via CDN)，无构建工具，简单易维护

## 🚀 本地开发预览

### 1. 克隆项目

```bash
git clone https://github.com/rgcass/rgcass.github.io.git
cd rgcass.github.io
git checkout dev
```

### 2. 本地预览

推荐使用 **VS Code + Live Server 插件**：

1. 用 VS Code 打开项目文件夹
2. 右键点击要预览的 `.html` 文件
3. 选择 "Open with Live Server"
4. 浏览器会自动打开，保存文件后自动刷新

其他静态文件服务器也可以，比如：

```bash
# Python 3
python -m http.server 8000
# 然后访问 http://localhost:8000
```

### 3. 关于 TailwindCSS

本项目使用 CDN 方式引入 TailwindCSS，**无需本地安装和编译**，直接修改 HTML 即可看到效果。

## 📝 内容更新指南

### 修改现有页面

直接打开对应的 `.html` 文件，修改文字、替换图片后保存即可。

主要页面：

| 页面 | 文件 | 说明 |
|------|------|------|
| 首页 | `index.html` | 网站首页，包含各个板块导航 |
| 认知解码 | `cognitive-decoding.html` | 认知解码研究方向专题页 |
| 类人智能体 (PsyMem) | `psymem.html` | PsyMem 研究方向专题页 |
| 社会传播模拟器 (Casevo) | `casevo.html` | Casevo 研究方向专题页 |
| 认知塑造 | `cognitive-shaping.html` | 认知塑造研究方向专题页 |

### 修改导航栏菜单

导航栏在所有页面的顶部，修改方式：

1. 打开对应 `.html` 文件
2. 搜索 `nav` 标签找到导航栏区域
3. 修改链接文字和 `href` 属性
4. 如果是当前页面，添加 `active` 类名实现高亮

示例：
```html
<a href="index.html" class="nav-link active">网站首页</a>
```

### 新增研究方向专题页

1. 复制现有的任意一个专题页 `.html` 文件作为模板
2. 修改标题、导航栏高亮、内容区域
3. 在 `index.html` 首页对应位置添加进入专题页的链接
4. 确保所有页面的导航栏都已添加新链接

### 图片存放规范

- 图片建议存放在 `assets/images/` 目录下（需要先创建）
- 引用路径使用相对路径：`assets/images/xxx.jpg`
- 建议压缩图片后再上传，减少加载时间

## 🔄 Git 提交流程

本项目遵循标准 Git 分支策略：

1. **确保在 dev 分支开发**：
   ```bash
   git checkout dev
   git pull origin dev
   ```

2. **修改内容并测试**：本地预览确认修改正确

3. **提交修改**：
   ```bash
   git add .
   git commit -m "docs: 更新xxx页面内容"
   # 或者
   git commit -m "feat: 新增xxx研究方向专题页"
   git push origin dev
   ```

4. **合并到 main 部署**：由维护者统一合并到 main 分支触发部署

### 提交信息规范参考

- `feat: 新增功能/页面`
- `fix: 修复问题`
- `docs: 更新文档/内容`
- `style: 样式调整`

## 🚢 部署说明

> 待 B009 配置 Github Pages 完成后补充

- 部署分支：`main` 分支自动部署到 Github Pages
- 回滚：如果出现问题，切换到上一个稳定版本重新合并即可

## 📄 许可证

MIT License - 详见 [LICENSE](./LICENSE)
