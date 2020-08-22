#### BigDecimal类型的数据

##### 简述

​        BigDecimal 是 java 在  java.math 中提供的，主要是用来处理超过16为有效数字的数进行精度的运算。java中的基本类型数据像双精度double 是可以处理16位有效数据之内的数据进行精度计算的，但是在实际的开发中往往要计算的数据都会超过16位有效数字。而double在超过16位有效数字后就会有精度丢失问题，像涉及到金额方面重要的数据，精度丢失就会成为一个很严重的问题。而BigDecimal就在很好的程度上解决了这一问题。

##### 初始化BigDecimal

​     初始化 BigDecimal 最容易遇到的坑就是 初始化 double类型的数据和初始化 String 类型的数据。

   例如：

​        下列是将一个 String 类型的数据初始化为BigDecimal  ，同时将一个 double 类型的数据初始化为一个 BigDecimal 。

   其实在实际的生活中，我们可以看出这两个都是为 “0.1” 大小也是相同的，但是在程序中就不一样了。

   <img src="https://i.loli.net/2020/08/22/Ihpijz8RmFrutqU.png" ></a>

运行结果：

​      运行的结果与我们实际中的认知是完全不符合的。

<img src="https://i.loli.net/2020/08/22/EeFrjJYAWs3XtC2.png" ></a>

BigDecimal  类型初始化总结

  