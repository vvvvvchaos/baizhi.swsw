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
   
   ![869090167eb8a8447dcd6445bf90535](https://user-images.githubusercontent.com/107102952/205489292-9b312de0-5d3f-4094-9e39-91fa048c5a4b.png)

   
5)运行测试类


#9.service层-业务逻辑层（服务层）

1）建立业务逻辑层

2）Implement interface按钮自动生成实现类对象（PostServiceImpl)
![5f5b41891c1e37f58e439639d948b6e](https://user-images.githubusercontent.com/107102952/205488824-595b3a6b-c069-44e8-9f0b-a537ba65e7b5.png)

![a0c47fa24a9568ed56fb7a353d5748f](https://user-images.githubusercontent.com/107102952/205488837-feddd061-1562-4587-9359-d662cb18e172.png)

3)类比PostDaoTest，用注解@Autowired，引入PostDao，用来操作数据库

![1f810299f35348dd1c7bcc1940be905](https://user-images.githubusercontent.com/107102952/205489095-34cf8789-fae3-4195-b883-d735d0019b11.png)

4）类比PETApplication,用注解@Service，来标明这是一个service文件

![00f9266ed88d531ad0f454d6f8bcec1](https://user-images.githubusercontent.com/107102952/205489379-92e22876-df8c-42d2-9e9f-59887d73c71f.png)

5）用注解@Autowired，将数据传入前端--用Http把数据传递到前端页面
   
   如何进行传递？
   
    使用下面这个方法来存储你想要传递至前端页面地数据（把session想象成一个容器，可以存放各种数据）
    
    setAttribute方法地括号中分为两部分
    
    逗号之前的部分，是你给数据起个名字，方便前端页面通过名字取出你想要地数据
    
    逗号之后是你要存的那个数据
    
    ![53b9a13fd96b283d9d7294fad71a973](https://user-images.githubusercontent.com/107102952/205490249-28cf1100-594a-4978-8fd5-5f5d03b57db1.png)

#10.编写测试类测试service

1）新建测试类

![9948cb291cf4072621641ce1771585a](https://user-images.githubusercontent.com/107102952/205490507-5628bc16-6e40-4121-874e-7d9581f62ec9.png)

2）引入注解@RunWith 和 @SpringBootTest

![1b177cc412fb726d046fad614d9546e](https://user-images.githubusercontent.com/107102952/205490519-d4a1b11e-18b9-4f06-b301-716a94a66525.png)

3）引入注解@Autowired，用于引入被测试的类-postService 

![20b793a5c05e29a5e4225da8a937021](https://user-images.githubusercontent.com/107102952/205490875-2dc99cc0-6647-443b-93a2-a5e877ee567d.png)

4）如何取出存入在session里面的数据-getAttribute方法

![7e15077b6be202739760bfd05cf85da](https://user-images.githubusercontent.com/107102952/205490956-7dea4cfc-8142-4243-a3c7-f857b6b227b5.png)

#11.前端
1)将相关文件导入webapp文件夹

![ea4b0005ab9d301ddad99d40692b11d](https://user-images.githubusercontent.com/107102952/205570549-041912cb-3713-45aa-9cec-825f2fae572e.png)
![0f6c81322389cfa78160abbf0fc5e6b](https://user-images.githubusercontent.com/107102952/205570574-7955cdd3-02f2-4c85-b857-07ded63d0b7b.png)

2）创建controller包

3）用@Controller//向springboot标明这是一个controller文件

![03fa5045d6389593268ecb1bdc29758](https://user-images.githubusercontent.com/107102952/205572348-1d9e6560-231d-494a-8387-4a5c84528951.png)

4） @Autowired ，引入Service

5) redirect:/是跳转到前端的一种方式，叫做重定向跳转

6)@RequestMapping 为类和方法起一个别名

![4a2873faa0beec4eddeeca4cc360f4f](https://user-images.githubusercontent.com/107102952/205578351-269d7132-7da9-40d4-8be7-28cca6c5b596.png)

注意：修改代码后要重启服务器







    



























