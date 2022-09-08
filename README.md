- main 函数的使用
```python
def main():
    # Todo: Add your code here
    pass


if __name__ == '__main__':
    main()
```
> 如果我们导入`(import)`的模块除了定义函数之外还有可以执行代码，那么Python解释器在导入这个模块时就会执行这些代码，因此如果我们在模块中编写了执行代码，最好是将这些执行代码放入如下所示的条件中，这样的话除非直接运行该模块，if条件下的这些代码是不会执行的，因为只有直接执行的模块的名字才是"__main__"。

- yield 生成 Fibonacci 数列
```py
def fib(n):
    a, b = 0, 1
    for _ in range(n):
        a, b = b, a + b
        yield a
```
