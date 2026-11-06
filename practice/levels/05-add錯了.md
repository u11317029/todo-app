# 第 05 關：add 錯了

> 對應投影片：後悔藥（git restore --staged）

## 情境

AI 加上了「已完成幾件」的統計，這個功能很好。但它順手把自己的工作筆記 `ai-notes.md` 也 add 進暫存區了，這份筆記不該放進專案。

## 開始

```bash
bash practice/start.sh 5
```

## 任務

把 `ai-notes.md` 從暫存區拿出來，只把 `app.js` 存進 commit。

## 步驟

1. 看看暫存區裡有什麼：

   ```bash
   git status
   ```

   綠色的檔案代表已經在暫存區。

2. 把 `ai-notes.md` 拿出來：

   ```bash
   git restore --staged ai-notes.md
   ```

3. 再看一次 `git status`，然後 commit：

   ```bash
   git commit -m "顯示已完成的數量"
   ```

4. 這份筆記用不到，直接刪掉：

   ```bash
   rm ai-notes.md
   ```

<details>
<summary>卡住了？看提示</summary>

- `git restore --staged` 只會把檔案移出暫存區，檔案本身還在資料夾裡，所以第 4 步要自己刪掉。
- 如果 AI 很常產生這類筆記，可以把檔名加進 `.gitignore`。

</details>

## 對 AI 說

> 「把 ai-notes.md 移出暫存區，只 commit app.js。」

## 檢查

```bash
bash practice/check.sh 5
```
