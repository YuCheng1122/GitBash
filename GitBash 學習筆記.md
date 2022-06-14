# GitBash 學習筆記

### 如何安裝GitBash

https://git-scm.com/download/win

![git(3)](https://github.com/YuCheng1122/GitBash/blob/master/src/git(3).png)

### Git 有哪些用途

- 版本控制系統

- 遊戲存檔功能

- 共同開發

### 什麼是GitHub?
- 遠端hosting，讓大家方便使用(可以自己host)
- 跟google drive很像
### 常用指令
1. git add
2. git commit 
3. git push
4. git remote
5. git status

## 如何將檔案上傳到GitHub
### git init 
將新建的資料夾初始化

![git(4)](https://github.com/YuCheng1122/GitBash/blob/master/src/git(4).png)

### git status 查詢狀態

透過這個指令查詢資料夾目前的狀態

![git(5)](https://github.com/YuCheng1122/GitBash/blob/master/src/git(5).png)
### git add 

可以用git add . 加入全部的檔案

```git
git add .
```



![git(6)](https://github.com/YuCheng1122/GitBash/blob/master/src/git(6).png)

### git commit

將加入的資料做儲存，同時為這一次的存檔命名

![Screenshot 2022-06-14 175414](https://github.com/YuCheng1122/GitBash/blob/master/src/Screenshot%202022-06-14%20175414.png)

### git log

存檔後我們可以透過git log這個語法去查詢我們幾次的存檔狀態

![git(7)](https://github.com/YuCheng1122/GitBash/blob/master/src/git(7).png)

### 創建origin

``` git
git remote add origin URL
```

### 上傳我們的檔案

```git
git push -u origin master
```

![git(10)](https://github.com/YuCheng1122/GitBash/blob/master/src/git(10).png)

## 參考資料

https://git-scm.com/downloads

https://youtu.be/B-SZqdlU59g

https://www.youtube.com/watch?v=Zd5jSDRjWfA&t=728s
