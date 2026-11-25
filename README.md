# 台北市長選舉預測投票

朋友之間的非科學預測遊戲：你覺得誰會當選台北市長？

- 開場對決畫面 → 輸入姓名 → 投票 → 顯示「預測已鎖定」
- **選舉期間不公開結果**：頁面不顯示票數、比例或名單，資料庫規則也禁止讀取別人的票；票數與名單只有主辦人能在 Firebase 後台（Firestore Database → votes）查看
- 票數存在 Firebase Firestore（匿名登入，每個瀏覽器限投一票）
- 投票截止：2026/11/28 15:59（台灣時間）。前端與 `firestore.rules` 都要同步修改才會生效

## 設定
1. `firebase-config.js`：貼上 Firebase 網頁應用程式的設定值
2. Firestore「規則」：貼上 `firestore.rules` 的內容並發佈
3. Authentication → 登入方式 → 啟用「匿名」
4. GitHub Pages：Settings → Pages → Deploy from a branch → `main` / root
