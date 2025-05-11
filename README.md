<a href="https://alfo0924.github.io/CssAtKeyFrames/">CssAtKeyFrames</a>
## 網站特點與優勢

這個範例網站主要展示了如何使用純 CSS 來創建一個動態的背景顏色漸變動畫。其主要特點與優勢包括：

1.  **提升視覺吸引力與使用者體驗**：動態背景能立即抓住使用者的注意力，使網站感覺更生動和現代化。它可以將靜態的網頁轉變為更具吸引力的互動體驗。
2.  **增強使用者參與度**：視覺上有趣的元素，如動畫背景，可以讓使用者更願意停留並探索網站內容，從而可能提高頁面停留時間等參與度指標。
3.  **強化品牌形象與第一印象**：精心設計的動畫背景有助於傳達品牌的個性，例如創新、活潑或優雅，並在使用者訪問的最初幾秒內留下深刻的第一印象。
4.  **引導使用者注意力**：雖然這個範例是全螢幕背景動畫，但巧妙的動態效果可以用來引導使用者的目光至特定內容或行動呼籲按鈕。
5.  **易於實現且高效能**：使用 CSS `keyframes` 製作動畫相對簡單，不需要 JavaScript 即可實現基本的動畫效果。CSS 動畫通常由瀏覽器進行優化，可以在 GPU 上運行，因此比某些 JavaScript 驅動的動畫更為流暢且效能更高，即使在中等系統負載下也能良好運行。
6.  **輕量級與 SEO 友好**：純 CSS 動畫通常是輕量級的，不會顯著增加頁面載入時間，這對使用者體驗和搜尋引擎排名是有益的。
7.  **跨瀏覽器相容性**：現代瀏覽器對 CSS 動畫有廣泛的支援，確保了在不同設備和瀏覽器上的一致體驗。
8.  **高度可自訂性**：開發者可以精確控制動畫的各個方面，如持續時間、時間函數（緩動效果）、延遲和迭代次數，以達到預期的視覺效果。

## 目標使用者族群

這種類型的背景動畫適用於多種網站和目標族群：

*   **創意產業網站**：例如設計師作品集、藝術畫廊、攝影網站等，希望透過視覺效果展示其創造力和獨特性。
*   **行銷與品牌推廣網站**：希望吸引訪客注意力，塑造鮮明品牌形象，並提升使用者互動的企業或產品網站。
*   **登陸頁面 (Landing Pages)**：需要快速抓住使用者興趣並引導其完成特定操作（如註冊、購買）的頁面。
*   **部落格或個人網站**：希望讓自己的網站更具個性化和現代感的個人或內容創作者。
*   **任何希望提升網站視覺吸引力與使用者體驗的開發者或設計師**：這是一種相對簡單且有效的方法來為網站增添動態感。

然而，需要注意的是，動畫應當是輔助性的，不應過於花哨以致分散使用者對主要內容的注意力，並應考慮到有特殊需求的使用者（例如提供減少動態效果的選項）。

## 程式碼運用邏輯解說

### HTML (index.html)

HTML 結構相對簡單，主要目的是提供一個應用 CSS 動畫的畫布以及一些基本內容。

```html



    
    
    CSS 背景動畫
    


    
        CSS 背景動畫範例
        這個背景會持續地改變顏色。
    
    


```

*   ``: 宣告文件類型為 HTML5。
*   ``: 設定頁面語言為繁體中文。
*   ``: 包含頁面的元資訊。
    *   ``: 設定字元編碼為 UTF-8。
    *   ``: 設定視口，以確保在不同設備上的響應式表現。
    *   `CSS 背景動畫`: 設定瀏覽器標籤頁上顯示的標題。
    *   ``: 連結外部 CSS 檔案 `style.css`。
*   ``: 包含頁面的可見內容。
    *   ``: 一個區塊元素，用於包裹標題和段落文字。這個 `div` 在 CSS 中被賦予了半透明背景，以便在動態變化的背景上仍能清晰閱讀文字。
    *   ``: 連結外部 JavaScript 檔案 `script.js`。雖然此範例的動畫主要由 CSS 控制，但引入 JS 檔案是常見做法，可用於未來擴展交互功能。

### CSS (style.css)

CSS 檔案是實現背景動畫的核心。

```css
body {
    margin: 0;
    padding: 0;
    height: 100vh;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    font-family: sans-serif;
    animation-name: colorChange;
    animation-duration: 10s;
    animation-timing-function: ease-in-out;
    animation-iteration-count: infinite;
}

@keyframes colorChange {
    0% {
        background-color: #FF5733;
    }
    25% {
        background-color: #33FF57;
    }
    50% {
        background-color: #3357FF;
    }
    75% {
        background-color: #F333FF;
    }
    100% {
        background-color: #FF5733;
    }
}

.content {
    padding: 20px;
    background-color: rgba(0, 0, 0, 0.3);
    border-radius: 10px;
}
```

*   **`body` 選擇器**:
    *   `margin: 0; padding: 0;`: 移除瀏覽器預設的邊距和內邊距。
    *   `height: 100vh;`: 設定 `body` 的高度為視窗高度的 100%，確保背景動畫充滿整個可見區域。
    *   `color: white;`: 設定文字顏色為白色，以便在彩色背景下易於閱讀。
    *   `display: flex; justify-content: center; align-items: center; text-align: center;`: 這些屬性用於將 `.content` 容器在頁面中水平和垂直居中，並使其內部文字居中。
    *   `font-family: sans-serif;`: 設定預設字體。
    *   `animation-name: colorChange;`: 指定要應用的 `@keyframes` 動畫的名稱。
    *   `animation-duration: 10s;`: 設定動畫完成一個週期的時間為 10 秒。
    *   `animation-timing-function: ease-in-out;`: 設定動畫的速度曲線，使動畫在開始和結束時速度較慢，中間較快，產生平滑過渡效果。
    *   `animation-iteration-count: infinite;`: 設定動畫無限次重複播放。

*   **`@keyframes colorChange` 規則**:
    *   `@keyframes` 用於定義動畫的各個階段（關鍵影格）的樣式[2][4]。動畫名稱為 `colorChange`。
    *   `0% { background-color: #FF5733; }`: 動畫開始時（0% 的時間點），背景顏色為 `#FF5733` (橘紅色)。`0%` 也可以用 `from` 關鍵字代替。
    *   `25% { background-color: #33FF57; }`: 動畫進行到 25% 的時間點時，背景顏色變為 `#33FF57` (亮綠色)。
    *   `50% { background-color: #3357FF; }`: 動畫進行到 50% 的時間點時，背景顏色變為 `#3357FF` (藍色)。
    *   `75% { background-color: #F333FF; }`: 動畫進行到 75% 的時間點時，背景顏色變為 `#F333FF` (亮紫色)。
    *   `100% { background-color: #FF5733; }`: 動畫結束時（100% 的時間點），背景顏色回到初始的 `#FF5733` (橘紅色)，以實現平滑的無限循環。`100%` 也可以用 `to` 關鍵字代替。
    *   瀏覽器會自動在這些關鍵影格之間平滑地過渡背景顏色。

*   **`.content` 選擇器**:
    *   `padding: 20px;`: 為內容區塊設定內邊距。
    *   `background-color: rgba(0, 0, 0, 0.3);`: 設定半透明的黑色背景，使文字在動態變化的彩色背景上更易於閱讀。
    *   `border-radius: 10px;`: 為內容區塊設定圓角。

### JavaScript (script.js)

```javascript
// 這個範例的背景動畫完全由 CSS 控制，
// 所以 JavaScript 檔案目前是空的。
// 如果需要更複雜的交互或基於事件的動畫，可以在這裡添加 JavaScript 代碼。
console.log("JavaScript 檔案已載入，但目前沒有執行特定功能。");
```

*   如註解所述，這個特定的背景動畫效果完全由 CSS 實現，因此 JavaScript 檔案在此範例中並未執行實際功能。
*   `console.log(...)`: 僅在瀏覽器控制台中輸出一條訊息，表明檔案已成功載入。
*   如果未來需要更複雜的動畫控制，例如根據使用者互動（如滑鼠移動、滾動）來改變動畫，或者在特定事件發生時觸發動畫，那麼 JavaScript 就會派上用場。但對於如此範例所示的連續循環動畫，CSS 是更簡潔且高效的選擇。

