# GoHighLevel 上传说明

两个文件,贴两个地方。

## 1. `style.css` → Funnel/Website 的 Custom CSS

GHL 后台 → 进入这个 Funnel/Website → **Settings** → **Custom CSS** →
把 `style.css` 整份贴进去 → Save。

字体是用 `@import` 引进来的,写在 CSS 第一行,**不要往下挪**(@import 必须在最前面才生效)。
所以不用另外去 Head Tracking Code 加 Google Fonts。

## 2. `body.html` → 页面里的 Custom JS/HTML element

在页面里加一个 Section → 拖入 **Custom JS/HTML** element →
把 `body.html` 整份贴进去 → Save。

### 装好后调这个 Section 的设置

| 项目 | 设成 |
|---|---|
| Section width | Full width |
| Row / Column padding | 0（上下左右都是 0） |
| Section background | `#FAF0E4`（跟页面底色一致,避免两侧露白） |

## 3. 要替换的地方

`body.html` 里用 `<!-- ① ② ③ -->` 标了 7 处:

1. **LOGO** — 换成 `<img src="..." alt="INFINITE" style="height:44px">`
2. **视频** — 把 `.jy-player-inner` 里面整段换成你的 iframe,CSS 已经帮 iframe 铺满金框
3. **主 CTA 链接** — 现在是 `#jy-why`
4. **见证位 02**
5. **见证位 03**
6. **「查看更多学员分享」链接**
7. **底部 CTA 链接** — 现在是 `#`

法律三条链接(Privacy / Terms / Earning disclaimer)在 footer 里,也要接上。

## 注意

- 所有 class 都带 `jy-` 前缀,所有 CSS 都收在 `.jy-page` 里,不会影响 GHL 其他元素。
- 滚动淡入默认是**关的**,JS 跑起来才开。GHL 若挡掉 script,内容照样正常显示。
- `.jy-why li` **不能改成 `display:flex`** —— 那样会把行内的 `<b>` 拆成独立的列,整句话散开。
