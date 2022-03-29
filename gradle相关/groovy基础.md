## 字符串
字符串不分单引号和双引号
```
// << doLast 意思
task printlnString<<{
  def str1 = "双引号"
  def str2 = '单引号'
  println '引用字符串:'+str1
  println '引用字符串2:'+str2
}
```

## 方法
### 括号可省略
```
def method(int a,int b){
  printlng a+b
}
```

### return是可以不写的
return语句不是必需的。当没有return的时候，Groovy会把方法执行过程中的最后一句代码作为其返回值.