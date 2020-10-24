
# Chapte5 If语句

## 5-1 条件测试 ： 
- 编写一系列条件测试； 将每个测试以及你对其结果的预测和实际结果都打印出来。 
````
car = 'subaru'
print("Is car == 'subaru'? I predict True.")
print(car == 'subaru')
print("\nIs car == 'audi'? I predict False.")
print(car == 'audi')
print("\nIs 1 == 2? I predict False.")
print(1 == 2)
print("\nIs 2 == 2? I predict True.")
print(2 == 2)
````

## 5-2 更多的条件测试 ： 
- 你并非只能创建10个测试。 如果你想尝试做更多的比较， 可再编写一些测试， 并将它们加入到conditional_tests.py中。 对于下面列出的各种测试， 至少编写一个结果为True 和False 的测试。
- 检查两个字符串相等和不等。
- 使用函数lower() 的测试。
- 检查两个数字相等、 不等、 大于、 小于、 大于等于和小于等于。
- 使用关键字and 和or 的测试。
- 测试特定的值是否包含在列表中。
- 测试特定的值是否未包含在列表中
````
print("Is 'car' == 'car'? I predict True.")
print('car' == 'subaru')
print("\nIs 'car' == 'audi'? I predict False.")
print('car' == 'audi')
print("\nIs 'car' == ('CAR').lower()? I predict True.")
print('car' == ('CAR').lower())
print("\nIs 1 != 2? I predict True.")
print(1 != 2)
print("\nIs 2 == 2? I predict True.")
print(2 == 2)
print("2>=1 and 3>=2:" )
print(2>=1 and 3>=2)
print("2>=1 or 3>=4:" )
print(2>=1 or 3>=4)
list = [1,'abc',34]
print("1 in list")
print(1 in list)
print("'abc' in list")
print('abc' in list)
print("345 not in list")
print(345 not in list)
````

## 5-3 外星人颜色 :
- 假设在游戏中刚射杀了一个外星人，请创建一个名为alien_color 的变量，并将其设置为'green' 、'yellow' 或'red' 。 
- 编写一条if 语句，检查外星人是否是绿色的;如果是，就打印一条消息，指出玩家获得了5个点。 
- 编写这个程序的两个版本，在一个版本中上述测试通过了，而在另一个版本中未通过(未通过测试时没有输出)。
````
alien_color  = 'green'
if alien_color == 'green':
    print("you get five score")

alien_color = 'red'
if alien_color == 'green':
    print("you get five score")
````
## 5-4 外星人颜色 :
- 像练习5-3那样设置外星人的颜色，并编写一个if-else 结构。 
- 如果外星人是绿色的，就打印一条消息，指出玩家因射杀该外星人获得了5个点。 
- 如果外星人不是绿色的，就打印一条消息，指出玩家获得了10个点。 
- 编写这个程序的两个版本，在一个版本中执行if 代码块，而在另一个版本中执行else 代码块。
````
alien_color  = 'green'
if alien_color == 'green':
    print("you get five score")
else:
    print("you get ten score")

alien_color = 'red'
if alien_color == 'green':
    print("you get five score")
else:
    print("you get ten score")
````


## 5-5 外星人颜色 : 
- 将练习5-4中的if-else 结构改为if-elif-else 结构。 
- 如果外星人是绿色的，就打印一条消息，指出玩家获得了5个点。 
- 如果外星人是黄色的，就打印一条消息，指出玩家获得了10个点。 
- 如果外星人是红色的，就打印一条消息，指出玩家获得了15个点。 
- 编写这个程序的三个版本，它们分别在外星人为绿色、黄色和红色时打印一条消息。
````
alien_color  = 'green'
if alien_color == 'green':
    print("you get five score")
elif alien_color == 'yellow':
    print("you get ten score")
elif alien_color == 'red' :
    print("your get 15 score")

alien_color = 'red'
if alien_color == 'green':
    print("you get five score")
elif alien_color == 'yellow':
    print("you get ten score")
elif alien_color == 'red' :
    print("your get 15 score")

alien_color = 'yellow'
if alien_color == 'green':
    print("you get five score")
elif alien_color == 'yellow':
    print("you get ten score")
elif alien_color == 'red' :
    print("your get 15 score")
````

## 5-6 人生的不同阶段 :
- 设置变量age 的值，再编写一个if-elif-else 结构，根据age 的值判断处于人生的哪个阶段。 
- 如果一个人的年龄小于2岁，就打印一条消息，指出他是婴儿。
- 如果一个人的年龄为2(含)~4岁，就打印一条消息，指出他正蹒跚学步。 
- 如果一个人的年龄为4(含)~13岁，就打印一条消息，指出他是儿童。 
- 如果一个人的年龄为13(含)~20岁，就打印一条消息，指出他是青少年。 
- 如果一个人的年龄为20(含)~65岁，就打印一条消息，指出他是成年人。 
- 如果一个人的年龄超过65(含)岁，就打印一条消息，指出他是老年人。
````
age = 15 
if age<2:
    print("他是婴儿")
elif age < 4:
    print("他正蹒跚学步")
elif age < 13:  
    print("他是儿童")
elif age < 20:
    print("他是青少年")
elif age <65:
    print("他是成年人")
else:
    print("他是老年人")
````

## 5-7 喜欢的水果 :
- 创建一个列表，其中包含你喜欢的水果，再编写一系列独立的if 语句，检查列表中是否包含特定的水果。 
- 将该列表命名为favorite_fruits ，并在其中包含三种水果。
- 编写5条if 语句，每条都检查某种水果是否包含在列表中，如果包含在列表中，就打印一条消息，如“You really like bananas!”。
````
favorite_fruits  = ['apple', 'banana', 'orange']
fruit = 'apple'
if fruit in favorite_fruits:
    print("you really like %s" %fruit)
fruit = 'banana'
if fruit in favorite_fruits:
    print("you really like %s" %fruit)
fruit = 'orange'
if fruit in favorite_fruits:
    print("you really like %s" %fruit)
fruit = 'lemon'
if fruit in favorite_fruits:
    print("you really like %s" %fruit)
````

## 5-8 以特殊方式跟管理员打招呼 :
- 创建一个至少包含5个用户名的列表，且其中一个用户名为'admin' 。想象你要编写代码，在每位用户登录网站后都打印一条问 候消息。遍历用户名列表，并向每位用户打印一条问候消息。
- 如果用户名为'admin' ，就打印一条特殊的问候消息，如“Hello admin, would you like to see a status report?”。
- 否则，打印一条普通的问候消息，如“Hello Eric, thank you for logging in again”。
````
users =  ['admin', 'Eric', 'Bob', 'Black', 'Green']
for user in users:
    if user == 'admin':
        print("Hello %s, would you like to see a status report?" %user) 
    else:
        print('Hello %s, thank you for logging in again' %user)
````

## 5-9 处理没有用户的情形 :
- 在为完成练习5-8编写的程序中，添加一条if 语句，检查用户名列表是否为空。
- 如果为空，就打印消息“We need to find some users!”。
- 删除列表中的所有用户名，确定将打印正确的消息。
````
users =  ['admin', 'Eric', 'Bob', 'Black', 'Green']
if users:
    for user in users:
        if user == 'admin':
            print("Hello %s, would you like to see a status report?" %user) 
        else:
            print('Hello %s, thank you for logging in again' %user)
else:
    print('We need to find some users!')

users.clear()
print('----------')
if users:
    for user in users:
        if user == 'admin':
            print("Hello %s, would you like to see a status report?" %user) 
        else:
            print('Hello %s, thank you for logging in again' %user)
else:
    print('We need to find some users!')

````

## 5-10 检查用户名 :
- 按下面的说明编写一个程序，模拟网站确保每位用户的用户名都独一无二的方式。
- 创建一个至少包含5个用户名的列表，并将其命名为current_users 。 
- 再创建一个包含5个用户名的列表，将其命名为new_users ，并确保其中有一两个用户名也包含在列表current_users 中。
- 遍历列表new_users ，对于其中的每个用户名，都检查它是否已被使用。如果是这样，就打印一条消息，指出需要输入别的用户名;否则，打印一条消息，指出这个用户名未被使用。
- 确保比较时不区分大消息;换句话说，如果用户名'John' 已被使用，应拒绝用户名'JOHN' 。
````
current_users = ['Green', 'Tom', 'BOB', 'Black', 'WhItE']
new_users = ['Bob', 'Smith', 'white', 'Oliver', 'Sam']
current_users = [x.title() for x in current_users]
for new_user in new_users:
    if new_user.title()  in current_users:
        print("input a new user")
    else:
        print("%s is never be used" %new_user)
````


## 5-11 序数 :
- 序数表示位置，如1st和2nd。大多数序数都以th结尾，只有1、2和3例外。
- 在一个列表中存储数字1~9。 遍历这个列表。
- 在循环中使用一个if-elif-else 结构，以打印每个数字对应的序数。输出内容应为1st 、2nd 、3rd 、4th 、5th 、6th 、7th 、8th 和9th ，但每个序 数都独占一行。
````
nums = range(1, 10)
for num in nums:
    if num ==1:
        print("1st")
    elif num == 2:
        print('2nd')
    elif num == 3:
        print('3rd')
    else:
        print('%sst' %num)
````

 
