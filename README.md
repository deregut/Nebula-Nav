
# 🌌 Nebula Nav (星雲導航)

Nebula Nav 是一個基於 **Cloudflare Pages** 和 **Cloudflare KV** 構建的現代化、高顏值個人導航頁。它採用 React + Vite 開發，擁有磨砂玻璃（Glassmorphism）的 UI 風格，支持全端適配、服務端數據存儲、以及強大的書籤管理功能。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![React](https://img.shields.io/badge/React-19-61dafb.svg)
![Cloudflare](https://img.shields.io/badge/Cloudflare-Pages%20%26%20KV-orange.svg)

## ✨ 核心亮點

### 🎨 極致 UI 與個性化
*   **磨砂玻璃設計**: 全局動態漸變背景 + 半透明卡片，視覺效果現代、通透。
*   **視圖自定義**: 
    *   支持切換 **標準卡片** (圖標+文字) 或 **僅圖標** 模式。
    *   支持調節圖標大小 (小/中/大)。
    *   **智能天氣動態壁紙**: 
        *   支持根據實時天氣（晴、雨、雪、夜等）自動切換精美壁紙。
        *   **動態視效**: 支持 Ken Burns 效果（緩慢縮放平移），讓靜態壁紙栩栩如生。
        *   **極致性能**: 天氣壁紙 URL 自動緩存至 KV，拒絕加載閃爍。
    *   支持 **自定義背景壁紙** (手動輸入圖片 URL)。
    *   **全局字體設置**: 支持自定義字體縮放比例、文字顏色及陰影強度。
*   **沉浸式體驗**: 首頁集成大屏時鐘與日期顯示，支持動態背景遮罩。

### 🚀 強大的交互體驗
*   **全功能拖拽**:
    *   **書籤排序**: 自由拖拽書籤改變位置。
    *   **跨分組拖拽**: 將書籤拖入其他分組自動歸類。
    *   **分組排序**: 支持拖拽調整分組（分類）的上下順序。
    *   **快捷欄排序**: 頂部置頂圖標也支持橫向拖拽。
*   **移動端優化**: 完美適配手機/平板，支持 **長按呼出菜單** (帶震動反饋)，解決移動端右鍵難題。

### 🛠️ 深度書籤管理
*   **書籤治理**:
    *   **查重工具**: 內置強大的查重功能，支持按 **URL**、**標題** 或 **主域名** 查找並批量清理重複書籤。
    *   **分組管理**: 支持新建、重命名分組，以及點擊分組標題進行摺疊/展開。
*   **搜索增強**: 集成聚合搜索欄，支持自定義搜索引擎（Google/Bing/Baidu/DDG），支持直接打開搜索結果。
*   **數據導入/導出**:
    *   支持導入 Chrome/Edge 導出的 HTML 書籤文件。
    *   支持導入/導出項目專屬的 JSON 全量備份（包含配置信息）。
    *   添加書籤時自動提取網站 Favicon 圖標，支持圖片壓縮上傳。

### 🧩 智能小組件 (Widgets)
*   **天氣組件**:
    *   **免配置定位**: 集成 IP 定位功能，無需瀏覽器授權即可自動獲取當前城市天氣。
    *   **位置優化**: 支持顯示精確的城市名稱（通過反向地理編碼）。
    *   **本地化**: 完美支持中文天氣描述（如“晴”、“多雲”），顯示實時溫度、溼度、風速。
*   **市場組件 (TradingView)**:
    *   **專業圖表**: 引入 TradingView Mini Symbol Overview，默認展示 **上證指數** (SSE:000001) 走勢。
    *   **美觀**: 支持暗色模式，動態交互。

### 🔐 安全與架構
*   **Serverless 架構**: 前端託管於 Cloudflare Pages，數據存儲於 Cloudflare KV，全球低延遲。
*   **隱私保護**: 訪問、編輯、管理均需通過密碼驗證 (KV 鑑權)。

## 🛠️ 技術棧

*   **Frontend**: React 19, TypeScript, Tailwind CSS, Vite
*   **Interaction**: @dnd-kit (Core, Sortable, Utilities)
*   **Backend**: Cloudflare Pages Functions (Edge Runtime)
*   **Database**: Cloudflare KV

## 🔄 最近更新 (Changelog)

### v1.2.0 - Visual & Experience Upgrade
*   **動態背景系統**: 
    *   新增 **Ken Burns** 動態效果開關，使天氣壁紙具備電影級的緩慢移動視效。
    *   新增 **壁紙 KV 緩存** 機制，首次加載後記錄 URL，再次訪問時秒開無閃爍。
*   **字體個性化**:
    *   新增全局 **字體設置** 面板，可調節字體大小縮放、全局文字顏色及文字陰影強度。
    *   解決了書籤文字顏色與 Tailwind 樣式衝突的問題。
*   **UI 優化**:
    *   底部統計欄漢化為 "書籤數量" 和 "KV 存儲"。
    *   恢復編輯模式入口為標準的齒輪圖標。
    *   優化了 Footer 的字體顯示效果。
    *   新增底部 **Telegram** 聯繫方式鏈接，方便反饋問題。

### v1.1.0 - Weather & Market Optimization
*   **智能天氣背景**: 新增根據實時天氣自動切換背景圖的功能。
*   **位置顯示修正**: 天氣組件現在能正確顯示所在的城市名稱，而非籠統的“當前位置”。
*   **市場組件修復**: 修復了 TradingView 組件加載失敗的問題，改用穩定性更高的上證指數代碼 (`SSE:000001`)。

### v1.0.0 - Widget & UI Upgrade
*   **重構天氣組件**:
    *   引入 `ipapi.co` 實現 IP 自動定位。
    *   增加 WMO 天氣代碼到中文的映射。
    *   優化 UI 佈局。
*   **移動端優化**:
    *   頂部時間/小組件區域在移動端支持橫向滑動 (Snap Scroll)。

## 🚀 部署指南

本項目專為 Cloudflare Pages 設計，開箱即用。

### 1. 前置準備
*   一個 Cloudflare 賬號。
*   GitHub 賬號。

### 2. 部署到 Cloudflare Pages

1.  **Fork** 本倉庫到你的 GitHub。
2.  登錄 Cloudflare Dashboard，進入 **Pages**。
3.  點擊 "Connect to Git"，選擇你的倉庫。
4.  **構建配置**:
    *   **Framework preset**: Vite
    *   **Build command**: `npm run build`
    *   **Output directory**: `dist`
5.  點擊 "Save and Deploy"。

### 3. 必要的配置 (關鍵步驟)

部署完成後，你必須配置 KV 和環境變量才能正常使用。

#### A. 創建 KV 命名空間
在 Cloudflare Dashboard -> Workers & Pages -> KV 中，創建一個新的 Namespace，命名為 `nebula_kv` (或者任意你喜歡的名字)。

#### B. 綁定 KV 到 Pages
1.  進入你的 Pages 項目 -> **Settings** -> **Functions**。
2.  找到 **KV Namespace Bindings**。
3.  添加綁定:
    *   **Variable name**: `NAV_KV` (⚠️ 必須完全一致，代碼中讀取此變量)
    *   **KV Namespace**: 選擇你剛才創建的 `nebula_kv`。

#### C. 設置環境變量
1.  進入你的 Pages 項目 -> **Settings** -> **Environment variables**。
2.  添加以下變量 (Production 和 Preview 都要加):
    *   `AUTH_PASSWORD`: 設置你的訪問/管理密碼 (例如 `your_secure_password`)。
    *   `VITE_SITE_TITLE`: (可選) 自定義網站標題，默認為 "星雲導航"。
    *   `REDIRECTS`: (可選) 路由重定向配置，見下文。

#### D. 重新部署
配置修改後，需要**重新部署**一次（Retry deployment）才能生效。

## ⚙️ 進階設置

### 路由重定向
項目位於 `functions/_middleware.ts` 中的中間件支持簡易的短鏈接跳轉功能。
你可以在環境變量 `REDIRECTS` 中配置 JSON 映射表。

**配置示例 (環境變量值):**
```json
{
  "emby": "https://emby.yourdomain.com",
  "blog": "https://blog.yourdomain.com",
  "monitor": "https://uptime.status.page"
}
```

**支持兩種跳轉模式：**

1.  **路徑跳轉 (推薦)**: 
    *   直接支持 `*.pages.dev` 域名。
    *   訪問 `https://your-nav.pages.dev/emby` -> 自動跳轉至 `https://emby.yourdomain.com`。

2.  **子域名跳轉 (高級)**:
    *   僅在使用 **自定義域名** 時生效 (需在 DNS 配置泛解析或對應 CNAME)。
    *   訪問 `https://emby.your-custom-domain.com` -> 自動跳轉至 `https://emby.yourdomain.com`。

## 🤝 貢獻

歡迎提交 Issue 或 Pull Request！

## 📄 License

MIT License.