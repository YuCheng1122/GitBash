# Git 學習筆記2

### 如何在同一台電腦中同時使用兩個GitHub帳號

因為有特殊的需求所以引起我想在同一台電腦中使用兩個GitHub帳號，但這個部分對我來說其實有一點挑戰，因為畢竟之前沒有用過Git，原本以為使用一般的方式應該就可以了，沒想到如果用一般的HTTPS的方式其實沒辦法同時在一台電腦中完成這件事，因此我就開始了這個的研究。

### 產生SSH

在這裡我是使用ed25519的而不是rsa但應該影響不大，因為我一開始在使用的時候以為是因為我用rsa導致無法上傳，所以才換成ed25519但事後看起來，其實應該是沒有任何影響，所以還是就先用rsa吧!

```git
$ssh-keygen -t rsa -C "userName@address"
```

### 確認有沒有成功

可以從User的地方找到.ssh的資料夾或是輸入

```git
ls
```

### 將產生的key放到你的GitHub帳號

從setting的地方找到ssh的地方，並將你的.pub檔放進去

![Screenshot 2022-06-14 185334](https://github.com/YuCheng1122/GitBash/blob/master/src/Screenshot%202022-06-14%20185334.png)

![git(11)](https://github.com/YuCheng1122/GitBash/blob/master/src/git(11).png)

### 產生出的檔案中.pub是公鑰，另一個則為對應的私鑰。

![git(12)](https://github.com/YuCheng1122/GitBash/blob/master/src/git(12).png)

### 設定SSH

現在要來建立一個config檔案

```git
touch config
```

設定裡面的內容

```git
vim config
```

按i左下角會有一個insert就可以做修改了

```git
# 預設帳號 （個人帳號） 
Host personal
     HostName github.com
     User git
     IdentityFile ~/.ssh/id_rsa_personal
# 工作帳號
Host work
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_rsa_work
# 其他帳號 ...
```

需要改的是 Host 還有 IdentityFile，名字都可以自己取。

### 設定git remote

@後面的部分就是你設定的Host

```git
git remote add origin git@personal:你的github帳號/你的github資料夾.git
```

如果你已經有設定過 remote了，那就會出現remote已經存在，以下可以為你的config做修改。

```git
cd .git
vim config
```

```git
[remote "github"]
         url = git@personal:你的github帳號/你的github資料夾.git
         fetch = +refs/heads/*:refs/remotes/github/*
```

依照你的帳號做修改。

### 進入config會用到什麼

```git
e 修改
i 加東西
esc 跳出
:q!離開不儲存
:wq 離開儲存變更
```

## 參考資料

https://medium.com/cyen6/%E5%A6%82%E4%BD%95%E4%B8%80%E5%8F%B0%E9%9B%BB%E8%85%A6%E4%BD%BF%E7%94%A8%E5%A4%9A%E5%80%8B-git-%E5%B8%B3%E8%99%9F-144d9582ff09

https://medium.com/@hyWang/%E5%A6%82%E4%BD%95%E5%9C%A8%E4%B8%80%E5%8F%B0%E9%9B%BB%E8%85%A6%E4%BD%BF%E7%94%A8%E5%A4%9A%E5%80%8Bgit%E5%B8%B3%E8%99%9F-907c8eadbabf

https://www.youtube.com/watch?v=vSeYsk4WYvg&t=3s

https://www.youtube.com/watch?v=N6YQlPuAamw&t=368s
