# -python
简要介绍哈希表的定义使用，以及经典算法题

##什么是哈希表：哈希表是一种通过 键（key）快速找到值（value） 的数据结构
#重要特征：查找速度非常快：平均 O(1)

 #----------Python中的哈希表------#
#字典dict      #集合set#

#------------字典--------#

###创建字典

方法1

    student = {
    "name": "Tom",
    "age": 20,
    "score": 95
}

#方法2

    student = dict(name="Tom", age=20)

#方法三（空字典）

    student = {}
    student = dict()

###访问元素

    student = {
    "name": "Tom",
    "age": 20
    }

    print(student["name"])

###添加元素

    student["score"] = 95

###修改元素

    student["age"] = 21

###删除元素

#删除指定Key

del student["age"]

#pop()

    student.pop("age")

#####判断key是否存在（非常重要的应用）

    if "name" in student:
    print("存在")

 #字典常用操作#

1.获取全部Key  

    student.keys()

2.获取所有value

    student.values()

3.获取所有键值对

    student.items()

4.遍历字典

遍历key

    for key in student:
    print(key)

遍历value

    for value in student.values():
    print(value)

遍历key-value

    for key, value in student.items():
    print(key, value)

#_------集合set-------#

#特点：1 不重复   2 查找快   3 无序

#创建集合

    nums = {1,2,3,4}
    nums = set([1,2,3,4])

#自动去重

    nums = {1,1,2,2,3}
    {1,2,3}

#添加元素

    nums.add(5)

#删除元素

    nums.remove(2)

 #判断是否存在 （非常有用！！！！！！！！！）

     if 3 in nums:
        print("存在")
        时间复杂度O(1)

 #-------------哈希表快速原因----（哈希函数）---#

 流程
 
       key → hash函数 → 数组位置

      #哈希表用途

1.统计次数

    统计字符串中每个字符出现次数
    s = "apple"

    count = {}

    for c in s:
        if c in count:
            count[c] += 1
        else:
            count[c] = 1

    print(count)

 输出

     {'a':1,'p':2,'l':1,'e':1}
     
2.去重

      nums = [1,2,2,3,3,4]

    nums = list(set(nums))

    print(nums)

结果

    [1,2,3,4]

3.快速查找

例如 Two sum O(n)

    nums = [2,7,11,15]
    target = 9

    hashmap = {}

    for i, num in enumerate(nums):
        if target - num in hashmap:
            return [hashmap[target-num], i]

      hashmap[num] = i

4.最长连续序列
   利用  set  快速判断  num+1 是否存在

#dict  VS set

dict :key ->value

set : only value

      dict:{"a":1,"b":2}      
      set:{"a","b","c"}

#-------------三大用途---------#

1.记录出现次数

          count[num] += 1

2.判断是否存在/遍历存在

      if num in set:
      if key in dict:

      for k,v in dict.items():

 3.建立映射关系   

      value → index
      set(nums)

      
