# 台北市長選舉預測投票

朋友之間的非科學預測遊戲：你覺得誰會當選台北市長？

- 開場對決畫面 → 輸入姓名 → 投票 → 顯示「預測已鎖定」
- **選舉期間不公開結果**：2026/11/28 16:30（台灣時間）之前，頁面不顯示票數、比例或名單，資料庫規則也禁止讀取別人的票；16:30 一到網站自動公布。公布前主辦人可在 Firebase 後台（Firestore Database → votes）查看
- 票數存在 Firebase Firestore（匿名登入，每個瀏覽器限投一票）
- 投票截止：2026/11/28 15:59（台灣時間）；公布結果：同日 16:30。前端（`DEADLINE`、`REVEAL`）與 `firestore.rules`（15:59 與 16:30 兩處）都要同步修改才會生效

## 設定
1. `firebase-config.js`：貼上 Firebase 網頁應用程式的設定值
2. Firestore「規則」：貼上 `firestore.rules` 的內容並發佈
3. Authentication → 登入方式 → 啟用「匿名」
4. GitHub Pages：Settings → Pages → Deploy from a branch → `main` / root

## 主辦人後台
`admin.html` 是只給主辦人看的即時票數頁面（`https://<帳號>.github.io/taipei-mayor-vote/admin.html`）。進入時輸入認證碼，認證碼寫在 Firebase 後台的資料庫規則（`firestore.rules` 裡的 `CHANGE_ME_PIN` 要換成你自己的，**不要把真正的認證碼提交到公開儲存庫**）。
