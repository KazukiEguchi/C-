# vectorのループの仕方

## std::sizeを用いて

要素数をsizeで持ってきて回す

```
std::vector<int> v = {1,2,3};
for(int i = 0;i != std::size(v);i++){
  std::cout << v[i];
}
```

## イテレーターを使って
```
for(auto iter = std::begin(v);iter != std::end(v);++iter){
  std::cout << *iter << std::endl;
}
```
  
