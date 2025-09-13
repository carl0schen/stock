<div class="search-container">
    <h3>輸入日期前往文章</h3>
    <input type="text" id="dateInput" placeholder="例如：20250913" class="date-input">
    <button id="searchButton" class="date-button">前往</button>
</div>

### 關於本站

利用AI彙整台股盤後資訊，快速掃描法人當日籌碼。

### 資料來源

上市投信買賣超：感謝PTT網友整理。  
上市外資買賣超：感謝PTT網友整理。  
三大法人買賣金額統計表：感謝PTT網友整理。

### 資料彙整

使用Open AI的ChatGPT建立綜合摘要和解讀籌碼方向。

### 資料網址

網址格式為`https://stock.may.tw/西元年月日/`，例如：`https://stock.may.tw/20250905/`。資料從2025年9月5日開始上傳。  

### 聯絡信箱

如果資料有誤，歡迎來信告知：`stock.may.tw@ghost.tw`  

### 文章訂閱

RSS訂閱：`https://stock.may.tw/rss.xml`  
電子郵件訂閱：使用[Feedrabbit](https://feedrabbit.com/)服務訂閱。

<script>
    // 在 Zero-MD 中，需要等待 DOM 元素載入完成
    window.addEventListener('load', function() {
        const dateInput = document.getElementById('dateInput');
        const searchButton = document.getElementById('searchButton');

        // 定義跳轉函式
        function goToDatePage() {
            const date = dateInput.value;
            if (date && /^\d{8}$/.test(date)) {
                window.location.href = `/${date}/`;
            } else {
                alert('請輸入有效的日期格式 (YYYYMMDD)，例如：20250913');
            }
        }

        // 檢查元素是否存在，然後再綁定事件
        if (dateInput && searchButton) {
            // 為按鈕綁定點擊事件
            searchButton.addEventListener('click', goToDatePage);

            // 為輸入框綁定鍵盤事件
            dateInput.addEventListener('keypress', function(event) {
                if (event.key === 'Enter') {
                    goToDatePage();
                }
            });
        }
    });
</script>

<style>
    /* 這裡的 CSS 樣式會被 Zero-MD 內嵌到頁面中 */
    .search-container {
        max-width: 70ch;
        margin: auto;
        padding: 2em 1em;
        display: flex;
        flex-direction: column;
        align-items: left;
    }
    
    .search-container h3 {
        margin-bottom: 0.5em;
        font-size: 1.25em;
    }
    
    .date-input {
        padding: 0.5em;
        border: 1px solid #ccc;
        border-radius: 4px;
        width: 15em;
        font-size: 1em;
        margin-right: 0.5em;
    }
    
    .date-button {
        padding: 0.5em 1em;
        background-color: #007bff;
        color: white;
        border: none;
        border-radius: 4px;
        cursor: pointer;
    }
</style>
