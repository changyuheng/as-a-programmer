# Fcitx - Input Method Framework

Fcitx 是一個自訂性很高的輸入法框架。

## Install Fcitx

```bash
sudo apt-get install fcitx
```

## Install Boshiamy input method

```bash
sudo apt-get install fcitx-table-boshiamy
```

### Configuration of Boshiamy

* `Activities` → `Input Method` 選擇 fcitx。重新登入。

* `Activities` → `Fcitx Configuration` → `Input Method` → `Boshiamy` → 雙擊 (如果沒看到 Boshiamy 就自行新增這個表格)
    `Other` → `Table` → `table/boshiamy.conf` → 設定
    `Adjust Order`：`AdjustNo`
    `Auto Send Candidate Word`：取消
    `Use Maching Key`：取消
    `Choose`：0123456789
    `Ignore Punctuation`：打勾

## Refs.

* [Ubuntu與嘸蝦米: 在fcitx下，(boshiamy)嘸蝦米的使用最為順暢、穩定!（新酷音、m17n、倉頡、輕鬆法亦適用）](http://www.ubuntu-tw.org/modules/newbb/viewtopic.php?post_id=246870)