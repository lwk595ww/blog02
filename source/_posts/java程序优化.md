#### java程序优化

#####    程序优化

​       前言 ： 程序中的循环中尽量不要有多计算，多查询，多异常的处理。

######        1.try...catch

​           在本质上来说，try...catch 是非常耗费性能的，不应该放在循环里使用，尽量放在循环外使用。例如 ：try...catch 包裹 for循环，同样嫩够达到效果。

######        2. 字符串拼接

​            方法一 ：采用 "+" 号的方式来拼接。  例如 ： string a = b+"abc";

​            缺点 ： 耗时长。 (不建议使用)

​           方法二 ：采用 StringBuilder 的 append() 方法来拼接字符串。(推荐使用)

```java
     StringBuilder builder = new StringBuilder();
     for (int i=0;i<1000;i++){
         //拼接字符串
         builder.append(i).append(";");
     }
        //将builder类型的转换为普通类型的字符串
        String data = builder.toString();
        //分割字符串
        StringTokenizer st = new StringTokenizer(data,";");
        while (st.hasMoreTokens()){
            String str = st.nextToken();
            System.out.println(str);
        }

        System.out.println(System.currentTimeMillis());
```

######      3.字符串分割

​          方法一 ： 采用 "split()" 方法来分割字符串。 例如 ： String[] a = data.split();

​          缺点 ：耗时长 （不建议使用）

​          方法二 ： 采用 StringTokenizer  st  =  new StringTokenizer("分割的字符串","按什么条件分割")；

```java
     StringBuilder builder = new StringBuilder();
     for (int i=0;i<1000;i++){
         //拼接字符串
         builder.append(i).append(";");
     }
        //将builder类型的转换为普通类型的字符串
        String data = builder.toString();
        //分割字符串
        StringTokenizer st = new StringTokenizer(data,";");
        while (st.hasMoreTokens()){
            String str = st.nextToken();
            System.out.println(str);
        }

        System.out.println(System.currentTimeMillis());
```

######     4. 复制数组

​     方法一 ： 采用循环的方式复制数组 。 (不建议使用)

​     方法二 ：采用 System.arraycopy() 方法来复制

```java
        int[] arryA = new int[]{1,2,3,4,5};
        int[] arryB = new int[6];
        arryB[0] = 10;
        /**
         * arryA : 有数据的数组
         * srcPos : 从有数据的数组从第几个开始复制
         * arryB : 表示没有数据的数组
         * desPos : 表示从没有数据的数组从第几个开始粘贴
         * arryA.length : 表示复制多少个
         */
        System.arraycopy(arryA,0,arryB,1,arryA.length);

        for (int i =0 ; i <arryB.length;i++){
            System.out.println(arryB[i]);
```

