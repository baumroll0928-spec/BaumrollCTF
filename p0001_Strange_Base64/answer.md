# Strange Base64

## フラグ

baumroll{tartar_sauce_is_very_healthy}

## 解説

問題文で提示されたコード
```
yMf1BxjVBgX7DgfYDgfYx3nHDwnLx2LZx3zLCNLFAgvHBhrOEx0=
```
をCyberchefを使ってそのままBase64デコードすると、フラグ形式どころかASCII文字列にすらなりません。

そこで、逆にフラグの既知部分 baumroll{ をエンコードしてみます。すると、
```
YmF1bXJvbGx7
```
となり、提示されたコードと比較すると、アルファベットの大文字と小文字が入れ替わっていることがわかります。

よって、全ての大文字と小文字を入れ替えてからデコードしてみます。
```
yMf1BxjVBgX7DgfYDgfYx3nHDwnLx2LZx3zLCNLFAgvHBhrOEx0=
```
↓ Swap case
```
YmF1bXJvbGx7dGFydGFyX3NhdWNlX2lzX3ZlcnlfaGVhbHRoeX0=
```
↓ From Base64
```
baumroll{tartar_sauce_is_very_healthy}
```
無事フラグが得られました。
