title: Hello World
date: 2016/12/06 12:06:06
categories:
- JAVA�����
tags:
- ����
- jacoco
---

# 1���ַ�ʽ

## 1.1 eclipseֱ�Ӱ�װ�������
![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco1.png)

**install new soft ��װ��� eclemma java code coverage**

����
![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco2.png)


���
![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco3.png)

���������Ԫ���Ա���
![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco4.png)

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco5.png)




## 1.2 ͨ��maven����������ӡ��Ԫ���Ա���

**pom.xml�ļ��м����Ӧ�Ĳ��֣�plugin����**


```
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>cn.whx</groupId>
    <artifactId>jacoco-test</artifactId>
    <version>0.0.1-SNAPSHOT</version>

    <dependencies>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.11</version>
            <scope>compile</scope>
        </dependency>
    </dependencies>
    <build>
          <plugins>
            <plugin>
                <groupId>org.jacoco</groupId>
                <artifactId>jacoco-maven-plugin</artifactId>
                <version>0.7.1.201405082137</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>prepare-agent</goal>
                        </goals>
                    </execution>
                    <execution>
                        <id>report</id>
                        <phase>prepare-package</phase>
                        <goals>
                            <goal>report</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
</project>
```


**maven clean package �����б��� ��target�ļ��� site index.html**

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco6.png)

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco7.png)






���

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco8.png)

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco9.png)


**ע����ʱ����ᷢ�ֻᱬ���������Skipping JaCoCo execution due to missing execution data file�������ԭ������Ϊû�б�������࣬����ʹ�� clean package -Dmaven.test.skip=false**



# 2.���ڼ��ָ��
���ɴ���������˼��Ӣ����ַ���ϣ�
[http://www.eclemma.org/jacoco/trunk/doc/counters.html](http://note.youdao.com/)

**Instructions (C0 Coverage)**

- ��Ҫ�Ǽ����ֽ����ļ��ĸ����ʡ�

**Branches (C1 Coverage)**

- JaCoCoҲ�����֧��������if�� switch��䡣��Ҫ�Ǽ����֧�ġ�
- û�и��ǣ��ڸ���û�з�֧������ִ�У����꣩
- ���ָ��ǣ�ֻ���ڸ��з�֧������һ�����Ѿ���ִ�У����꣩
- ȫ���ǣ��ڸ��и���֧������ִ�У����꣩

**Cyclomatic Complexity **

- Ȧ���Ӷ�(Cyclomatic Complexity)��һ�ִ��븴�Ӷȵĺ�����׼����������������һ��ģ���ж��ṹ�ĸ��ӳ̶ȣ������ϱ���Ϊ��������·��������Ҳ�����Ϊ�������еĿ����������ʹ�õĲ�����������Ȧ���Ӷȴ�˵�����������ж��߼����ӣ����������������ڲ��Ժ�ά��������Ŀ��ܴ���͸ߵ�Ȧ���Ӷ����źܴ��ϵ����ע�⣬JaCoCo�������쳣����ķ�֧����try-catch��Ҳ�������Ӹ����ԡ�����ͷ�֧����ء�ʵ���ϣ���ȥ����ĸ����о��Ѿ�ȷ����һ��������Ȧ���Ӷȣ��� CC������ 10 �ķ������ںܴ�ĳ�����ա�
- ����Ȧ���Ӷȵ���⣬���Կ��������ӡ�

- [http://blog.csdn.net/lg707415323/article/details/7790660 ](http://note.youdao.com/)
- [http://www.ibm.com/developerworks/cn/java/j-cq03316/](http://note.youdao.com/)

- �Լ�һ��ͼ

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco10.png)

**Lines**

- ��Ҫ������ڸ��ǵ�ʵ��Դ���������Դ�ļ��и��ǡ�ͨ�����ʶ����״̬��
- û�и��ǣ��ڸ����κ�ָ��ִ�У���ɫ������
- ���ָ��ǣ�ֻ���ڸ��е�ָʾ��һ�����Ѿ���ִ�У���ɫ������
- ȫ���ǣ��ڸ��е�����ָ����ִ�У���ɫ������


**Methods**

- ÿ���ǳ��󷽷���������һ��ָ����캯���;�̬��ʼ��������������




# 4.��������

**�����ϴ���
�������ࣺ**

```
package utils;

import java.math.BigDecimal;

/**
 * ��ȫת��Ǯ�ĵ�λ
 * 
 * @author rutine
 * @time Apr 28, 2015 3:52:18 PM
 */
public class MoneyUtil {


    /**
     * <pre>
     * ����˵�� : ��ȫת��double����, ����λԪ��ǮתΪ��
     *     ��: 19.9(Ԫ), ���ս��: 1990(��)
     * </pre>
     * 
     * @param money ���(Ԫ)
     * @return
     */
    public static int getFenMoney(String money) {
        BigDecimal hundred = new BigDecimal(100);
        BigDecimal decimalMoney = new BigDecimal(money);
        return decimalMoney.multiply(hundred).intValue();
    }


    /**
     * ����˵�� : ��ȡ����, ����С������λ��
     * 
     * @param money �ܽ��(Ԫ)
     * @param quantity ����
     * @return
     */
    public static double getUnitMoney(String money, int quantity) {
        if ("50".equals(money)) {
            System.out.println("branch1");
        }else if ("60".equals(money)) {
            System.out.println("branch2");
        }else if ("70".equals(money)) {
            System.out.println("branch3");
        }else {
            System.out.println("other branch");
        }
        BigDecimal decimalMoney = new BigDecimal(money);
        BigDecimal unitMoney = decimalMoney.divide(new BigDecimal(quantity), 2, BigDecimal.ROUND_HALF_UP);

        return unitMoney.doubleValue();
    }
}
```



**�����ࣺ**

```
package test;

import org.junit.Test;

import utils.MoneyUtil;

public class TestMoney {

    @Test
    public void testGetUnitMoney(){
        MoneyUtil.getUnitMoney("50", 2);
        MoneyUtil.getUnitMoney("60", 2);
        MoneyUtil.getUnitMoney("70", 2);
        MoneyUtil.getUnitMoney("75", 2);
    }
}
```




**���Խ����ָ�����**

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco11.png)


��һ��ָ��instructions��ָ�����ֽ����ļ���������18/62����˼��  18Ϊδִ�е�ָ��������62Ϊ��ָ��������

 ![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco12.png)
 
 ![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco13.png)



��һ��ָ��branches��ָ���Ƿ�֧�ĸ��������0/6��0Ϊδִ�еķ�֧������6Ϊ�ܷ�֧����������else������뵽��֧�����С���������㲻дelse,�򸲸��ʲ���Ϊ100%��

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco14.png)

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco15.png)


��һ��ָ�꣬ΪȦ���Ӷȡ�missed Ϊδ���Ե�������cxtyΪ������

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco16.png)

�������������Ȧ���Ӷ�Ϊɶ��4

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco17.png)

�򵥵Ļ���������ͼ

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco18.png)

v=e-n+2   8���� - 6���ڵ� + 2 = 4


��һ��ָ�꣬Ϊ�еĸ��������missed Ϊδ���Ե�������linesΪ������

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco19.png)

ͬ���ģ������������

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco20.png)

������10�С�δ������0�С�

��һ��ָ�꣬Ϊ�����ĸ��������missed Ϊδ���Ե�������methodsΪ������

![image](http://ohoyqlwj0.bkt.clouddn.com/jacoco21.png)

�����ע�⣬�����ʴﵽ100%����������ĳ����ok�ˣ�
