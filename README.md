# 民雄椪皮麵 嘉義分店｜網站專案

正式網站已於 2026-09-28 部署到 Netlify。

- **正式主站**：https://minxiong-pongpi-chiayi.netlify.app/
- **GitHub 版本庫／備援**：https://github.com/wenbo0285-crypto/minxiong-pongpi-chiayi
- **部署架構**：Netlify 對外服務；GitHub 保存版本與備援
- **Netlify Team**：NSNLINEAGE

## 網站目標

- 行動版轉換：電話、Google 地圖導航 CTA
- Local SEO：店名、地址、電話、營業時間、Geo 座標、Restaurant / LocalBusiness JSON-LD
- 在地搜尋語意：嘉義東區、興業東路、嘉義椪皮麵、嘉義小吃、嘉義麵店
- GEO / AI 可讀性：主要事實直接寫在 HTML，另有 llms.txt，robots.txt 明確允許 OAI-SearchBot
- FAQ：補足「椪皮麵是什麼／店在哪／營業時間／推薦品項」的自然語言問答

## 目前公開資訊

- 店名：民雄椪皮麵 嘉義分店
- 地址：嘉義市東區興業東路30號
- 電話：05-228-3666
- 營業時間：週三～週日 11:00–20:00；週一、週二公休
- 座標：23.4692672, 120.4547953
- 主要品項：椪皮麵、骨仔肉、粉腸湯

## 圖片授權

部分店面與餐點照片已取得「台南咬一口」作者同意使用。
網站每張使用照片均標示來源與原文連結，頁尾保留作者若認為呈現方式不適合，可聯絡後儘速調整或下架之說明。

來源：
https://eattnn.com/05-228-3666/

## SEO / GEO 後續

1. Google Search Console 驗證 Netlify 正式網址
2. 提交：https://minxiong-pongpi-chiayi.netlify.app/sitemap.xml
3. Google 商家檔案網站欄位改成 Netlify 正式網址
4. 定期更新真實菜單、營業時間、店內照片
5. 若未來購買自有網域，再將 canonical、og:url、sitemap、robots 與 Google 商家統一換成自有網域

## 網址規則

搜尋引擎的主版本固定為 Netlify：
https://minxiong-pongpi-chiayi.netlify.app/

GitHub Pages 若仍可存取，只作備援；頁面 canonical 應持續指向 Netlify，避免重複內容互相競爭。

## GEO 備註

llms.txt 屬於額外的機器可讀內容，不應視為 Google 或 AI 排名保證。真正重要的是：
- 公開可索引 HTML
- 明確且一致的店名／地址／電話
- 結構化資料
- 真實第三方提及
- Google 商家檔案
- 可被搜尋引擎與 AI 搜尋爬蟲存取
