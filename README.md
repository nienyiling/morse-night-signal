# 夜航電報 · NIGHT SIGNAL

玩遊戲學摩斯電碼。

## ▶ 立即遊玩

### **https://morse-night-signal.netlify.app**

打開網址就能玩，**免安裝、免註冊**，手機和電腦都可以。

> 海上的夜裡，無線電是你唯一的聲音。
> 握住電鍵，把求救訊號敲出去——摩斯電碼，會在你手裡慢慢長出來。

🎧 **記得戴耳機或開喇叭**，聲音是這個遊戲的重點。敲出成績還能上全球排行榜。

---

## 這個 repo 目前有什麼

- `index.html`：整個遊戲（單檔，含 CSS／JS）。內容取自線上版現行頁面原始碼。

## ⚠️ 這個 repo 目前**還不是**完整的部署來源

線上站另有 3 個 Netlify Functions，它們的原始碼**不在這個 repo 裡**（當初是以 zip 手動上傳部署的）：

| 端點 | function | 用途 |
|---|---|---|
| `/api/leaderboard` | `leaderboard` | 全球排行榜讀寫 |
| `/api/messages` | `messages` | 留言 |
| `/api/stats` | `stats` | 統計 |

因此：

- **不要**把 Netlify 專案綁定到這個 repo 做自動部署。一旦綁定並觸發建置，部署包裡沒有 `netlify/functions/*`，線上那 3 個 function 會被整組清掉，排行榜與留言直接死掉。
- 要改成 GitHub 自動部署，得先把這 3 支 function 的原始碼補進 `netlify/functions/`（連同 Netlify Blobs 等相依設定），確認齊全後再綁。
- 在那之前，線上站維持原本的手動上傳部署方式。
