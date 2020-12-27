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
