## 权重优先级
!important（无穷）> 
行内样式 style=“”（1,0,0,0）>
id选择器(0,1,0,0)>
类选择器，伪类选择器(0,0,1,0)>
标签选择器(0,0,0,1)>
继承(0,0,0,0)

## 覆盖原则
权重相同的样式，写在后面的样式可以覆盖写在前面的

## 复合选择器
复合选择器有权重叠加，但是不会进位
例子：
```
ul li{
    color:yello;
}
```
0,0,0,1+0,0,0,1