# 自行組合安全、好記且每個網站相異的密碼

資訊應用和我們的結合愈來愈緊密，保護隱私和機敏資料的最後一道防線ーー密碼，顯得更為重要。

我們知道密碼不應過於簡單、容易猜測：不該用生日、電話、常見的單字、人名等等。安全的做法是用密碼產生器產生隨機不同大小寫的字母、數字、符號組合。此外，網站被駭客入侵時有所聞，為了避免因為一個網站的密碼外洩而影響到所有的密碼，應該讓每個網站採用不同的密碼。密碼產生器產生的密碼極其複雜，於是有人發明了密碼管理軟體，來幫忙記住各組密碼。但是一旦我們把所有的密碼都放進同一套軟體，不就又將雞蛋丟進同一個籠子裡了嗎？

一個不同的密碼產生方法：token + pattern。

## 優點

1. 不必將雞蛋放進同一個籠子
2. 容易記憶
3. 每一個網站都不同
4. 較生日、電話等容易猜測的密碼安全
5. 快速方便地輸入密碼，不須透過額外軟體

## 缺點

1. 複雜度較密碼產生器產生的密碼低
2. 有被全盤破解的風險

## 說明

Token 是一串自訂的密碼，例如 TAIPEI 的變形 T@iP31。
Pattern 是一種能套用到不同網站的規則。例如取網站名稱的尾 2 字和頭 2 字：產生的密碼要給 Google 使用就是 lego；給 Yahoo 就是 ooya。

如此一來在 Google 的密碼就會是 T@iP31lego，在 Yahoo 的密碼是 T@iP31ooya。只要記 token 和 pattern 的規則即可，非常容易記憶。Pattern 的制定可以更加複雜，像是加上「[凱撒密碼](http://zh.wikipedia.org/zh-tw/%E5%87%B1%E6%92%92%E5%AF%86%E7%A2%BC)」來混淆。整體的組合也能再加以變化，像是改成 token 1 + pattern 1 + token 2 + pattern 2。

## 相關文章

* [Create a Different, Secure, Easy-to-Remember Password for Every Site](http://www.pcworld.com/article/252024/create_a_different_secure_easy_to_remember_password_for_every_site.html)