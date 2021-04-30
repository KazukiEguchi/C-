# アルゴリズム

ここからvはvectorでfは関数、predは引数が一つで返り値がbool値の関数

## for_each

イテレーターを先頭から末尾まで回し、要素ごとに関数を呼び出す

```cpp
	std::for_each(begin,end,f)
```

## all_of/any_of/none_of

all_of(any_of)はpred(*iter)が全て(1つでも)trueならtrueを返す  
none_ofは全てfalseならtrueを返す

```cpp
	std::all_of(begin,end,pred)
```

## find/find_if

条件に合うものを探し、そのイテレーターを返す、なかったらendが返る

```cpp
	std::find(begin,end,value)
	std::find_if(begin,end,pred)
```

## count/count_if

条件に合うものの数を返す

```cpp
	std::count(begin,end,value)
	std::count_if(begin,end,value)
```

## equal

二つのイテレーターが等しかったらtrueを返す  
引数に関数を取ることができ、単に==じゃない比較ができる。(小数点以下切り捨てで比較とか)

```cpp
	std::equal(begin1,end1,begin2,end2)
	std::equal(begin1,end1,begin2,end2,pred)
```

## search

後半のイテレーターの並びが前半のイテレーターに存在するか。存在したらtrueを返す。

```cpp
	std::search(begin1,end1,begin2,end2)
```

## copy

イテレーター[begin,end)の値をイテレーターresultに書き込んでいく。
戻り値は要素数だけ進めたイテレーターresultだ。

```cpp
	std::copy(begin,end,result)
```

## transform

copyに似ている。がresultへの書き込みが関数を通す。\*result = op(\*iter)  
opは引数が一つで値を返す関数

```cpp
	std::transform(begin,end,result,op)
```

## replace

old_valueがあれば、new_valueに変える。

```cpp
	std::replace(begin,end,old_value,new_value)
```

## fill/fill_n

[begin,end)の範囲にvalueを代入。fill_nは範囲が[begin,begin+n)になる。

```cpp
	std::fill(begin,end,value)
	std::fill_n(begin,n,value)
```

## generate/generate_n

fillと似ている。valueじゃなく関数genを使って代入。

```cpp
	std::generate(begin,end,gen)
	std::generate_n(begin,n,gen)
```

## remove/remove_if

条件にあった要素を後続の値で上書きする。新しい終端イテレーターを返す。  
上書きなので元のvectorの要素数は変わらない。

```cpp
	std::remove(begin,end,value)
	std::remove_if(begin,end,pred)
```