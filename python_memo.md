# Pythonメモ
## フォーマット
  ### 金額用カンマフォーマット
```python
x = 900000
print(f"{x:,}")
```
結果:
```cmd
900,000
```
### 小数点フォーマット
```python
x = 900000
print(f"{x: .5f}")
```
結果:
```cmd
900000.00000
```
## 三項演算子
```python
age = input()

result = "成人" if age >= 20 else "子供"
```

## 可変長引数
### 引数をタプルとして扱う
```python
def func(*args):

    print(args)

func(1, 3, 5)
```
tuple型として扱われる
```cmd
(1, 3, 5)
```
### 引数を辞書型として扱う
```python
def func(**kwargs)

    print(kwargs)

func(name="Issei", age="22")
```
辞書型として扱われる
```cmd
{"name": "Issei", "age": "22"}
```
### 普通の引数を持つ場合
```python
def func(x, *args):

    (処理)

func(x=1, 1, 2, 5)
```
## for文とwhile文のbreak, continue
### break: ループを抜ける

### continue: ループ内のこれ以下の処理を飛ばして次のループに入る


## ラムダ式
### map関数と使う
```python
names = ["鈴木", "加藤", "國政"]

list(map(lambda x: x + "さん", names))
```
### filter関数と使う
```python
num = [1, 2, 10, 12, 30]

list(filter(lambda x: x>= 10), num)
```
結果:
```cmd
[10, 12, 30]
```
### リスト内包表記と使う
```python
names = ["工藤", "有馬", "國政"]

# (lambda x: x + "さん")(x) → func(x) と考えるとわかりやすい
a = [(lambda x: x + "さん")(x) for x in names]
```
## データクラス
```python
@dataclass
class User:
    name: str
    age: int
    gender: str
```
### デフォルト値を設定するフィールドは設定しないフィールドの後に書く
```python
@dataclass
class User:
    name: str
    gender: str
    age: int = 22
```
ミュータブルオブジェクトの場合は特殊

ほかにも便利な機能がある

## セイウチ演算子(代入演算子)
```python
x = [1, 2, 3]

if (n:=len(x)) >= 10:

    print("listが長すぎます")

    print(n)
```

## デバッガー
### breakpoint()を挿入

p: print

n: 次の行

s: 関数の中に入る

c: 次のbreakpointへ進む

q: 終了する

## requirements.txt

pip freeze で出力される
