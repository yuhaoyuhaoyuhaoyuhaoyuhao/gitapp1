# git指令介紹
### git command study

- 檢查git版本
git --version

-檢查設定檔
git config --list

設定user.name & user.eamil
git config --global user.name "yourname"
git config --global user.eamil "youreamil"

cd 切換目錄
cd ..切換到上一個目錄
ls -al 檢視目錄全部

此資料夾被git控管 生成.git檔案
git init

檢視現在資料夾狀態
git status

新增檔案到暫存區 or被git控管
git add 檔名.副檔名
git add *.副檔名
全部一起新增到暫存區
git add --all 

commit將檔案放到本機儲存區
-m 是參數 留訊息
git commit -m "message"
只有被git控管的檔案才可以一次跳過暫存區
儲存到本機儲存區
git commit -am "message"
git commit -a -m "message"
=============================
#為什麼會兩次動作
1.類似倉庫管理
2.逐筆確認
3.codereview

甚麼時候commit
1.沒有一定
2.階段性功能完成一次
3.一天至少一次

文字編輯器：
:q 離開
:w 儲存
:wq q+w

把異動紀錄修改到最近一次commit
git commit --amend --no-edit

修改最近一次的commit訊息
git commit --amend -m "new message"
===============================
修改後的檔案在工作區還未加入暫存區，會強制回復到上次存檔的
紀錄，要小心使用！
git restore 檔名
參數:--staged  若修改後的檔案已經放到暫存區，回將檔案丟回工作區，並保留異動的狀態

將檔案設定成不被git控管
git rm --cached 檔名 (不常使用)

檢視工作區的異動
git diff
參數: 
--staged 檢視暫存區的異動
資訊碼 資訊碼 檢視兩個commit比較

檢視每一行程式碼的紀錄(更動內容、更動人員、更動時間)
git blame 檔名


移動你的commit版本到指定的版本，並回到工作區
git reset 資訊碼
git reset HEAD~ (~表示上一個)
git reset HEAD^ 
參數： 
--soft 回到暫存區
--hard 直接回到上一個版本的狀態(會異動程式請小心使用)

檢視歷史commit紀錄
git reflog

====================================
分支
檢視目前分支
git branch

創建分支(會複製目前所在分支的所有檔案，並且放入新創建的分支內)
git branch <new branch name>
-d 刪除

合併分支
git merge branch名稱

移動分支
git checkout 分支名
git switch 分支名

創建並移動分支
git checked -b <branch name>
git switch -c 資訊碼

修改分支名稱
-M 新名稱 改自己的名稱
-m 新名稱 改別的分支

==============================
設定遠端儲存區url
git remote add 別名 URL

參數：
-v 檢視路徑
