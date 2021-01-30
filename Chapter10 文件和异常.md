# Chapter9 文件和异常

## 10-1 Python学习笔记 ： 在文本编辑器中新建一个文件， 写几句话来总结一下你至此学到的Python知识， 其中每一行都以“In Python you can”打头。 
* 将这个文件命名为 learning_python.txt， 并将其存储到为完成本章练习而编写的程序所在的目录中。 
* 编写一个程序， 它读取这个文件， 并将你所写的内容打印三次： 第一次打印时读取整个文件； 第二次打印时遍历文件对象； 第三次打印时将各行存储在一个列表中， 再在with 代码块外打印它们。
````
with open('learning_python.txt') as file:
    content = file.read()
    print(content)

print('-------------------')
with open('learning_python.txt') as file:
    for line in file:
        print(line.rstrip())

print('-------------------')
with open('learning_python.txt') as file:
    lines = file.readlines()

for line in lines:
    print(line.rstrip())
````

## 10-2 C语言学习笔记 ： 可使用方法replace() 将字符串中的特定单词都替换为另一个单词。 下面是一个简单的示例， 演示了如何将句子中的'dog' 替换为'cat'：
````
>>> message = "I really like dogs."
>>> message.replace('dog', 'cat')
'I really like cats.'
````
* 读取你刚创建的文件learning_python.txt中的每一行， 将其中的Python都替换为另一门语言的名称， 如C。 将修改后的各行都打印到屏幕上。
````
with open('learning_python.txt') as file:
    content = file.read()
    print(content.replace('Python', 'C'))

print('-------------------')
with open('learning_python.txt') as file:
    for line in file:
        print(line.rstrip().replace('Python', 'C'))

print('-------------------')
with open('learning_python.txt') as file:
    lines = file.readlines()

for line in lines:
    print(line.rstrip().replace('Python', 'C'))
````
## 10-3 访客 ： 编写一个程序， 提示用户输入其名字； 用户作出响应后， 将其名字写入到文件guest.txt中。
````
name = input('input your name:\n')

with open('guest.txt', 'w') as name_file:
    name_file.write(name + '\n')
````
## 10-4 访客名单 ： 编写一个while 循环， 提示用户输入其名字。 用户输入其名字后， 在屏幕上打印一句问候语， 并将一条访问记录添加到文件guest_b个文件中的每条记录都独占一行。
````
name = input('input your name, while input quit to end:\n')

with open('guest_b.txt', 'w') as name_file:
    while name!= 'quit':
        print('Hi, %s!' %name)
        name_file.write(name + '\n')
        name = input('input your name, while input quit to end:\n')     
````
## 10-5 关于编程的调查 ： 编写一个while 循环， 询问用户为何喜欢编程。 每当用户输入一个原因后， 都将其添加到一个存储所有原因的文件中。
````
reason = input('input your reason liking programing, while input quit to end:\n')

with open('reason.txt', 'w') as reason_file:
    while reason!= 'quit':
        reason_file.write(reason + '\n')
        reason = input('input your reason liking programing, while input quit to end:\n')
````

## 10-6 加法运算 ： 提示用户提供数值输入时， 常出现的一个问题是， 用户提供的是文本而不是数字。 在这种情况下， 当你尝试将输入转换为整数时， 将引发TypeError 异常。 
* 编写一个程序， 提示用户输入两个数字， 再将它们相加并打印结果。 在用户输入的任何一个值不是数字时都捕获TypeError 异常， 并打印一条友好的错误消息。 
* 对你编写的程序进行测试： 先输入两个数字， 再输入一些文本而不是数字。
````
try:
    num1 = int(input("input num1:\n"))
    num2 = int(input("input num2:\n"))
except ValueError as e:
    print('input is not a number')
else:
    print('sum is:%s' %(num1 + num2))
````

## 10-7 加法计算器 ： 将你为完成练习10-6而编写的代码放在一个while 循环中， 让用户犯错（输入的是文本而不是数字） 后能够继续输入数字。
````
while True:
    try:
        num1 = int(input("input num1:\n"))
        num2 = int(input("input num2:\n"))
    except ValueError as e:
        print('input is not a number')
    else:
        print('sum is:%s' %(num1 + num2))
````

## 10-8 猫和狗 ： 创建两个文件cats.txt和dogs.txt， 在第一个文件中至少存储三只猫的名字， 在第二个文件中至少存储三条狗的名字。 
* 编写一个程序， 尝试读取这些文件，并将其内容打印到屏幕上。 
* 将这些代码放在一个try-except 代码块中， 以便在文件不存在时捕获FileNotFound 错误， 并打印一条友好的消息。 
* 将其中一个文件移到另一个地方， 并确认except 代码块中的代码将正确地执行。
````
try:
    with open('dogs.txt') as dog_file:
        for line in dog_file.readlines():
            print(line.rstrip())

    with open('cats.txt') as cat_file:
        for line in cat_file.readlines():
            print(line.rstrip())
except FileNotFoundError:
    print('file is not exist')
````
## 10-9 沉默的猫和狗 ： 修改你在练习10-8中编写的except 代码块， 让程序在文件不存在时一言不发。
````
try:
    with open('dogs.txt') as dog_file:
        for line in dog_file.readlines():
            print(line.rstrip())

    with open('cats.txt') as cat_file:
        for line in cat_file.readlines():
            print(line.rstrip())
except FileNotFoundError:
    pass
````
## 10-10 常见单词 ： 访问项目Gutenberg（http://gutenberg.org/ ） ， 并找一些你想分析的图书。 下载这些作品的文本文件或将浏览器中的原始文本复制到文本文件中。
* 你可以使用方法count() 来确定特定的单词或短语在字符串中出现了多少次。 例如， 下面的代码计算'row' 在一个字符串中出现了多少次：
````
>>> line = "Row, row, row your boat"
>>> line.count('row')
2 >
>>
````
* 请注意， 通过使用lower() 将字符串转换为小写， 可捕捉要查找的单词出现的所有次数， 而不管其大小写格式如何。
* 编写一个程序， 它读取你在项目Gutenberg中获取的文件， 并计算单词'the' 在每个文件中分别出现了多少次。
````
count = 0
try:
    with open('book.txt','r', encoding='UTF-8') as book_file:
        for line in book_file.readlines():
            count += line.lower().count('the')
except FileNotFoundError:
    pass
else:
    print("count is:" + str(count))
````

## 10-11 喜欢的数字 ： 编写一个程序， 提示用户输入他喜欢的数字， 并使用json.dump() 将这个数字存储到文件中。 再编写一个程序， 从文件中读取这个值， 并打印消息“I know your favorite number! It's _____.”。
````
import json
num = input('input your number:\n')

with open('num.json', 'w') as num_json:
    json.dump(int(num), num_json)

-----
with open('num.json') as read_json:
    print("I know your favorite number! It's %s" %json.load(read_json))
````

## 10-12 记住喜欢的数字 ： 将练习10-11中的两个程序合而为一。 如果存储了用户喜欢的数字， 就向用户显示它， 否则提示用户输入他喜欢的数字并将其存储到文件中。运行这个程序两次， 看看它是否像预期的那样工作。
````
import json

try:
    with open('num.json') as read_json:
        print("I know your favorite number! It's %s" %json.load(read_json))
except FileNotFoundError:
    num = input('input your number:\n')
    with open('num.json', 'w') as num_json:
        json.dump(int(num), num_json)
````
## 10-13 验证用户 ： 最后一个remember_me.py版本假设用户要么已输入其用户名， 要么是首次运行该程序。 我们应修改这个程序， 以应对这样的情形： 当前和最后一次运行该程序的用户并非同一个人。为此， 在greet_user() 中打印欢迎用户回来的消息前， 先询问他用户名是否是对的。 如果不对， 就调用get_new_username() 让用户输入正确的用户名。
````
import json
def get_stored_username():
    """如果存储了用户名， 就获取它"""
    filename = 'username.json'
    try:
        with open(filename) as f_obj:
            username = json.load(f_obj)
    except FileNotFoundError:
        return None
    else:
        return username

def get_new_username():
    """提示用户输入用户名"""
    username = input("What is your name? ")
    filename = 'username.json'
    with open(filename, 'w') as f_obj:
        json.dump(username, f_obj)
    return username

def greet_user():
    """问候用户， 并指出其名字"""
    username = get_stored_username()
    if username:
        input_name = input("input your name!")
        if username == input_name:
            print("Welcome back, " + username + "!")
        else:
            print("input the right name!")
            get_new_username()
    else:
        username = get_new_username()
        print("We'll remember you when you come back, " + username + "!")
    
greet_user()
````
