# 小店長工具街 — 專案檔與部署說明

## 專案形式
純 HTML、CSS、JavaScript 靜態網站，附完整可編輯原始碼與街景插畫。
不需要 npm install、編譯、Node.js 後端、資料庫或 API 金鑰。

## 檔案
- public/index.html：頁面結構、文案與表單
- public/style.css：樣式、手機版排版
- public/app.js：圖片縮放、壓縮、海報製作、ZIP 打包
- public/town.webp：街景插畫

## 放上你的伺服器
1. 解壓縮 ZIP。
2. 將 public 資料夾「裡面的四個檔案」一起上傳到網站根目錄。
   例如虛擬主機的 public_html，或你已設定的 Nginx／Apache／IIS 網站目錄。
3. 確保 index.html、style.css、app.js、town.webp 在同一層。
4. 用正式網址開啟網站，建議啟用 HTTPS。
5. 可以部署在子目錄，例如 /tools/；本專案使用相對路徑。

伺服器只需正常提供 HTML、CSS、JavaScript、WebP 靜態檔案。
不需要 SPA 路由轉寫，也不需要伺服器端圖片上傳端點。
本匯出包沒有原示範網站的登入限制；放到公開目錄後即可公開使用。

## 本機預覽
若已安裝 Python 3，在 public 目錄開啟終端機：

    python -m http.server 8080

瀏覽 http://localhost:8080 。macOS／Linux 也可使用 python3。
Python 只用於本機預覽，不是正式網站的執行依賴。

## 已有功能
- 方方照相館：批次等比例縮放至方形畫布，可選背景色，不裁切商品。
- 輕輕打包所：保留像素尺寸，調整 JPG 品質；透明部分填白。
- 大賣海報社：加入品名、價格、促銷文字，輸出 1080 × 1350 JPG。
- 成品預覽、單張下載、全部打包 ZIP。
- 圖片在訪客瀏覽器處理，不上傳到伺服器。

## 限制與注意
- 支援 JPG、PNG、WebP；每張最多 15 MB，一次最多 20 張。
- 程式略過解碼後超過 4,000 萬像素的圖片；解碼大型圖片仍可能消耗大量裝置記憶體。
- 壓縮不保證檔案一定變小；結果會顯示處理前後大小。
- 輸出為 JPG，不保留透明度或動畫。
- 請使用更新的主流瀏覽器；圖片處理依賴 Canvas 與 createImageBitmap。
- 未接入 AdSense、流量統計、帳號系統或資料儲存。
- 本包是已完成示範站的靜態原始檔，沒有 npm 專案或 Nuxt/Vue 專案。

## 修改入口
- 網站名稱、說明與教學：編輯 public/index.html。
- 配色、尺寸與手機排版：編輯 public/style.css。
- 輸出格式、畫布排版與互動：編輯 public/app.js。
- 替換街景：替換 public/town.webp，保留檔名或同步修改 HTML。

## 驗證範圍
已檢查 JavaScript 語法、檔案引用，並驗證 ZIP 完整性及中文檔名。
尚未在你的伺服器及實際瀏覽器執行端到端測試。
部署後請用橫圖、直圖和透明 PNG 各測試一次三種功能及下載。

## 後續廣告接入
目前沒有廣告碼或 AdSense 發布商 ID。
正式申請前需另外補齊隱私權政策與內容，完成你自己的帳號及網站審核。
本包不包含任何原代管平台的識別碼、憑證或部署設定。
