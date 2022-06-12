# YARIX-學習紀錄1

### 什麼是YARA rules?

YARA rules 是透過原文或二進制模式創建惡意軟件家族的描述，作為分類及識別惡意軟件使用。

### 使用YARA rules的方法

YARA rules 其實很像程式語言，運作方式是透過已找到的惡意軟體樣本來定義變數數量，根據規則會去找到與定義相同的惡意軟件，並成功識別惡意軟件。分析惡意軟件時，研究員會透過識別惡意軟件內特殊的模式或字串作為辨識惡意軟件家族與璩體的依據，當這些樣本互相有關聯時，就可以很好的將惡意軟件區分出來。

### YARA 包含以下元件

- Metadata
- Strings 
- Conditions
- Imports

## 如何安裝Yarix

Yarix的GitHub網址:

https://github.com/Yara-Rules/rules

### 安裝指令

```javascript
apt-get install cmake curl flex bison g++ gcc make python3 python3-dev python3-venv zlib1g zlib1g-dev wget
python3 -m venv YarIx
source YarIx/bin/activate
python3 -m pip install pip==21.0.1
make -C src/
pip install -r requirements.txt
```

![資安(1)](C:\Users\Tommy\Pictures\Screenshots\資安(1).png)

建立 binary的索引

```javascript
mkdir idx1
./buildindex -r samples1.txt -w idx1
```

### 如何蒐集惡意軟件?

https://resources.infosecinstitute.com/topic/top-7-malware-sample-databases-and-datasets-for-research-and-training/

### 透過VirusShare獲得惡意軟件

![Screenshot (87)](C:\Users\Tommy\Pictures\Screenshots\Screenshot (87).png)

![Screenshot (88)](C:\Users\Tommy\Pictures\Screenshots\Screenshot (88).png)

### 學習來源

https://ithelp.ithome.com.tw/articles/10209898

https://www.varonis.com/blog/yara-rules

https://amingosec.blog/yara-%E6%98%AF%E4%BB%80%E9%BA%BC%EF%BC%9F/
