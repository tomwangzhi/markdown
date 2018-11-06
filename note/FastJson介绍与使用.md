
## 介绍
Fastjson是一个性能很好的Java语言实现的Json解析器和生成器，由来自阿里巴巴的工程师开发。具有极快的性能。

**特点：**

	1.快速（比其他任何基于Java的解析器和生成器更快，包括Jackson）
	2.强大（支持普通JDK类包括任意Java Bean Class、Collection、Map、Data或enum）
	3.零依赖（没有依赖其他任何类库，除JDK）
	4.支持注解、支持全类型序列化
**生成json使用：**
	
	1.引入maven依赖

	 <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>fastjson</artifactId>
            <version>1.2.45</version>
     </dependency>

	2.测试样例：

	 User user = new User();
     user.setId("1");
     user.setName("xiaoming");
     user.setSex("男");
     Object obj = JSON.toJSON(user);
     System.out.println(obj);

	3.输出结果：
	{"sex":"男","name":"xiaoming","id":"1"}

**解析json使用**
	
	测试样例：

	 String strUser = "{\"name\":\"xiaoming\",\"id\":\"24\",\"sex\":\"男\"}";
     JSONObject ob = JSONObject.parseObject(strUser);
     User u = JSONObject.toJavaObject(ob,User.class);
     System.out.println(u);

	测试结果：
	User{id='24', name='xiaoming', sex='男'}
	