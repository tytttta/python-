# Chapter6 字典

## 6-1 人 ： 
-使用一个字典来存储一个熟人的信息， 包括名、 姓、 年龄和居住的城市。 该字典应包含键first_name 、 last_name 、 age 和city 。 将存储在该字典中的每项信息都打印出来。
````
person = {"first_name":"Tom", "last_name":"Green", "age": 14, "city":"hangzhou"}
print(person)
print(person['first_name'])
print(person['last_name'])
print(person['age'])
print(person['city'])
````

## 6-2 喜欢的数字 ： 
- 使用一个字典来存储一些人喜欢的数字。 请想出5个人的名字， 并将这些名字用作字典中的键； 想出每个人喜欢的一个数字， 并将这些数字作为值存储在字典中。 打印每个人的名字和喜欢的数字。
为让这个程序更有趣， 通过询问朋友确保数据是真实的。
````
fav_nums = {"Tom": 5, "Sam": 2, "Dean": 6, "Bill": 3, "Sara": 8}
print("Tom likes %s" %fav_nums['Tom'])
print("Sam likes %s" %fav_nums['Sam'])
print("Dean likes %s" %fav_nums['Dean'])
print("Bill likes %s" %fav_nums['Bill'])
print("Sara likes %s" %fav_nums['Sara'])
````

## 6-3 词汇表 ： Python字典可用于模拟现实生活中的字典， 但为避免混淆， 我们将后者称为词汇表。
- 想出你在前面学过的5个编程词汇， 将它们用作词汇表中的键， 并将它们的含义作为值存储在词汇表中。
- 以整洁的方式打印每个词汇及其含义。 为此， 你可以先打印词汇， 在它后面加上一个冒号， 再打印词汇的含义； 也可在一行打印词汇， 再使用换行符（\n ） 插入一个空行， 然后在下一行以缩进的方式打印词汇的含义。
````
dict = {"list":"a set of elements combined", "tuple": "a set of mutal elements combined"}
print("%s: %s" %("list", dict['list']))
print("%s: %s" %("tuple", dict['tuple']))
````

## 6-4 词汇表2 ： 既然你知道了如何遍历字典， 现在请整理你为完成练习6-3而编写的代码， 将其中的一系列print 语句替换为一个遍历字典中的键和值的循环。 确定该
循环正确无误后， 再在词汇表中添加5个Python术语。 当你再次运行这个程序时， 这些新术语及其含义将自动包含在输出中
````
fav_nums = {"Tom": 5, "Sam": 2, "Dean": 6, "Bill": 3, "Sara": 8}
for key in fav_nums.keys():
    print(key)

print("---------------")
for key in fav_nums:
    print(key)

print("---------------")
for name, value in fav_nums.items():
    print(name + ' likes ' + str(value))
````
## 6-5 河流 ： 创建一个字典， 在其中存储三条大河流及其流经的国家。 其中一个键—值对可能是'nile': 'egypt' 。
- 使用循环为每条河流打印一条消息， 如“The Nile runs through Egypt.”。
- 使用循环将该字典中每条河流的名字都打印出来。
- 使用循环将该字典包含的每个国家的名字都打印出来。
````
rivers = {'nile': 'egypt', 'hanghe':'china', 'henhe': 'india'}
for river, country in rivers.items():
    print("The %s runs through %s." %(river.title(), country.title()))

print("--------------")
for river in rivers:
    print(river)

print("--------------")
for country in rivers.values():
    print(country)
````

## 6-6 调查 ： 在6.3.1节编写的程序favorite_languages.py中执行以下操作。
- 创建一个应该会接受调查的人员名单， 其中有些人已包含在字典中， 而其他人未包含在字典中。
- 遍历这个人员名单， 对于已参与调查的人， 打印一条消息表示感谢。 对于还未参与调查的人， 打印一条消息邀请他参与调查。
````
fav_nums = {"Tom": 5, "Sam": 2, "Dean": 6, "Bill": 3, "Sara": 8}
invest_per = ["Mart",'Steven', 'Dean']
for per in invest_per:
    if per in fav_nums.keys():
        print('Thank for paticate in investagation, %s' %per)
    else:
        print("%s, i invite you to paticate in investgation" % per)

````

## 6-7 人 ： 在为完成练习6-1而编写的程序中， 再创建两个表示人的字典， 然后将这三个字典都存储在一个名为people 的列表中。 遍历这个列表， 将其中每个人的所有信息都打印出来。
````
person1 = {"first_name":"Tom", "last_name":"Green", "age": 14, "city":"Hangzhou"}
person2 = {"first_name":"Mike", "last_name":"Smith", "age": 31, "city":"Beijing"}
person3 = {"first_name":"Hank", "last_name":"Scotte", "age": 26, "city":"Nanjing"}
people = [person1, person2, person3]
for per in people:
    print(per)
````


## 6-8 宠物 ： 创建多个字典， 对于每个字典， 都使用一个宠物的名称来给它命名； 在每个字典中， 包含宠物的类型及其主人的名字。 将这些字典存储在一个名为pets的列表中， 再遍历该列表， 并将宠物的所有信息都打印出来。
````
pet1={'type': 'dog', 'master':'Mike'}
pet2={'type': 'cat', 'master':'Bill'}
pet3={'type': 'pig', 'master':'Bob'}
pets =[pet1, pet2, pet3]
for pet in pets:
    print(pet)
````

## 6-9 喜欢的地方 ： 创建一个名为favorite_places 的字典。 在这个字典中， 将三个人的名字用作键； 对于其中的每个人， 都存储他喜欢的1~3个地方。 为让这个练习更有趣些， 可让一些朋友指出他们喜欢的几个地方。 遍历这个字典， 并将其中每个人的名字及其喜欢的地方打印出来。
````
favorite_places = {'Tom': 'Hangzhou', 'Bill': ['Nanjing','Shanghai'], 'Cate': ['Beijing', 'Shanxi']}
for place in favorite_places:
    print('%s likes %s' %(place, favorite_places[place]))
````

## 6-10 喜欢的数字 ： 修改为完成练习6-2而编写的程序， 让每个人都可以有多个喜欢的数字， 然后将每个人的名字及其喜欢的数字打印出来。
````
fav_nums = {"Tom": 5, "Sam": 2, "Dean": [6, 8], "Bill": [3, 5, 7], "Sara": 8}
for person in fav_nums:
    print('%s likes %s' %(person, fav_nums[person]))
````

## 6-11 城市 ： 创建一个名为cities 的字典， 其中将三个城市名用作键； 对于每座城市， 都创建一个字典， 并在其中包含该城市所属的国家、 人口约数以及一个有关该城市的事实。 在表示每座城市的字典中， 应包含country 、 population 和fact 等键。 将每座城市的名字以及有关它们的信息都打印出来。
````
citys = {"NewYork" : {"country":"American", "population": 10,"fact":"American city"}
, "London":{"country": "English", "population": 20, 'fact':"English city"}
 , 'Nanjing':{'country':'Chinese', 'population': 200, 'fact':'Chinese city'}}  

for key, values in citys.items():
    print('the city name is: %s' %key )
    print('the country of city is: %s'  %values["country"])
    print('the population of city is: %s' %values["population"])
    print('the fact of city is: %s' %values["fact"])

````

## 6-12 扩展 ： 本章的示例足够复杂， 可以以很多方式进行扩展了。 请对本章的一个示例进行扩展： 添加键和值、 调整程序要解决的问题或改进输出的格式。
````
fav_numsOrAlpha = {"Tom": 5, "Sam": 2, "Dean": [6, 8], "Bill": [3, 5, 7], "Sara": 8}
fav_numsOrAlpha['Kate'] = 'a'
for name, fav in fav_numsOrAlpha.items():
    print('%s likes %s' %(name, fav_numsOrAlpha[name]))
````
