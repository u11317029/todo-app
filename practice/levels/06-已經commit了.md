# 第 06 關：已經 commit 了

> 對應投影片：已經 commit 了：revert 還是 reset？

## 情境

AI 說它重構了刪除功能，而且已經幫你 commit 好了。結果你刪掉一個待辦事項，其他的卻全部不見了。

## 開始

```bash
bash practice/start.sh 6
```

## 任務

用 `git revert` 撤銷這個壞掉的 commit，而且要**保留歷史紀錄**。

## 步驟

1. 在網頁上新增三個待辦事項，再刪掉其中一個，看看發生什麼事。
2. 找出是哪個 commit：

   ```bash
   git log --oneline
   ```

   注意作者：`git log` 的完整模式會顯示這個 commit 是「AI 助手」做的。

3. 打開那個 commit 看看改了什麼：

   ```bash
   git show HEAD
   ```

4. 撤銷它：

   ```bash
   git revert HEAD --no-edit
   ```

5. 再看一次 `git log --oneline`：壞掉的 commit 還在，後面多了一個 `Revert` commit 把它抵銷。

<details>
<summary>卡住了？看提示</summary>

- 加上 `--no-edit` 是為了不打開文字編輯器。如果忘了加，畫面跳進看不懂的編輯器：
  - 畫面最下方有很多 `~` 符號：這是 Vim，輸入 `:wq` 再按 Enter 離開。
  - 畫面最下方有 `^X Exit`：這是 nano，按 `Ctrl + X` 離開。
- 這一關不要用 `git reset`。它會讓壞掉的 commit 從歷史消失，如果已經推上 GitHub，會影響其他人。

</details>

## 對 AI 說

> 「用 revert 撤銷最新的那個 commit，不要改寫歷史。」

## 檢查

```bash
bash practice/check.sh 6
```
