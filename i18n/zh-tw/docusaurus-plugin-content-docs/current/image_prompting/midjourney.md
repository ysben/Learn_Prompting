---
sidebar_position: 99
---
# 🟢 Midjourney

[Midjourney](https://www.midjourney.com) 是另一個 AI 影象生成器。與 Stable Diffusion 不同，Midjourney 使用 Discord Bot 作為 AI 影象生成的介面（[在此](https://discord.gg/midjourney)加入 Discord，或在 [Learn Prompting Discord](https://learnprompting.org/discord) 中嘗試該 Bot）。不過，使用 Midjourney Bot 的遵循相同的影象提示基本原則。

import midjourney_astronaut from '@site/docs/assets/images_chapter/midjourney_astronaut.webp';
import midjourney_astronaut_params from '@site/docs/assets/images_chapter/midjourney_astronaut_params.webp';
import midjourney_astronaut_multi1 from '@site/docs/assets/images_chapter/midjourney_astronaut_multi1.webp';
import midjourney_astronaut_multi2 from '@site/docs/assets/images_chapter/midjourney_astronaut_multi2.webp';
import midjourney_astronaut_ip2 from '@site/docs/assets/images_chapter/midjourney_astronaut_ip2.webp';


# 基本用法

Midjourney 的基本結構是 `/imagine prompt: [IMAGE PROMPT] [--OPTIONAL PARAMETERS]`. 例如:

```text
/imagine prompt: astronaut on a horse
```

<div style={{textAlign: 'center'}}>
  <img src={midjourney_astronaut} style={{width: "750px"}}/>
</div>

更多關於影象提示引數的資訊可以在這裡找到：[Midjourney Documentation - Parameter List](https://docs.midjourney.com/docs/parameter-list)

例如:

```text
/imagine prompt: astronaut on a horse --ar 3:2 --c 70 --q 2 --seed 1000 
```

<div style={{textAlign: 'center'}}>
  <LazyLoadImage src={midjourney_astronaut_params} style={{width: "750px"}} />
</div>

# 進階用法
## 多重提示
Midjourney 預設情況下會整體理解你的提示語。使用雙冒號 :: 可以讓 Midjourney 分別理解提示語的每個部分。例如：
```text
/imagine prompt: astronaut and horse
```
<div style={{textAlign: 'center'}}>
  <LazyLoadImage src={midjourney_astronaut_multi1} style={{width: "750px"}} />
</div>

```text
/imagine prompt: astronaut:: and horse
```
<div style={{textAlign: 'center'}}>
  <LazyLoadImage src={midjourney_astronaut_multi2} style={{width: "750px"}} />
</div>


## 影象提示
透過將一個圖片上傳到 Discord，並在提示語中使用它的 URL，你可以指示 Midjourney 使用該圖片來影響你的結果的內容、樣式和構成。例如：
[Astronaut (Source: Wikipedia)](https://en.wikipedia.org/wiki/Astronaut#/media/File:STS41B-35-1613_-_Bruce_McCandless_II_during_EVA_(Retouched).webp)

```text
/imagine prompt: [image URL], impressionist painting
```
<div style={{textAlign: 'center'}}>
  <LazyLoadImage src={midjourney_astronaut_ip2} style={{width: "750px"}} />
</div>

## Notes

Needs more content!