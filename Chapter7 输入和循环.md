# Chapter7 输入和循环

## 7-1 汽车租赁 ： 编写一个程序， 询问用户要租赁什么样的汽车， 并打印一条消息， 如“Let me see if I can find you a Subaru”。
````
car =input('What car do you want: ')
print('Let me see if I can find you a %s' %car)
````

## 7-2 餐馆订位 ： 编写一个程序， 询问用户有多少人用餐。 如果超过8人， 就打印一条消息， 指出没有空桌； 否则指出有空桌。
````
num = input('how many person will come to have dinner: ')
num = int(num)
if num >8:
    print('There is no such big table')
else:
    print('There is such table')
````

## 7-3 10的整数倍 ： 让用户输入一个数字， 并指出这个数字是否是10的整数倍。
````
num = input('input a num: ')
num = int(num)
if num % 10 ==0:
    print('This num divide 10 is 0')
else:
    print('This num divide 10 is not 0')
````

## 7-4 比萨配料 ： 编写一个循环， 提示用户输入一系列的比萨配料， 并在用户输入'quit' 时结束循环。 每当用户输入一种配料后， 都打印一条消息， 说我们会在比萨中添加这种配料。
````
msg = "input a food, and it will end when input 'quit':\n"
inputTxt = input(msg)
while inputTxt!='quit':
    print('The %s will be add to pizza' %inputTxt)
    inputTxt=input(msg)
````

## 7-5 电影票 ： 有家电影院根据观众的年龄收取不同的票价： 不到3岁的观众免费； 3~12岁的观众为10美元； 超过12岁的观众为15美元。 请编写一个循环， 在其中询问用户的年龄， 并指出其票价。
````
age = input('input the age:\n')
age = int(age)
while age> 0:
    if(age<3):
        print('free')
    elif(age<12):
        print('price is $10')
    else:
        print('price is $15')
    age = input('input the age:\n')
    age = int(age)
    
````
## 7-6 三个出口 ： 以另一种方式完成练习7-4或练习7-5， 在程序中采取如下所有做法。
* 在while 循环中使用条件测试来结束循环。
* 使用变量active 来控制循环结束的时机。
- 使用break 语句在用户输入'quit' 时退出循环。
````
````
7-7 无限循环 ： 编写一个没完没了的循环， 并运行它（要结束该循环， 可按Ctrl +C， 也可关闭显示输出的窗口） 。
