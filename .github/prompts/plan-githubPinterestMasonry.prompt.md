## Plan: GitHub README Pinterest 瀑布流 Stylus CSS

创建一个 Stylus 用户样式文件，将 GitHub README 中包含图片的内容块转换为 Pinterest 风格的瀑布流布局。使用 CSS Columns 实现自然瀑布流效果，隐藏标题和文本，仅保留图片卡片，并提供可配置的间距和主题变量。

### Steps

1. **创建 Stylus 用户样式主文件** - 新建 `github-pinterest-masonry.user.css`，包含 `@-moz-document domain("github.com")` 规则和 UserCSS 元数据头
2. **定义可配置变量** - 在 `:root` 中设置瀑布流列数、间距、卡片圆角/阴影/背景、图片悬停效果、主题色等 CSS 自定义属性
3. **实现瀑布流容器** - 对 `.markdown-body` 应用 `column-count` 和 `column-gap`，配合 `break-inside: avoid` 防止卡片断裂
4. **隐藏非图片元素** - 使用 `display: none` 隐藏 `h2-h6`、`pre`、`code`、`.highlight`、不含图片的 `p` 段落和 `strong`/`em` 文本
5. **优化图片与 flex 容器** - 图片设为 `width: 100%` 自适应，将用户示例中的 `div[style*="flex"]` 改为块级排列，添加悬停缩放动画

### Further Considerations

1. ~~**响应式列数** - 是否需要添加 `@media` 查询在不同屏幕宽度自动切换列数？（如移动端 1 列、平板 2 列、桌面 3+ 列）~~ ✅ 已实现 (768px/1024px/1440px 断点)
2. ~~**图片懒加载支持** - 需要处理 GitHub 的图片懒加载机制，确保所有图片都能正确显示？~~ ✅ 已实现 (loading="lazy" 占位符样式)
3. **兼容性测试** - 兼容 Chrome ✅ (使用 `:has()` 选择器，Chrome 105+)
4. 每次迭代后完善本 plan

### Completed

- [x] Step 1: 创建 `github-pinterest-masonry.user.css` 主文件，包含 UserCSS 元数据头
- [x] Step 2: 定义可配置变量 (列数、间距、圆角、阴影、背景色、悬停缩放)
- [x] Step 3: 实现瀑布流容器 (CSS Columns + break-inside: avoid)
- [x] Step 4: 隐藏非图片元素 (h1-h6, pre, code, 纯文本 p, blockquote, hr)
- [x] Step 5: 优化图片与 flex 容器 (覆盖 inline style, 悬停动画)