# CODEX_HANDOFF.md

# 民雄椪皮麵 嘉義分店｜Codex 專案交接文件

> 更新日期：2026-10-16  
> 專案狀態：已正式上線，可繼續維護、優化 SEO / GEO、更新內容與部署。

---

## 1. 專案目標

這是一個「民雄椪皮麵 嘉義分店」的正式店家官網。

主要目標：

1. 建立可信、可公開使用的正式店家網站。
2. 強化 Local SEO：
   - 嘉義椪皮麵
   - 嘉義東區小吃
   - 嘉義東區麵店
   - 興業東路美食
   - 興業東路麵店
   - 嘉義古早味小吃
   - 嘉義骨仔肉
   - 嘉義粉腸湯
3. 強化 GEO / AI 可讀性。
4. 引導顧客：
   - Google 地圖導航
   - 撥打電話
   - 了解店家與餐點
5. 後續可能作為在地店家網站服務的示範案例。

---

## 2. 本機專案位置

主工作目錄：

```text
C:\Users\寶寶馨2\Desktop\民雄椪皮麵_嘉義分店_官網
```

GitHub / 部署用 repo 工作目錄：

```text
C:\Users\寶寶馨2\Desktop\民雄椪皮麵_嘉義分店_官網\deploy
```

### 重要

- 平常網站內容修改，優先修改主工作目錄。
- 要同步 GitHub 時，再同步到 `deploy\`。
- 不要隨意刪除授權圖片、來源紀錄、SEO 文件。

---

## 3. 正式網站與備援架構

### 正式主站：Netlify

```text
https://minxiong-pongpi-chiayi.netlify.app/
```

Netlify site name：

```text
minxiong-pongpi-chiayi
```

Netlify Site ID：

```text
ed58201c-fe23-4635-8990-6c72e13d614c
```

Netlify Team：

```text
NSNLINEAGE
```

Netlify account slug：

```text
wenbo0285
```

Netlify 管理頁：

```text
https://app.netlify.com/projects/minxiong-pongpi-chiayi
```

### GitHub：版本庫 / 備援

Repo：

```text
https://github.com/wenbo0285-crypto/minxiong-pongpi-chiayi
```

GitHub 帳號：

```text
wenbo0285-crypto
```

Branch：

```text
main
```

### 重要架構原則

```text
Netlify = 正式主站
GitHub = 程式碼版本庫 / 備援
```

不要把 GitHub Pages 再改成 canonical 主站。

目前所有：

- canonical
- og:url
- og:image
- robots.txt
- sitemap.xml

都應指向 Netlify。

---

## 4. 目前部署方式

目前 Netlify site 已與本機專案連結，且可以用 Netlify CLI 手動正式部署。

Netlify CLI 安裝在專案內：

```text
C:\Users\寶寶馨2\Desktop\民雄椪皮麵_嘉義分店_官網\.netlify-cli-temp
```

CLI：

```text
.netlify-cli-temp\node_modules\.bin\netlify.cmd
```

### 正式部署指令

在：

```text
C:\Users\寶寶馨2\Desktop\民雄椪皮麵_嘉義分店_官網\deploy
```

執行：

```powershell
& 'C:\Users\寶寶馨2\Desktop\民雄椪皮麵_嘉義分店_官網\.netlify-cli-temp\node_modules\.bin\netlify.cmd' deploy --prod --dir .
```

### 部署前建議流程

1. 修改主工作目錄內容。
2. 測試網站。
3. 同步要公開的檔案到 `deploy\`。
4. 在 `deploy\` 內：
   - `git status`
   - `git log --oneline -n 5`
5. Commit。
6. Push：
   - 必須明確 push `origin main`
7. 執行 Netlify production deploy。
8. 外網確認：
   - 首頁 200
   - robots.txt 200
   - sitemap.xml 200
   - llms.txt 200
   - 主要圖片 200
9. 確認 canonical 仍指向 Netlify。

---

## 5. Netlify 設定

`netlify.toml`：

```toml
[build]
  publish = "."

[build.environment]
  NODE_VERSION = "20"

[[headers]]
  for = "/assets/*"
  [headers.values]
    Cache-Control = "public, max-age=31536000, immutable"
```

目前是純靜態網站，不需要 framework build。

---

## 6. 店家核心資料

### 店名

```text
民雄椪皮麵 嘉義分店
```

### 地址

```text
600 嘉義市東區興業東路30號
```

### 電話

```text
05-228-3666
```

國際格式：

```text
+886-5-228-3666
```

### Google Maps

```text
https://maps.app.goo.gl/QmqFHKa6T9PSeqWr5
```

### 座標

```text
23.4692672, 120.4547953
```

### 目前網站使用的營業時間

```text
週三～週日 11:00–20:00
週一、週二公休
```

注意：

營業時間未來仍應以店家與 Google 商家最新資訊為準。

---

## 7. 網站主要檔案

### 核心

```text
index.html
styles.css
script.js
robots.txt
sitemap.xml
llms.txt
manifest.webmanifest
netlify.toml
```

### 圖片

```text
assets\photos\
```

主要正式圖片：

```text
pongpi-noodles.webp
pongpi-closeup.webp
bone-meat.webp
intestine-soup.webp
store-exterior.webp
store-counter.webp
store-interior.webp
store-clean.webp
menu-board.webp
meal-set.webp
```

目前正式網站優先使用 WebP。

原始 JPG 不要放到公開部署 repo，除非有明確需要。

---

## 8. 圖片授權｜非常重要

目前使用的部分真實照片來自：

```text
台南咬一口
https://eattnn.com/05-228-3666/
```

### 授權狀態

已取得作者同意。

作者允許目前官網先使用，條件：

1. 圖片下方標示引用來源。
2. 附上原文章網址。
3. 網站需保留說明：
   - 如果作者日後認為圖片使用方式、版面或情境不適合，
   - 作者可以聯絡店家，
   - 店家會儘速調整或下架。

### 網站目前使用的來源文字

圖片附近：

```text
圖片引用來源：台南咬一口
原文網址：https://eattnn.com/05-228-3666/
```

頁尾完整說明概念：

```text
本網站部分照片經原作者同意引用，僅用於「民雄椪皮麵 嘉義分店」
官方網站之店家介紹與資訊展示。
若原作者日後認為圖片使用方式、版面呈現或相關內容有不適合之處，
請與我們聯繫，我們將於收到通知後儘速調整或下架。
```

### 不可做

- 不可移除來源標示。
- 不可把照片當作自己拍攝。
- 不可轉售照片。
- 不可擅自授權第三方使用。
- 不可把「作者可要求下架」的聲明刪掉。
- 不可因為有授權，就任意把原圖拿去做其他品牌商業素材。

---

## 9. 授權資料與參考照

原始參考 / 授權資料：

```text
待取得授權_參考照片\
```

雖然資料夾名稱仍叫「待取得授權」，實際上目前：

```text
台南咬一口 = 已取得授權
```

授權紀錄：

```text
待取得授權_參考照片\授權來源與聯絡文案.md
```

該文件已更新為已取得授權狀態。

不要因為資料夾名稱誤判成「尚未授權」。

---

## 10. 真實餐點呈現原則

早期曾使用 AI 生成人像式／情境式餐點圖，但出現一個問題：

AI 會自行添加實際店內不存在的配料。

因此後續原則：

### 真實餐點

優先使用已授權實拍照片。

### 如果未來再生成 AI 圖

必須：

1. 先找實際店家照片做視覺與配料參考。
2. 不可以亂增加：
   - 滷肉塊
   - 青菜
   - 額外蔥花
   - 不存在的配料
3. 不可把生成圖誤稱為「店內實拍」。

實際椪皮麵外觀應以授權照片為最高準則。

---

## 11. SEO 現況

目前 `index.html` 已包含：

- title
- meta description
- canonical
- Open Graph
- twitter card
- LocalBusiness / Restaurant JSON-LD
- 地址
- 電話
- GPS
- 營業時間
- cuisine
- Google Maps
- FAQ
- 真實店家語意內容

### Canonical

必須保持：

```text
https://minxiong-pongpi-chiayi.netlify.app/
```

### OG URL

同上。

### OG Image

目前正式圖片：

```text
https://minxiong-pongpi-chiayi.netlify.app/assets/photos/pongpi-noodles.webp
```

---

## 12. Schema

目前使用：

```json
"@type": ["Restaurant", "LocalBusiness"]
```

包含：

- name
- alternateName
- description
- telephone
- address
- geo
- servesCuisine
- openingHoursSpecification
- hasMap
- menu
- knowsAbout

### 不要亂加

不要自行增加：

- AggregateRating
- Review
- 虛構評價
- 虛構星等
- 虛構價位

除非資料來源與 Schema 規範完全確認。

---

## 13. GEO / AI 可讀性

目前有：

```text
llms.txt
```

內容包含：

- 店名
- 地址
- 電話
- 官方網站
- 地圖
- 招牌餐點
- 地理語意

注意：

`llms.txt` 是補充資訊。

不要宣稱它是 Google 或 AI 排名保證因素。

真正重要的仍是：

1. 公開 HTML
2. 實體資料一致
3. Google Business Profile
4. LocalBusiness Schema
5. 第三方可信提及
6. Search Console
7. sitemap
8. 真實內容與照片

---

## 14. robots.txt

目前允許一般搜尋引擎與 AI 搜尋爬蟲。

包括：

```text
User-agent: *
Allow: /

User-agent: OAI-SearchBot
Allow: /

User-agent: ChatGPT-User
Allow: /
```

Sitemap 必須保持：

```text
https://minxiong-pongpi-chiayi.netlify.app/sitemap.xml
```

---

## 15. sitemap.xml

目前主頁：

```text
https://minxiong-pongpi-chiayi.netlify.app/
```

若未來增加：

- 菜單頁
- 椪皮介紹頁
- 店家故事
- 交通停車
- 最新消息
- FAQ 獨立頁

記得同步更新 sitemap。

---

## 16. 已知媒體 / 外部可信來源

目前網站有引用或參考：

### 食尚玩家 / TVBS

```text
https://supertaste.tvbs.com.tw/hot/361568
```

可作為：

- 媒體收錄
- 外部實體佐證

不要誤稱為官方合作或代言。

---

## 17. 目前網站 UX

已完成：

- RWD
- 手機固定 CTA
- Google 地圖導航
- 電話連結
- 店家介紹
- 椪皮介紹
- 招牌品項
- 真實店面照片
- 真實餐點照片
- FAQ
- 媒體提及
- 圖片來源聲明

---

## 18. 不要隨意改的地方

### A. 店名 / NAP

NAP：

```text
Name
Address
Phone
```

必須盡量與 Google Business Profile 一致。

不要自己改：

- 店名
- 地址
- 電話

除非使用者明確要求或有新資料。

### B. Canonical

Netlify 是主站。

不要改回 GitHub Pages。

### C. 圖片授權文字

不可刪。

### D. 真實餐點

不要用 AI 自己猜配料。

### E. Google 評價

不要自動把目前星等 / 評論數寫進 Schema。

它會變動。

---

## 19. Git 提交規則

執行 commit 前：

```powershell
git log --oneline -n 5
```

保持目前 commit style 簡短、英文、動詞開頭，例如：

```text
Launch official site
Add Netlify deployment config
Make Netlify the primary site
Document Netlify primary deployment
```

Push 時：

```powershell
git push origin main
```

不要省略 branch。

---

## 20. 目前最新 GitHub 狀態

最近重要 commit：

```text
8d13e3d Launch official site
742dd32 Add Netlify deployment config
ba9135b Make Netlify the primary site
2935920 Document Netlify primary deployment
```

---

## 21. 網站驗證標準

任何正式發布前至少檢查：

### HTTP

```text
/                                 200
/robots.txt                       200
/sitemap.xml                      200
/llms.txt                         200
/assets/photos/pongpi-noodles.webp 200
```

### HTML

確認：

- canonical 正確
- og:url 正確
- og:image 正確
- JSON-LD 可 parse
- 所有 img 有 alt
- 所有內部 anchor 存在
- 沒有圖片 404
- 沒有把 GitHub Pages 當正式主網址

---

## 22. 現有本機驗證工具

主工作目錄有：

```text
validate_site.py
optimize_images.py
預覽網站.cmd
```

用途：

### validate_site.py

檢查：

- image alt
- 本地圖片存在
- anchor
- JSON-LD
- 圖片來源標示

### optimize_images.py

JPG → WebP。

正式網站盡量使用 WebP。

---

## 23. 下一階段工作｜優先順序

Codex 接手後，建議依照以下優先級執行。

### P0：Google Search Console

目前尚未確認已完成。

要做：

1. 新增：
   ```text
   https://minxiong-pongpi-chiayi.netlify.app/
   ```
2. 驗證網站。
3. 提交：
   ```text
   https://minxiong-pongpi-chiayi.netlify.app/sitemap.xml
   ```
4. Request indexing。

### P0：Google Business Profile

將「網站」欄位設為：

```text
https://minxiong-pongpi-chiayi.netlify.app/
```

目的：

建立：

```text
Google Maps 店家實體 ↔ 官方網站
```

關聯。

### P1：確認真實營業資訊

再次向店家確認：

- 營業時間
- 公休日
- 電話
- 菜單
- 價格
- 臨時休息規則

### P1：正式菜單

目前舊食記裡的價目表可能已過期。

不要直接把舊價目表當最新菜單。

應取得最新：

- 品項
- 價格
- 是否停售
- 大小碗
- 湯品
- 小菜

再做正式菜單頁。

### P1：Local SEO Landing Pages

可以增加：

```text
/chiayi-pongpi-noodles/
/menu/
/about-pongpi/
/visit/
/faq/
```

但不要為了 SEO 大量生成低品質重複頁。

### P2：Analytics

可導入 GA4。

重要事件：

- 點 Google Maps
- 點電話
- 點媒體報導
- 點來源連結

### P2：正式網域

目前不需要購買也能運作。

未來若購買自有網域：

例如：

```text
pongpi.tw
chiayipongpi.tw
minxiongnoodles.tw
```

必須同步更新：

- Netlify custom domain
- canonical
- og:url
- og:image
- robots
- sitemap
- llms.txt
- Search Console
- Google Business Profile
- README

---

## 24. Google Pages / GitHub Pages 注意

GitHub Pages 曾經部署過：

```text
https://wenbo0285-crypto.github.io/minxiong-pongpi-chiayi/
```

目前它不是正式主站。

不要讓它的 canonical 指向自己。

如果未來要保留 GitHub Pages：

應該：

- canonical 指向 Netlify
- 或做 redirect（如果架構允許）

目標是避免兩個網址彼此競爭搜尋排名。

---

## 25. 專案執行原則

Codex 在這個專案工作時：

1. 不要只改一半。
2. 多項任務逐項核對。
3. 宣稱完成前要實際測試。
4. 若修改部署相關內容：
   - 本機
   - GitHub
   - Netlify
   三者都要確認。
5. 若修改網址：
   - canonical
   - OG
   - sitemap
   - robots
   - llms
   - README
   全部一起檢查。
6. 不要捏造店家資訊。
7. 不要捏造評價。
8. 不要偷偷移除授權來源。
9. 不要把 AI 圖當實拍。
10. 優先保留目前真實感與在地感，不要把網站改成過度科技、SaaS、模板感。

---

## 26. 視覺方向

目前方向：

- 嘉義古早味
- 溫暖
- 真實小吃店
- 不過度網美
- 不鏽鋼桌
- 白鐵工作台
- 橘色圓凳
- 實際店面
- 真實餐點

不要改成：

- 高級餐廳
- Fine Dining
- 日式拉麵店
- 西式咖啡館
- 過度 AI 感
- 假裝復古、實際與店內不符的場景

---

## 27. 成功標準

網站的成功不是「看起來漂亮」而已。

真正 KPI：

1. Google 能收錄。
2. Google 商家與官網連結。
3. 搜尋：
   - 嘉義椪皮麵
   - 嘉義東區小吃
   - 興業東路美食
   能逐漸出現。
4. 使用者能快速：
   - 導航
   - 打電話
5. 店家資訊正確。
6. 真實照片建立信任。
7. 頁面載入快。
8. 未來可觀察流量與轉換。

---

## 28. 接手後第一件事

Codex 進入專案後，先做：

```powershell
cd "C:\Users\寶寶馨2\Desktop\民雄椪皮麵_嘉義分店_官網"

Get-ChildItem
```

然後閱讀：

```text
CODEX_HANDOFF.md
README.md
SEO_GEO_執行計畫.md
待取得授權_參考照片\授權來源與聯絡文案.md
```

再進入：

```text
deploy\
```

查看：

```powershell
git status
git log --oneline -n 5
git remote -v
```

在沒有理解目前架構前，不要直接大改或重新初始化專案。

---

# 最後一句

這個專案目前已經是「正式上線中的店家官網」，不是 Demo。

任何變更都要以：

```text
真實資料
授權合規
Local SEO
GEO 可讀性
行動轉換
穩定部署
```

為最高優先。
