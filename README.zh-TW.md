# scrabble

一個簡單的工具，用於從遠端伺服器上暴露的 `.git` 資料夾中恢復 Git 儲存庫。

## 快速開始

1.  **下載腳本：**
    ```bash
    curl -O https://raw.githubusercontent.com/denny0223/scrabble/refs/heads/master/scrabble
    ```

2.  **賦予執行權限：**
    ```bash
    chmod +x scrabble
    ```

3.  **執行腳本：**
    ```bash
    ./scrabble <url> [directory]
    ```

## 使用方式

`scrabble <url> [directory]`

### 參數：

*   `<url>`: 儲存庫 `.git` 資料夾的完整 URL (例如：`http://example.com/my-project.git/`)。
*   `[directory]` (選填): 要將儲存庫複製到的本地資料夾。
    *   如果未提供，腳本將預設使用從 URL 派生的儲存庫名稱作為資料夾名稱 (例如：從 `http://example.com/my-project.git/` 派生出 `my-project`)。

### 重要注意事項：

*   您需要確保目標 URL 具有暴露的 `.git` 資料夾。
*   本腳本**不會**覆蓋現有資料夾。如果目標資料夾已存在，腳本將會報錯並終止執行，以防止意外的資料遺失。請移除現有資料夾或選擇不同的名稱。
*   此工具旨在將儲存庫複製到一個**新的、空的資料夾**中。請勿在現有的 Git 儲存庫中執行此工具，否則它將覆蓋其內容。

## 範例

```bash
# 複製到名為 'my-project' 的資料夾
scrabble http://example.com/my-project.git/

# 複製到名為 'my-local-repo' 的特定資料夾
scrabble http://example.com/my-project.git/ my-local-repo
```
