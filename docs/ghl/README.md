# GoHighLevel 上传说明

## 推荐做法:只贴一次 —— `all-in-one.html`

**GHL 的 Custom CSS 栏位什么都不要放。**

页面里加一个 Section → 拖入 **Custom JS/HTML** element →
把 `all-in-one.html` 整份贴进去 → Save。完事。

字体、样式、结构、脚本全在这一块里,不碰 GHL 的全局样式表,
所以不可能再把 GHL 自己的页面弄塌。

### 装好后调这个 Section

| 项目 | 设成 |
|---|---|
| Section width | Full width |
| Row / Column padding | 0（上下左右都是 0） |
| Section background | `#FAF0E4`（跟页面底色一致,避免两侧露白） |

---

## 备选:拆成两份(只在你确定 GHL 的 Custom CSS 栏位正常时用)

- `style.css` → Settings → Custom CSS
- `body.html` → Custom JS/HTML element

⚠️ 之前用这个方式把页面弄塌过。原因是 GHL 会把你的 CSS 拼进它自己的样式表,
`@import` 一旦不在文件开头就可能让整份样式表被丢掉。
现在 `style.css` 里的 `@import` 已经拿掉了,字体改由 `body.html` 里的 `<link>` 载入 —— 但
**两份都贴时,记得 `body.html` 一定要贴,否则没有字体**。

---

## 要替换的 7 处

HTML 里用 `<!-- ① ~ ⑦ -->` 标了:

1. **LOGO** — 换成 `<img src="..." alt="INFINITE" style="height:44px">`
2. **视频** — 把 `.jy-player-inner` 里面整段换成你的 iframe,CSS 已经帮 iframe 铺满金框
3. **主 CTA 链接** — 现在是 `#jy-why`
4. **见证位 02**
5. **见证位 03**
6. **「查看更多学员分享」链接**
7. **底部 CTA 链接** — 现在是 `#`

法律三条链接（Privacy / Terms / Earning disclaimer）在 footer 里,也要接上。

---

## 改的时候注意

- 所有 class 都带 `jy-` 前缀,所有 CSS 都收在 `.jy-page` 里。
- CSS 里**没有任何非 ASCII 字符**（连注释都是英文,`「」` 用 `\300C` 转义）,避免编码问题。
- CSS 里**没有 `@import`**。要加字体请用 `<link>`。
- 滚动淡入默认是关的,JS 跑起来才开。GHL 若挡掉 script,内容照样显示。
- `.jy-why li` **不能改成 `display:flex`** —— 会把行内的 `<b>` 拆成独立的列,整句话散开。
