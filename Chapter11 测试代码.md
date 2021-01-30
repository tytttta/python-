# Chapter11 测试代码

## 11-1 城市和国家 ： 编写一个函数， 它接受两个形参： 一个城市名和一个国家名。 
* 这个函数返回一个格式为City, Country 的字符串， 如Santiago, Chile 。 将这个函数存储在一个名为city_functions.py的模块中。
* 创建一个名为test_cities.py的程序， 对刚编写的函数进行测试（别忘了， 你需要导入模块unittest 以及要测试的函数） 。 
* 编写一个名为test_city_country() 的方法， 核实使用类似于'santiago' 和'chile' 这样的值来调用前述函数时， 得到的字符串是正确的。 
* 运行test_cities.py ， 确认测试test_city_country() 通过了。
````
'''city_functions.py'''
def city_country(city, country):
    return city.title() +', ' + country.title()
````

````
'''test_cities.py'''
import unittest
from city_functions import city_country

class CityFunctionTestCase(unittest.TestCase):
    def test_city_country(self):
        """测试city_country方法"""
        result = city_country('hongkong', 'china')
        self.assertEqual(result, 'Hongkong, China')
    
    def test_city_country2(self):
        """测试city_country方法"""
        result = city_country('santiago', 'chile')
        self.assertEqual(result, 'Santiago, Chile')

unittest.main()

````

## 11-2 人口数量 ： 修改前面的函数， 使其包含第三个必不可少的形参population ， 并返回一个格式为City, Country - population xxx 的字符串，如Santiago, Chile - population 5000000 。 
* 运行test_cities.py， 确认测试test_city_country() 未通过。
* 修改上述函数， 将形参population 设置为可选的。 再次运行test_cities.py， 确认测试test_city_country() 又通过了。
* 再编写一个名为test_city_country_population() 的测试， 核实可以使用类似于'santiago' 、 'chile' 和'population=5000000' 这样的值来调用这个函数。 再次运行test_cities.py， 确认测试test_city_country_population() 通过了。
````
'''city_functions.py'''
def city_country(city, country, population):
    return city.title() +', ' + country.title() + " - population " + str(population)

def city_country2(city, country, population = 5000):
    return city.title() +', ' + country.title() + " - population " + str(population)
````

````
'''test_cities.py'''
import unittest
from city_functions import city_country
from city_functions import city_country2

class CityFunctionTestCase(unittest.TestCase):
    def test_city_country(self):
        """测试city_country方法"""
        result = city_country('hongkong', 'china')
        self.assertEqual(result, 'Hongkong, China')
    
    def test_city_country2(self):
        """测试city_country2方法"""
        result = city_country2('santiago', 'chile')
        self.assertEqual(result, 'Santiago, Chile - population 5000')

    def test_city_country_population(self):
        """测试city_country2方法"""
        result = city_country2('santiago', 'chile', 1000)
        self.assertEqual(result, 'Santiago, Chile - population 1000')

unittest.main()
````
