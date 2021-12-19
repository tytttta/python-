# 生成数据 

## 15-1 立方 :数字的三次方被称为其立方。请绘制一个图形，显示前5个整数的立方值，再绘制一个图形，显示前5000个整数的立方值。
````
import matplotlib.pyplot as plt

x_value = range(5)
y_value = [x*x*x for x in x_value]


plt.scatter(x_value, y_value)

plt.show()

x_value2 = range(5000)
y_value2 = [x*x*x for x in x_value2]
plt.scatter(x_value2, y_value2)
plt.show()
````

## 15-2 彩色立方 :给你前面绘制的立方图指定颜色映射。
````
import matplotlib.pyplot as plt

x_value = list(range(5000))
y_value = [x**3 for x in x_value]
plt.scatter(x_value, y_value, c=y_value,cmap=plt.cm.Reds ,edgecolor='none',s=40)

plt.title(" x*x*x")
plt.xlabel("x_value")
plt.ylabel('y_value')

plt.axis([0, 5000, 0, 200000000000])
plt.show()
````


