# Lambda表达式

##### 简述：

​    java 8 提供的 Lambda 表达式 ，利用流和 Lambda 表达式对List集合进行处理。

##### 缺点：

​    （1）.若不用并行计算，很多时候计算速度没有比传统的 for 循环快。

​    （2）.容易使用 debug 模式调试。

​    （3）.在 lambda 语句中直接强制类型转换不方便。

​    （4）.不可以在 foreach 中修改 foreach 外面的值。

##### Lambda基本操作：

######     遍历：

```java
list.forEach(student1 -> System.out.println(student1.getWorke()));
```

###### 基本语法 ：

​    实体类 : :  属性     : 表示这个对象中的某个属性 。

​           例如 : Student :: getAge  

​    .collect (Collectors . 转换的类型) ： 表示最后的结果转换成什么类型。 

​           例如 ： .collect (Collectors . toList())  表示最后的结果转换成 list 集合。

​                        .collect (Collectors . toSet())  表示最后的结果转换成 set 集合。

​                        collect(Collectors.toMap(ppi003601 -> "键", Function.identity()));

  Function.identity() : 表示当前对象，并且递增取当前对象。

###### stream() 操作：

##### 排序 (sorted()):

######     升序 

 根据对象中的年龄来排序

```java
List<Student> collect = list.stream().sorted(Comparator.comparing(Student::getAge)).collect(Collectors.toList());
```

######   降序

根据对象中的年龄来降序

```java
List<Student> collect1 = list.stream().sorted(Comparator.comparing(Student::getAge).reversed()).collect(Collectors.toList());
```

##### 去重 :  (distinct())

```java
List<Student> distinctList = list.stream().distinct().collect(Collectors.toList());
```

##### 过滤：(filter())

```java
List<Student> collect2 = list.stream().filter(student1 -> student1.getAge() > 20).collect(Collectors.toList());
```

##### 提取：（map()）

   解释 ： 集合中提取出来单个对象中的某个属性。

```java
Set<String> nameSet = list.stream().map(Student::getName).collect(Collectors.toSet());
```

##### 统计：

######    求和（sum()）

```java
int sum = list.stream().mapToInt(Student::getAge).sum();
```

###### 平均值(average())

```java
double asDouble = list.stream().mapToInt(Student::getAge).average().getAsDouble();
```

###### 最大值 (max())

```java
int max = list.stream().mapToInt(Student::getAge).max().getAsInt();
```

###### 最小值 (min())

```java
int min = list.stream().mapToInt(Student::getAge).min().getAsInt();
```

##### 分组：(groupingBy())

######      单一分组：

```java
Map<String, List<Student>> collect3 = list.stream().collect(Collectors.groupingBy(Student::getName));
```

######     多重分组：

```java
Map<String, Map<String, List<Student>>> collect4 = list.stream().collect(Collectors.groupingBy(Student::getName, Collectors.groupingBy(Student::getSex)));
```



沈燕，袁彐静





![]()