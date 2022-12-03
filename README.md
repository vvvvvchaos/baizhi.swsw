宠物寄养社区-管理帖子板块
=

———————————————————————————


#1.Maven的安装与配置




#2.新建项目




#3.导jar包入pom.xml


注意：1.导入包之后一定记得刷新！！！ 2.mysql部分的jar包注意版本对应


#4.建文件夹



#5.在文件夹中建包

1）java 文件夹 entity 实体类

2) java文件夹  dao

3）resouces文件夹下new directory

4)test文件夹下 new package





#6.导入配置文件

1.util

2.application.properties 注意图标

3.PostDaoMapper.xml

4.PostDaoTest.xml


在此介绍一下java中的分包分层

1）entity包-实体类包

   用来存放实体类的实体类

2）mapper包
   
   用来存放dao接口的mapper文件

3）test包
   
   用来存放测试类

4）dao层-数据持久化层
   
   负责对数据库进行增删改查
   

#7.

1）entity中建立Post类
   
   实现接口序列化，构造方法

2）application.properties
   
   注意因mysql版本不同导致的驱动类不同
   
   注意端口号
   
   注意修改密码
   
   注意mapper文件的位置
 
#8.

1）在PostDao方法中进行编写方法

2）在PostDaoMapper.xml中编写sql语句
   
   注意sql语句中的属性和Post类中的属性要一一对应

3）PostDaoTest类中编写测试语句

4）编写启动类 
   
   加注释@SpringBootApplication  出现开关按钮
   
   加注释@MapperScan("com.baizhi.ply.dao")  标明dao接口的位置
   
   调用这个启动类启动整个springboot项目
   
   SpringApplication.run(PETApplication.class,args);
   
5)运行测试类
























