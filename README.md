# ugractf-powerful  
  
Задание:  

![image](https://user-images.githubusercontent.com/73061822/109431632-8f7bef80-7a18-11eb-9fc5-9b105683297b.png)

В powerful.key лежит что-то в base64  
Разбейзим:  

![image](https://user-images.githubusercontent.com/73061822/109431735-0e712800-7a19-11eb-88b4-8508966c030f.png)

Привлекает эта строка:  
```python

x = ((a ** b) ** (c ** d)) % n
    c1 = chr((x % n) % 256)
    c2 = chr((x % n) // 256 % 256)
    c3 = chr((x % n) // 65536)

```

Получается, что мы можем улучшить алгоритм - перед каждым возведением в степень брать остаток a от n.  
Однако этого недостаточно, ведь надо избавиться от (c ** d)  
С этим нам помогает теорема Эйлера (https://ru.wikipedia.org/wiki/Теорема_Эйлера_(теория_чисел))
    
