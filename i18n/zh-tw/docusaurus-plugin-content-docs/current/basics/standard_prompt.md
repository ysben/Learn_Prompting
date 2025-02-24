---
sidebar_position: 3
---

# 🟢 “標準”提示

到目前為止，我們已經說過幾種不同格式的提示。根據Kojima等人的說法(@kojima2022large)，我們將僅包含一個問題的提示稱為“標準”提示。我們還認為僅包含問答形式為問題的提示也是“標準”提示。

#### 我為什麼要在意？

我們引用的許多文章都使用這個術語。我們這麼定義它的目的，以便我們可以討論與標準提示不同的新型提示。

### 標準提示的兩個示例:


_標準提示_
```
法國的首都是哪裡？
```

_問答形式的標準提示_
```
問：法國的首都是哪裡？

答：
```

## Few Shot標準提示

Few shot標準提示(@liu2021pretrain)就是隻包含_示例_的標準提示。示例是提示要解決的任務的例子，這些示例包含在提示本身中(@brown2020language)。在研究中，Few shot標準提示有時簡稱為標準提示（儘管我們嘗試在本指南中不這樣稱呼）。

### Few Shot標準提示的兩個示例：

_Few Shot標準提示_

```
西班牙的首都是哪裡？
馬德里
義大利的首都是哪裡？
羅馬
法國的首都是哪裡？
```

_問答形式的Few Shot標準提示_
```
問：西班牙的首都是哪裡？
答：馬德里
問：義大利的首都是哪裡？
答：羅馬
問：法國的首都是哪裡？
答：
```

Few shot提示有助於“few shot”或稱為“上下文中”的學習，即在不更新引數的情況下進行學習(@zhao2021calibrate)

