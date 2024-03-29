# Markdown

## 見出し

先頭に `#` を記述する。

```
# 見出し１
## 見出し２
### 見出し３
#### 見出し４
##### 見出し５
###### 見出し６
```

# 見出し１
## 見出し２
### 見出し３
#### 見出し４
##### 見出し５
###### 見出し６

## 段落

空行列を挟む。

```
段落１
(空行)
段落２
```

段落１

段落２

## 改行

改行の前に半角スペース`  `を２つ記述する。

```
aaa
bbb(半角スペース２つ)
ccc
```

aaa
bbb  
ccc

## コード

バッククオート３つをコード全体に囲む。
開始を表すバッククオートの3つ目に続けて、任意で言語名を明記することができる。

```c
#include <stdio.h>

int main(){
    printf("%s\n", "Hello!");
    return 0;
}
```

インラインコードはバッククオート１つで囲む。「`some code`」

## 折りたたみ

detailsタグとsummaryタグを使用する。

<details>
<summary>折りたたみ</summary>

aaaaaaaaaaaaaaa

bbbbbbbbbbbbbbb

ccccccccccccccc
</details>

## 箇条書きリスト

ハイフン`-`、プラス`+`、アスタリスク`*`のいずれかを先頭に記述する。

- リスト１
  - リスト1-1
    - リスト1-1-1
    - リスト1-1-2
  - リスト1-2
- リスト２
- リスト３
