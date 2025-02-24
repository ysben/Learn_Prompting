---
sidebar_position: 600
---

# 🟢 電子郵件的 Zapier

import Basic from '@site/docs/assets/basic_applications/Zapiermail/Basic.webp';
import Diagram from '@site/docs/assets/basic_applications/Zapiermail/Diagram.webp';
import Step1 from '@site/docs/assets/basic_applications/Zapiermail/Step1.webp';
import Step2 from '@site/docs/assets/basic_applications/Zapiermail/Step2.webp';
import Step3 from '@site/docs/assets/basic_applications/Zapiermail/Step3.webp';
import Step4 from '@site/docs/assets/basic_applications/Zapiermail/Step4.webp';
import Zap from '@site/docs/assets/basic_applications/Zapiermail/Zap.webp';

## 介紹

我們已經看到 GPT-3 在電子郵件方面的用處。當您將它與 [Zapier](https://zapier.com) 或 [Bubble.io](https://bubble.io) 等 **無程式碼** 工具結合使用時，效果會更好。

本文將包含一個範倒，用以說明 Zapier+GPT-3 僅需少量設定即可完成哪些工作。本文雖然著眼於一個特定的範倒，但其想象空間是要大得多的。請記住，您也可以在 Bubble.io 中執行此操作。還有許多其他無程式碼工具，但在撰寫本文時還只有極少數允許您使用 GPT-3。

在本文中，我們將向您展示如何在 Zapier 中設定一個簡單的系統，在其中**彙總和儲存電子郵件**。將要與某人會面了？快速檢視您與此人往來的電子郵件摘要。這些設定大約需要 20 分鐘。

:::caution
瞭解 Zapier 對本文很有幫助。如果不瞭解，可以檢視這篇 [文章](https://zapier.com/learn/)。
:::


## 總體思路


下面是我們將在 Zapier 中執行的操作的圖示。每當一封電子郵件進入您的收件箱時，它都會觸發 Zapier 以下的四個步驟（至少目前是這樣的）:

1. 收到電子郵件並觸發 Zapier
1. 格式化電子郵件的內容（例如刪除 HTML markdown） 
2. 傳送到 GPT-3 進行總結
3. 將輸出儲存在資料庫中

<div style={{textAlign: 'left'}}>
  <img src={Diagram} style={{width: "500px"}}/>
</div>

## 設定 Zapier

首先確保擁有 [Zapier 帳戶](https://zapier.com/sign-up)（您可以獲得一個免費帳戶）。設定它是比較簡單的。建立帳戶後，點選展開下面內容可以檢視我們需要建立的每個 Zapier 操作的完整描述。

<details>
  <summary>展開以獲取更多 Zapier 設定步驟的細節</summary>
  <div>
  這就是 Zapier 步驟圖的樣子。
    <div><div style={{textAlign: 'left'}}>
  <LazyLoadImage src={Zap} style={{width: "500px"}} />
</div></div>
    <br/>
    <details>
      <summary>
        步驟 1: 收到電子郵件並觸發 Zapier
      </summary>
      <div>
        <div style={{textAlign: 'left'}}>
    <LazyLoadImage src={Step1} style={{width: "500px"}} />
        </div>
      </div>
    </details>
    <details>
      <summary>
       步驟 2: 格式化電子郵件的內容 
      </summary>
      <div>
        <div style={{textAlign: 'left'}}>
  <LazyLoadImage src={Step2} style={{width: "500px"}} />
</div>
      </div>
    </details>
    <details>
      <summary>
        步驟 3: 和提示詞一起傳送到 GPT-3
        <br/>
      </summary>
      <div>
        <div style={{textAlign: 'left'}}>
  <LazyLoadImage src={Step3} style={{width: "500px"}} />
</div>
      </div>
    </details>
    <details>
      <summary>
        步驟 4: 新增到資料庫中
      </summary>
      <div>
        <div style={{textAlign: 'left'}}>
  <LazyLoadImage src={Step4} style={{width: "500px"}} />
</div>
      </div>
    </details>
  </div>
</details>
這是 zapier 中的一個設定，它允許您進行非常基本的總結，如圖所示。它有它的侷限性，但它確實可以完成任務並且建立一個有用的資料庫。


## 最佳化提示以獲得更好的結果

有幾種簡單的方法可以改善您的結果，像新增上下文和角色提示都可以改進輸出。但是，您電子郵件的主題和內容可能涵蓋廣泛的範圍。這意味著寬泛的說明會比非常具體的說明帶來的效果更好。

出於實際原因，可以透過簡單地新增“Email：”並以““Summary”：”結束的提示來告訴 GPT-3 的回答格式。這避免了 GPT-3 回答“當然！我可以為你總結一下......”這樣的內容。

角色提示在這裡也很有用。讓 GPT-3 充當私人助理有助於提高摘要的質量。
如果您想總結工作電子郵件，只需新增您所需要的角色的特質描述即可為 GPT-3 提供工作的上下文。就好像假定讀者具有一定程度的知識，這有助於過濾掉電子郵件中不相關的部分。
下面我們展示了一些辦公室管理者可能收到的電子郵件範倒。

您可以要求它以要點形式總結一封簡單的電子郵件，但是，這可能不是很符合您的預期，具體取決於這份摘要的用途。為了快速瀏覽電子郵件，您可能只希望它簡短明瞭。下面是此提示的範倒，可以調整它並嘗試一下，看看結果是如何變化的。

<iframe
    src="https://embed.learnprompting.org/embed?config=eyJ0b3BQIjoxLCJ0ZW1wZXJhdHVyZSI6MC43LCJtYXhUb2tlbnMiOjI1Niwib3V0cHV0IjoiUmVxdWVzdCBmb3IgYWRkaXRpb25hbCBvZmZpY2Ugc3VwcGxpZXMgZHVlIHRvIGhpZ2ggd29ya2xvYWQuIExpc3Qgb2YgcmVxdWVzdGVkIGl0ZW1zOiBwcmludGVyIHBhcGVyLCBpbmsgY2FydHJpZGdlcyBmb3IgSFAgcHJpbnRlciBpbiBjb25mZXJlbmNlIHJvb20sIHN0aWNreSBub3RlcywgYmluZGVyIGNsaXBzLCBhbmQgaGlnaGxpZ2h0ZXJzLiBSZXF1ZXN0aW5nIGRlbGl2ZXJ5IGluZm9ybWF0aW9uIGFuZCBpZiB0aGVyZSBhcmUgYW55IHF1ZXN0aW9ucyBvciBjb25jZXJucy4iLCJwcm9tcHQiOiJBY3QgYXMgbXkgcGVyc29uYWwgYXNzaXN0YW50LiBJIGFtIGFuIG9mZmljZSBhZG1pbmlzdHJhdG9yLiBTdW1tYXJpemUgdGhlIGZvbGxvd2luZyBlbWFpbCBhcyBjb25jaXNlbHkgYXMgeW91IGNhbiwgaWdub3JlIHRoZSBmb290ZXIgYW5kIGhlYWRlciBhbmQgYW55IHByZXZpb3VzIGVtYWlscy4gXG5cbkVtYWlsOiBSZXF1ZXN0IGZvciBBZGRpdGlvbmFsIE9mZmljZSBTdXBwbGllcyBEZWFyIE9mZmljZSBBZG1pbmlzdHJhdG9yLCBJIGhvcGUgdGhpcyBlbWFpbCBmaW5kcyB5b3Ugd2VsbC4gSSBhbSB3cml0aW5nIHRvIHJlcXVlc3QgYWRkaXRpb25hbCBvZmZpY2Ugc3VwcGxpZXMgZm9yIG91ciB0ZWFtLiBBcyB5b3Uga25vdywgd2UgaGF2ZSBiZWVuIGV4cGVyaWVuY2luZyBhIGhpZ2ggdm9sdW1lIG9mIHdvcmsgbGF0ZWx5IGFuZCBoYXZlIGJlZW4gdXNpbmcgb3VyIHN1cHBsaWVzIGF0IGEgZmFzdGVyIHJhdGUgdGhhbiB1c3VhbC4gV2Ugd291bGQgZ3JlYXRseSBhcHByZWNpYXRlIGl0IGlmIHlvdSBjb3VsZCBwcm92aWRlIHVzIHdpdGggdGhlIGZvbGxvd2luZyBpdGVtczogUHJpbnRlciBwYXBlciBJbmsgY2FydHJpZGdlcyBmb3IgdGhlIEhQIHByaW50ZXIgaW4gdGhlIGNvbmZlcmVuY2Ugcm9vbSBTdGlja3kgbm90ZXMgQmluZGVyIGNsaXBzIEhpZ2hsaWdodGVycyBQbGVhc2UgbGV0IG1lIGtub3cgaWYgdGhlcmUgYXJlIGFueSBxdWVzdGlvbnMgb3IgY29uY2VybnMsIGFuZCB3aGVuIHdlIGNhbiBleHBlY3QgdGhlIHN1cHBsaWVzIHRvIGJlIGRlbGl2ZXJlZC4gVGhhbmsgeW91IGZvciB5b3VyIGhlbHAuIFxuXG5CZXN0IHJlZ2FyZHMsIFlvdXIgTmFtZSBTdW1tYXJ5OlxuIiwibW9kZWwiOiJ0ZXh0LWRhdmluY2ktMDAzIn0%3D"
    style={{width:"100%", height:"500px", border:"0", borderRadius:"4px", overflow:"hidden"}}
    sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
></iframe>

此處的回覆看得出來是有效的。但是，透過進一步微調，您可以獲得更好的結果。作為摘要的讀者，您不關心它是一封電子郵件，您可能希望摘要的細節程度較低。關於為什麼的資訊是無關緊要的，有些問題和疑慮也是如此。透過簡單地描述摘要的目標可以快速刪除不需要的內容，進而改善結果。

<iframe
    src="https://embed.learnprompting.org/embed?config=eyJ0b3BQIjowLCJ0ZW1wZXJhdHVyZSI6MCwibWF4VG9rZW5zIjoyNTYsIm91dHB1dCI6IlJlcXVlc3QgZm9yIGFkZGl0aW9uYWwgb2ZmaWNlIHN1cHBsaWVzIC0gcHJpbnRlciBwYXBlciwgaW5rIGNhcnRyaWRnZXMgZm9yIEhQIHByaW50ZXIsIHN0aWNreSBub3RlcywgYmluZGVyIGNsaXBzIGFuZCBoaWdobGlnaHRlcnMuIiwicHJvbXB0IjoiQWN0IGFzIG15IHBlcnNvbmFsIGFzc2lzdGFudC4gSSBhbSBhbiBvZmZpY2UgYWRtaW5pc3RyYXRvci4gU3VtbWFyaXplIHRoZSBmb2xsb3dpbmcgZW1haWwgYXMgY29uY2lzZWx5IGFzIHlvdSBjYW4sIGlnbm9yZSB0aGUgZm9vdGVyIGFuZCBoZWFkZXIgYW5kIGFueSBwcmV2aW91cyBlbWFpbHMuIEkgd2FudCB0byB1c2UgdGhlIHN1bW1hcnkgdG8gc2tpbSBlbWFpbHMuIFJlbW92ZSBhbnkgcGxlYXNhbnRyaWVzLiBcblxuRW1haWw6IFJlcXVlc3QgZm9yIEFkZGl0aW9uYWwgT2ZmaWNlIFN1cHBsaWVzIERlYXIgT2ZmaWNlIEFkbWluaXN0cmF0b3IsIEkgaG9wZSB0aGlzIGVtYWlsIGZpbmRzIHlvdSB3ZWxsLiBJIGFtIHdyaXRpbmcgdG8gcmVxdWVzdCBhZGRpdGlvbmFsIG9mZmljZSBzdXBwbGllcyBmb3Igb3VyIHRlYW0uIEFzIHlvdSBrbm93LCB3ZSBoYXZlIGJlZW4gZXhwZXJpZW5jaW5nIGEgaGlnaCB2b2x1bWUgb2Ygd29yayBsYXRlbHkgYW5kIGhhdmUgYmVlbiB1c2luZyBvdXIgc3VwcGxpZXMgYXQgYSBmYXN0ZXIgcmF0ZSB0aGFuIHVzdWFsLiBXZSB3b3VsZCBncmVhdGx5IGFwcHJlY2lhdGUgaXQgaWYgeW91IGNvdWxkIHByb3ZpZGUgdXMgd2l0aCB0aGUgZm9sbG93aW5nIGl0ZW1zOiBQcmludGVyIHBhcGVyIEluayBjYXJ0cmlkZ2VzIGZvciB0aGUgSFAgcHJpbnRlciBpbiB0aGUgY29uZmVyZW5jZSByb29tIFN0aWNreSBub3RlcyBCaW5kZXIgY2xpcHMgSGlnaGxpZ2h0ZXJzIFBsZWFzZSBsZXQgbWUga25vdyBpZiB0aGVyZSBhcmUgYW55IHF1ZXN0aW9ucyBvciBjb25jZXJucywgYW5kIHdoZW4gd2UgY2FuIGV4cGVjdCB0aGUgc3VwcGxpZXMgdG8gYmUgZGVsaXZlcmVkLiBUaGFuayB5b3UgZm9yIHlvdXIgaGVscC4gXG5cbkJlc3QgcmVnYXJkcywgWW91ciBOYW1lIFN1bW1hcnk6XG4iLCJtb2RlbCI6InRleHQtZGF2aW5jaS0wMDMifQ%3D%3D"
    style={{width:"100%", height:"500px", border:"0", borderRadius:"4px", overflow:"hidden"}}
    sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
></iframe>


<br/>


## 其他用例

現在您已經看到了如何進行摘要的範倒，我們將提及 Zapier+GPT-3 的其他一些用例。一個很好的例子是讓 GPT-3 對您的電子郵件進行分類。這隻需要在提示中告訴它將以下電子郵件分類為您喜歡的任何類別。

一個更深入的例子是使用多個提示。您可以使用提示來生成同意電子郵件要求的響應以及不同意的響應。這些都可以儲存在您的草稿中，等待隨時傳送。

如果您經常收到非常相似的電子郵件，您可以使用 Zapier 中的過濾器來僅對該型別電子郵件應用提示。與格式化程式結合使用時，這可能是一個強大的工具。您可以從中提取資訊並匯出 CSV，或者直接將它們儲存在某種形式的資料庫中。


## 顧慮

透過 GPT-3 執行電子郵件並存儲它們時，請務必牢記隱私問題。 GPT-3 有時會出錯。我們強烈建議在傳送前檢查電子郵件內容。

By [gezilinll](https://github.com/gezilinll).