# Chapter9 类
## 9-1 餐馆 ： 创建一个名为Restaurant 的类， 其方法__init__() 设置两个属性： restaurant_name 和cuisine_type 。 
* 创建一个名为describe_restaurant() 的方法和一个名为open_restaurant() 的方法， 其中前者打印前述两项信息， 而后者打印一条消息， 指出餐馆正在营业。
* 根据这个类创建一个名为restaurant 的实例， 分别打印其两个属性， 再调用前述两个方法。
````
class Restaurant():
    def __init__(self, restaurant_name, cuisine_type):
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
    
    def describe_restaurant(self):
        print('restaurant_name is %s, cuisine_type is %s.' %(self.restaurant_name, self.cuisine_type))

    def open_restaurant(self):
        print('restaurant :%s is running' %self.restaurant_name)

restaurant = Restaurant('aa', 'bb')
restaurant.describe_restaurant()
restaurant.open_restaurant()

````
## 9-2 三家餐馆 ： 根据你为完成练习9-1而编写的类创建三个实例， 并对每个实例调用方法describe_restaurant() 。
````
class Restaurant():
    def __init__(self, restaurant_name, cuisine_type):
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
    
    def describe_restaurant(self):
        print('restaurant_name is %s, cuisine_type is %s.' %(self.restaurant_name, self.cuisine_type))

    def open_restaurant(self):
        print('restaurant :%s is running' %self.restaurant_name)

restaurantA = Restaurant('aa', 'bb')
restaurantB = Restaurant('ab', 'bc')
restaurantC = Restaurant('ac', 'cd')
restaurantA.describe_restaurant()
restaurantA.open_restaurant()
restaurantB.describe_restaurant()
restaurantB.open_restaurant()
restaurantC.describe_restaurant()
restaurantC.open_restaurant()

````
## 9-3 用户 ： 创建一个名为User 的类， 其中包含属性first_name 和last_name ， 还有用户简介通常会存储的其他几个属性。 
* 在类User 中定义一个名为describe_user() 的方法， 它打印用户信息摘要； 再定义一个名为greet_user() 的方法， 它向用户发出个性化的问候。
* 创建多个表示不同用户的实例， 并对每个实例都调用上述两个方法。
````
class User():
    def __init__(self, first_name, last_name, **other_info):
        self.first_name = first_name
        self.last_name = last_name
        self.other_info = other_info

    def describe_user(self):
        msg = 'first_name is ' + self.first_name + ', last_name is ' + self.last_name
        for k, v in self.other_info.items():
            msg +=', ' + k + ' is ' + str(v)
        print(msg)

    def greet_user(self):
        print('Hi, %s %s' %(self.first_name, self.last_name))


userA = User('Bill', 'Gates')
userB = User('Tom', 'Green', age=10)
userC = User('Kate', 'White', age=20, sex='female')
userA.describe_user()
userA.greet_user()
userB.describe_user()
userB.greet_user()
userC.describe_user()
userC.greet_user()        
````

## 9-4 就餐人数 ： 在为完成练习9-1而编写的程序中， 添加一个名为number_served 的属性， 并将其默认值设置为0。 
* 根据这个类创建一个名为restaurant 的实例； 打印有多少人在这家餐馆就餐过， 然后修改这个值并再次打印它。
* 添加一个名为set_number_served() 的方法， 它让你能够设置就餐人数。 调用这个方法并向它传递一个值， 然后再次打印这个值。
* 添加一个名为increment_number_served() 的方法， 它让你能够将就餐人数递增。 调用这个方法并向它传递一个这样的值： 你认为这家餐馆每天可能接待的就餐人数。
````
class Restaurant():
    def __init__(self, restaurant_name, cuisine_type):
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
        self.number_served = 0
    
    def describe_restaurant(self):
        print('restaurant_name is %s, cuisine_type is %s, number_served is %s.' %(self.restaurant_name, self.cuisine_type, self.number_served))

    def open_restaurant(self):
        print('restaurant :%s is running' %self.restaurant_name)

    def set_number_served(self, num):
        self.number_served = num

    def increment_number_served(self, max_num):
        if(self.number_served>=max_num):
            print('The max number_served is %s.' %max_num)
        else:
            self.number_served +=1

restaurant = Restaurant('aa', 'bb')
restaurant.describe_restaurant()
restaurant.number_served = 2
restaurant.describe_restaurant()
restaurant.set_number_served(12)
restaurant.describe_restaurant()
restaurant.increment_number_served(12)
restaurant.describe_restaurant()

````

## 9-5 尝试登录次数 ： 在为完成练习9-3而编写的User 类中， 添加一个名为login_attempts 的属性。
* 编写一个名为increment_login_attempts() 的方法，它将属性login_attempts 的值加1。 
* 再编写一个名为reset_login_attempts() 的方法， 它将属性login_attempts 的值重置为0。
* 根据User 类创建一个实例， 再调用方法increment_login_attempts() 多次。 打印属性login_attempts 的值， 确认它被正确地递增； 然后， 调用方法reset_login_attempts() ， 并再次打印属性login_attempts 的值， 确认它被重置为0。
````
class User():
    def __init__(self, first_name, last_name, **other_info):
        self.first_name = first_name
        self.last_name = last_name
        self.other_info = other_info
        self.login_attempts = 0

    def increment_login_attempts(self):
        self.login_attempts += 1
    
    def descrbe_login_attempts(self):
        print('login_attempts is %s' %self.login_attempts)

    def reset_login_attempts(self):
        print('reset the login_attempts')
        self.login_attempts = 0

user = User('Tom', 'Hank')
user.descrbe_login_attempts()
for i in range(10):
    user.increment_login_attempts()
user.descrbe_login_attempts()
user.reset_login_attempts()
user.descrbe_login_attempts()
````

## 9-6 冰淇淋小店 ： 冰淇淋小店是一种特殊的餐馆。 
* 编写一个名为IceCreamStand 的类， 让它继承你为完成练习9-1或练习9-4而编写的Restaurant 类。 这两个版本的Restaurant 类都可以， 挑选你更喜欢的那个即可。 
* 添加一个名为flavors 的属性， 用于存储一个由各种口味的冰淇淋组成的列表。 编写一个显示这些冰淇淋的方法。 
* 创建一个IceCreamStand 实例， 并调用这个方法。
````
class Restaurant():
    def __init__(self, restaurant_name, cuisine_type):
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
    
    def describe_restaurant(self):
        print('restaurant_name is %s, cuisine_type is %s.' %(self.restaurant_name, self.cuisine_type))

    def open_restaurant(self):
        print('restaurant :%s is running' %self.restaurant_name)

class IceCreamStand(Restaurant):
    def __init__(self, restaurant_name, cuisine_type, flavors):
        super().__init__(restaurant_name, cuisine_type)
        self.flavors = flavors

    def show_favor(self):
        print(self.flavors)

iceCreamStand = IceCreamStand('iceCream', 'ice', ['blur','orange','apple'])
iceCreamStand.show_favor()
````

## 9-7 管理员 ： 管理员是一种特殊的用户。
* 编写一个名为Admin 的类， 让它继承你为完成练习9-3或练习9-5而编写的User 类。 
* 添加一个名为privileges 的属性， 用于存储一个由字符串（如"can add post" 、 "can delete post" 、 "can ban user" 等） 组成的列表。 
* 编写一个名为show_privileges() 的方法， 它显示管理员的权限。 创建一个Admin 实例， 并调用这个方法。
````
class User():
    def __init__(self, first_name, last_name, **other_info):
        self.first_name = first_name
        self.last_name = last_name
        self.other_info = other_info

    def describe_user(self):
        msg = 'first_name is ' + self.first_name + ', last_name is ' + self.last_name
        for k, v in self.other_info.items():
            msg +=', ' + k + ' is ' + str(v)
        print(msg)

    def greet_user(self):
        print('Hi, %s %s' %(self.first_name, self.last_name))

class Admin(User):
    def __init__(self, first_name, last_name, privileges, **other_info):
        super().__init__(first_name, last_name, **other_info)
        self.privileges = privileges

    def show_privileges(self):
        print(self.privileges)

admin = Admin('aa', 'ab', ['can add post', 'can delete post', 'can delete post'])
admin.show_privileges()


````
## 9-8 权限 ： 编写一个名为Privileges 的类， 它只有一个属性——privileges ， 其中存储了练习9-7 所说的字符串列表。 
* 将方法show_privileges() 移到这个类中。 
* 在Admin 类中， 将一个Privileges 实例用作其属性。 创建一个Admin 实例， 并使用方法show_privileges() 来显示其权限。
````
class User():
    def __init__(self, first_name, last_name, **other_info):
        self.first_name = first_name
        self.last_name = last_name
        self.other_info = other_info

    def describe_user(self):
        msg = 'first_name is ' + self.first_name + ', last_name is ' + self.last_name
        for k, v in self.other_info.items():
            msg +=', ' + k + ' is ' + str(v)
        print(msg)

    def greet_user(self):
        print('Hi, %s %s' %(self.first_name, self.last_name))


class Privileges():
    def __init__(self, privileges):
        self.privileges = privileges
    
    def show_privileges(self):
        print(self.privileges)

class Admin(User):
    def __init__(self, first_name, last_name, privileges, **other_info):
        super().__init__(first_name, last_name, **other_info)
        self.privileges = Privileges(privileges)



admin = Admin('aa', 'ab', ['can add post', 'can delete post', 'can delete post'])
admin.privileges.show_privileges()

````

## 9-9 电瓶升级 ： 在本节最后一个electric_car.py版本中， 给Battery 类添加一个名为upgrade_battery() 的方法。 
* 这个方法检查电瓶容量， 如果它不是85， 就将它设置为85。 
* 创建一辆电瓶容量为默认值的电动汽车， 调用方法get_range() ， 然后对电瓶进行升级， 并再次调用get_range() 。 你会看到这辆汽车的续航里程增加了。
````
class Car():
    """一次模拟汽车的简单尝试"""
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()

    def read_odometer(self):
        print("This car has " + str(self.odometer_reading) + " miles on it.")

    def update_odometer(self, mileage):
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        self.odometer_reading += miles

class Battery():
    """一次模拟电动汽车电瓶的简单尝试"""
    def __init__(self, battery_size=70):
        """初始化电瓶的属性"""
        self.battery_size = battery_size

    def describe_battery(self):
        """打印一条描述电瓶容量的消息"""
        print("This car has a " + str(self.battery_size) + "-kWh battery.")

    def get_range(self):
        """打印一条消息， 指出电瓶的续航里程"""
        if self.battery_size == 70:
            range = 240
        elif self.battery_size == 85:
            range = 270
        message = "This car can go approximately " + str(range)
        message += " miles on a full charge."
        print(message)
    
    def upgrade_battery(self):
        if self.battery_size !=85:
            self.battery_size = 85
        

class ElectricCar(Car):
    """电动汽车的独特之处"""
    def __init__(self, make, model, year):
        """初始化父类的属性， 再初始化电动汽车特有的属性"""
        super().__init__(make, model, year)
        self.battery = Battery()

my_tesla = ElectricCar('tesla', 'model s', 2016)
my_tesla.battery.describe_battery()
my_tesla.battery.upgrade_battery()
my_tesla.battery.describe_battery()
````
## 9-13 使用OrderedDict ： 在练习6-4中， 你使用了一个标准字典来表示词汇表。 请使用OrderedDict 类来重写这个程序， 并确认输出的顺序与你在字典中添加键—值对的顺序一致。
````
````

## 9-14 骰子 ： 模块random 包含以各种方式生成随机数的函数， 其中的randint() 返回一个位于指定范围内的整数， 例如， 下面的代码返回一个1~6内的整数：
from random import randint
x = randint(1, 6)

* 请创建一个Die 类， 它包含一个名为sides 的属性， 该属性的默认值为6。 
* 编写一个名为roll_die() 的方法， 它打印位于1和骰子面数之间的随机数。 创建一个6面的骰子， 再掷10次。 
* 创建一个10面的骰子和一个20面的骰子， 并将它们都掷10次
````
````
。
9-15 Python Module of the Week ： 要了解Python标准库， 一个很不错的资源是网站Python Module of the Week。 请访问http://pymotw.com/ 并查看其中的目录， 在其中找一个你感兴趣的模块进行探索， 或阅读模块collections 和random 的文档。
