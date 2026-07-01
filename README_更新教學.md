# 慢日子研究所網站更新教學

這份網站是靜態 GitHub Pages，可直接放到 GitHub repo：`https://github.com/CY-Ou/slowdayslab`。

## 檔案結構

```text
slowdayslab-site/
  index.html
  assets/
    SlowDaysLab_Logo_Horizontal.png
    SlowDaysLab_Logo_Square.png
  media/
    README.md
  posts/
```

## 更新首頁文字

1. 用文字編輯器打開 `index.html`。
2. 搜尋要改的標題或段落，例如 `最新分享`、`照片相簿`。
3. 直接修改 HTML 中的中文文字。
4. 儲存後用瀏覽器開啟 `index.html` 檢查。

## 上傳照片

1. 把照片放進 `media/`，建議檔名使用英文與數字，例如：

```text
media/2026-taichung-walk-01.jpg
media/2026-taichung-walk-02.jpg
```

2. 在 `index.html` 的相簿卡片，把原本的色塊改成圖片。例如：

```html
<article class="photo-card">
  <img class="photo-img" src="media/2026-taichung-walk-01.jpg" alt="台中散步照片">
</article>
```

3. 若要讓照片漂亮填滿卡片，在 `<style>` 裡加入一次即可：

```css
.photo-img {
  width: 100%;
  height: 100%;
  min-height: 300px;
  object-fit: cover;
  display: block;
}
```

建議照片先壓縮到 1600px 寬以內，網站會載入比較快。

## 上傳影片

建議影片不要直接放 GitHub，請先上傳 YouTube，再把連結放到網站。

### 嵌入單支 YouTube 影片

1. 打開 YouTube 影片。
2. 點「分享」。
3. 複製影片網址，例如：

```text
https://www.youtube.com/watch?v=VIDEO_ID
```

4. 改成嵌入格式：

```html
<iframe
  src="https://www.youtube.com/embed/VIDEO_ID"
  title="影片標題"
  loading="lazy"
  allowfullscreen></iframe>
```

`VIDEO_ID` 是 `watch?v=` 後面的那串字。

## 新增一篇文章卡片

在 `index.html` 搜尋 `<div class="post-grid">`，複製一整段 `<article class="post-card">...</article>`，然後改標題、日期、描述與連結。

範例：

```html
<article class="post-card">
  <div class="post-media"><span>台南旅行</span></div>
  <div class="post-body">
    <div class="meta"><span>Travel</span><span>2026.07</span></div>
    <h3>台南兩日慢旅行</h3>
    <p>老屋、巷弄、咖啡與傍晚散步的紀錄。</p>
  </div>
</article>
```

## 發佈到 GitHub Pages

1. 進入 GitHub Dashboard：`https://github.com/CY-Ou/slowdayslab`
2. 上傳或覆蓋 `index.html`、`assets/`、`media/`。
3. 等 GitHub Pages 更新，通常 1 到 3 分鐘後會出現在：

```text
https://cy-ou.github.io/slowdayslab/
```

## 建議維護方式

- 照片放 `media/`
- Logo、固定圖示放 `assets/`
- 長文章可之後放 `posts/`
- 影片放 YouTube，網站只放嵌入碼或連結
- 每次更新前先在本機開 `index.html` 確認排版
