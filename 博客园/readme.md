## **第一步：将文件上传到 公开的 GitHub 仓库**

- 例如，你创建了一个仓库 my-music，里面有一个文件 bgm.mp3
- 仓库地址：https://github.com/你的用户名/my-music

## 第二步：构造 jsDelivr 外链 URL

通用格式：

```js
https://cdn.jsdelivr.net/gh/用户名/仓库名@版本号/文件路径
```

✅ 示例（无版本号，默认最新）：

```js
https://cdn.jsdelivr.net/gh/yourname/my-music/bgm.mp3
```

✅ 示例（指定分支或标签，推荐用 tag 或 commit hash 避免缓存问题）：

```js
https://cdn.jsdelivr.net/gh/yourname/my-music@main/bgm.mp3
https://cdn.jsdelivr.net/gh/yourname/my-music@v1.0/bgm.mp3
https://cdn.jsdelivr.net/gh/yourname/my-music@abcd1234/bgm.mp3
```

> 🔔 注意：
>
> - 仓库必须是 Public（公开）；
> - 首次访问可能稍慢（CDN 缓存预热），之后全球加速；
> - 单文件建议 ≤ 20MB（GitHub 本身限制 100MB，但大文件不推荐用于网页加载）。

**在网页中使用示例：**

```js
<!-- 播放背景音乐 -->
<audio controls>
  <source src="https://cdn.jsdelivr.net/gh/yourname/my-music/bgm.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

<!-- 引用 JS 库 -->
<script src="https://cdn.jsdelivr.net/gh/yourname/my-project/script.js"></script>

<!-- 加载图片 -->
<img src="https://cdn.jsdelivr.net/gh/yourname/my-images/logo.png" alt="Logo">
```

⚠️ 使用注意事项

- **不要用于盗版或侵权内容**

jsDelivr 仅用于合法开源内容，若被举报会移除资源。

- **避免频繁更新“latest”链接**

CDN 有缓存（通常数小时到几天），如需立即生效，建议用 commit hash 作为版本号。

- **不要用于大文件分发（如软件安装包、视频）**

虽然技术上可行，但违反服务精神，可能被限流。

- **国内可访问性良好**

jsDelivr 在中国有节点（通过合作伙伴），比 raw.githubusercontent.com 快很多。



🔗 官方文档与工具

- 官网：https://www.jsdelivr.com
- GitHub 支持文档：https://github.com/jsdelivr/jsdelivr#github
- URL 构造器（官方）：https://www.jsdelivr.com/github
