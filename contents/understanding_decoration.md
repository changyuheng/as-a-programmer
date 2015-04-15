Decorator 是一個 Python 中較為進階的語法，因為較難理解故常被提出來討論。這邊提供一個簡潔的說明。

假設有一名為 func 的 function 被名為 decor1 和 decor2 的二 decorator 修飾如下：

```python
@decor1
@decor2
def func(*args, **kwargs):
    pass
```

則當我們如下呼叫 func() 時：

```python
func(*args, **kwargs)
```

可以將之理解為：

```python
decor1(decor2(func))(*args, **kwargs)
```

更詳細的說明可以參考：

1. [Understanding Python Decorators in 12 Easy Steps!](http://simeonfranklin.com/blog/2012/jul/1/python-decorators-in-12-steps/)
2. [How can I make a chain of function decorators in Python?](http://stackoverflow.com/a/739679)