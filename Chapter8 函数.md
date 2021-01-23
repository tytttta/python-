# Chapter8 函数

## 8-1 消息 ： 编写一个名为display_message() 的函数， 它打印一个句子， 指出你在本章学的是什么。 
* 调用这个函数， 确认显示的消息正确无误。
````
def display_message():
    '''show what is learned in this chapter'''
    print('This chapter show what is function')

display_message()
````

## 8-2 喜欢的图书 ： 编写一个名为favorite_book() 的函数， 其中包含一个名为title 的形参。 
* 这个函数打印一条消息， 如One of my favorite books is Alice in Wonderland 。 
* 调用这个函数，并将一本图书的名称作为实参传递给它。
````
def favorite_book(title):
    print('One of my favorite books is %s。 ' %title)

favorite_book('Green Tale')
````

## 8-3 T恤 ： 编写一个名为make_shirt() 的函数， 它接受一个尺码以及要印到T恤上的字样。 
* 这个函数应打印一个句子， 概要地说明T恤的尺码和字样。
* 使用位置实参调用这个函数来制作一件T恤； 再使用关键字实参来调用这个函数。
````
def make_shirt(size, msg):
    print('This T_shirt size is %s, its message is %s.' %(size, msg))
    # print('This T_shirt size is %d, its message is %s.' %(size, msg))

make_shirt(10, 'abc')
````

## 8-4 大号T恤 ： 修改函数make_shirt() ， 使其在默认情况下制作一件印有字样“I love Python”的大号T恤。
* 调用这个函数来制作如下T恤： 一件印有默认字样的大号T恤、 一件印有默认字样的中号T恤和一件印有其他字样的T恤（尺码无关紧要） 。
````
def make_shirt(size, msg='I love Python'):
    print('This T_shirt size is %s, its message is %s.' %(size, msg))
    # print('This T_shirt size is %d, its message is %s.' %(size, msg))

make_shirt('big')
make_shirt('middle')
make_shirt(10, 'abc')
````
## 8-5 城市 ： 编写一个名为describe_city() 的函数， 它接受一座城市的名字以及该城市所属的国家。
* 这个函数应打印一个简单的句子， 如Reykjavik is in Iceland 。 
* 给用于存储国家的形参指定默认值。 为三座不同的城市调用这个函数， 且其中至少有一座城市不属于默认国家。
````
def describe_city(city_name, country_name='China'):
    print('%s is in %s' %(city_name, country_name))

describe_city('Shanghai')
describe_city('TaiWan')
describe_city('London', 'English')
````

## 8-6 城市名 ： 编写一个名为city_country() 的函数， 它接受城市的名称及其所属的国家。
* 这个函数应返回一个格式类似于下面这样的字符串："Santiago, Chile" 至少使用三个城市-国家对调用这个函数， 并打印它返回的值。
````
def city_country(city_name, country_name='China'):
    print('%s, %s' %(city_name.title(), country_name.title()))

city_country('Shanghai', 'china')
city_country('TaiWan',  'china')
city_country('London', 'English')
````
## 8-7 专辑 ： 编写一个名为make_album() 的函数， 它创建一个描述音乐专辑的字典。 
* 这个函数应接受歌手的名字和专辑名， 并返回一个包含这两项信息的字典。 
* 使用这个函数创建三个表示不同专辑的字典， 并打印每个返回的值， 以核实字典正确地存储了专辑的信息。
* 给函数make_album() 添加一个可选形参， 以便能够存储专辑包含的歌曲数。 
* 如果调用这个函数时指定了歌曲数， 就将这个值添加到表示专辑的字典中。 
* 调用这个函数， 并至少在一次调用中指定专辑包含的歌曲数。
````
def make_album(singer, album, num=0):
    if num :
        return  {'singer': singer, 'album': album, 'num': num}
    else:
        return {'singer': singer, 'album': album}

print(make_album('Jay', 'Fan'))
print(make_album('Liu', 'XX'))
print(make_album('Zhang', 'XX2', 5))
````

## 8-8 用户的专辑 ： 在为完成练习8-7编写的程序中， 编写一个while 循环， 让用户输入一个专辑的歌手和名称。 
* 获取这些信息后， 使用它们来调用函数make_album() ， 并将创建的字典打印出来。
* 在这个while 循环中， 务必要提供退出途径。
````
def make_album(singer, album, num=0):
    if num :
        return  {'singer': singer, 'album': album, 'num': num}
    else:
        return {'singer': singer, 'album': album}


while True:
    singer = input("input the singer's name or the quit to exit:\n")
    if(singer == 'quit'):
        break;
    album = input("input hte album's name:\n")
    print(make_album(singer, album))
````
## 8-9 魔术师 ： 创建一个包含魔术师名字的列表， 并将其传递给一个名为show_magicians() 的函数， 这个函数打印列表中每个魔术师的名字。
````
def show_magicians(name_list):
    for name in name_list:
        print(name)

name_list = ['Tom', 'Bil', 'Kate']
show_magicians(name_list)
````

## 8-10 了不起的魔术师 ： 在你为完成练习8-9而编写的程序中， 编写一个名为make_great() 的函数， 对魔术师列表进行修改， 在每个魔术师的名字中都加入字样“the Great”。 
* 调用函数show_magicians() ， 确认魔术师列表确实变了。
````
def make_great(name_list):
    for i in range(len(name_list)):
        name_list[i] = 'The Great ' +  name_list[i]

def show_magicians(name_list):
    for name in name_list:
        print(name)

name_list = ['Tom', 'Bil', 'Kate']
make_great(name_list)
show_magicians(name_list)
````

## 8-11 不变的魔术师 ： 修改你为完成练习8-10而编写的程序， 在调用函数make_great() 时， 向它传递魔术师列表的副本。 
* 由于不想修改原始列表， 请返回修改后的列表， 并将其存储到另一个列表中。 
* 分别使用这两个列表来调用show_magicians() ， 确认一个列表包含的是原来的魔术师名字， 而另一个列表包含的是添加了字样“the Great”的魔术师名字。
````
def make_great(name_list):
    for i in range(len(name_list)):
        name_list[i] = 'The Great ' +  name_list[i]
    
    return name_list

def show_magicians(name_list):
    for name in name_list:
        print(name)

name_list = ['Tom', 'Bil', 'Kate']
revise_name_list = make_great(name_list[:])
show_magicians(name_list)
show_magicians(revise_name_list)
````

## 8-12 三明治 ： 编写一个函数， 它接受顾客要在三明治中添加的一系列食材。 
* 这个函数只有一个形参（它收集函数调用中提供的所有食材） ， 并打印一条消息， 对顾客点的三明治进行概述。
* 调用这个函数三次， 每次都提供不同数量的实参。
````
def sandwich_food(*foods):
    for food in foods:
        print('The sandwich will add %s' %food)

sandwich_food('tomato')
sandwich_food('pomato','egg')
sandwich_food('pomato', 'tomato','egg')
````
## 8-13 用户简介 ： 复制前面的程序user_profile.py， 在其中调用build_profile() 来创建有关你的简介； 调用这个函数时， 指定你的名和姓， 以及三个描述你的键-值对。
````
def build_profile(first, last, **user_info):
    """创建一个字典， 其中包含我们知道的有关用户的一切"""
    profile = {}
    profile['first_name'] = first
    profile['last_name'] = last
    for key, value in user_info.items():
        profile[key] = value
    return profile

user_profile = build_profile('Bill', 'Gates', location='US' ,field='cs')
print(user_profile)
````
## 8-14 汽车 ： 编写一个函数， 将一辆汽车的信息存储在一个字典中。 
* 这个函数总是接受制造商和型号， 还接受任意数量的关键字实参。 这样调用这个函数： 提供必不可少的信息， 以及两个名称—值对， 如颜色和选装配件。 
* 这个函数必须能够像下面这样进行调用：car = make_car('subaru', 'outback', color='blue', tow_package=True)
````
def make_car(producer, type, **info):
    car = {}
    car['producer'] = producer
    car['type'] = type
    for k, v in info.items():
        car[k]=v
    return car

car = make_car('subaru', 'outback', color='blue', tow_package=True)
print(car)
````
