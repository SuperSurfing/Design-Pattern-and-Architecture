### Abstract
&emsp;&emsp;Read The Fucking Source Code �����һ�����ϵͳ����õİ취�����ǣ����ڴ��������˵��RTFSC �����Ƿǳ���Ч��������ͷ�۵��¡���ô����û�и�Ч RTFSC �İ취�أ�

&emsp;&emsp;������Ҫ�����ţ�ǡ���Ч�Ķ�Դ�롱�ķ������ܽ��Լ���ʵ���е���ᡣ�����ⷽ�澭������ӣ��һ᲻�ϸ����Լ����ĵá�  

### Content
- [RTFSC Common Methods](#rtfsc_common_methods)
  - [���ĵ�](#���ĵ�)
  - [�������](#�������)
  - [����Ͳ���](#����Ͳ���)
  - [����־](#����־)
  - [����ܹ�](#����ܹ�)
  - [��������](#��������)
- [��־ƪ](#��־ƪ)
- [�ܹ�ƪ](#�ܹ�ƪ)
  - [�ⲿ�ܹ�](#�ⲿ�ܹ�)
  - [�ڲ��ܹ�](#�ڲ��ܹ�)
  - [ģ���ɫ](#ģ���ɫ)
- [����ƪ](#����ƪ)
  - [Notepad++](#notepad)
  - [OpenGrok](#opengrok)
  - [Understand](#understand)
  - [Depends.exe](#depends.exe)
  - [Meld](#meld)
- [Reference](#reference)
- 


### RTFSC_Common_Methods

�������Ҹ��ݴ�ţ�ķ�����Լ���ʵ�����ܽ�ġ��Ķ�Դ�롱��ͨ�÷�����

1. ���ĵ����ȶ��ĵ�  
2. ���������ֱ�۸������� Features    
3. �����Ͳ��������build and deploy��  
4. �Ķ���־   
5. ���϶�������ܹ�  

> ���Ķ���ʽ����ص㣬�����ڶ���ÿһ�г�ʽ�룬����������Ч�ʵ�͸��̽�����Ķ����Ӷ��˽�ϵͳ�ļܹ�����Ϊģʽ���Ա�������Ҫ�˽��κ�Ƭ�ε�ϸ��ʵ��ʱ���ܹ��ܿ������϶�ӳ������ĳ�ʽ��λ�ã�ֱ����һ�̣�����ϸ����ʱ������


�������ϵ�ͨ�÷���������һЩС���ɣ���� [��������](#��������)����  

1. Debug���鿴 CallStack
2. ���� Abrreviation Table
3. �� UML Graph �� WorkFlow Graph
4. �о� Demo
5. Rebuild���޸Ĵ��벢�۲���
6. ʹ�� Depends.exe �鿴 dll �ĵ����ӿ�



#### ���ĵ�

1. �ȶ��û��ĵ���Overview, Manual Book, Quick Start�����ٶ�����ĵ�  
2. �������������������ܺ�֪�������Ҷ�Ӧ�½�  
3. ����ĵ�����Ҫһ�ζ�����������Զ��մ����ض���Ӧ�½�   
4. google ��ز��ͣ�����ǰ�˵ľ���  


#### �������

1. ���հ�װ������  
2. ������ Manual Book���������� Features  
3. �鿴��װĿ¼���˽���� exe �� dll  
4. ��������ĵ���INI and XML����ע���SYSTEM\Services and SOFTWARE��  
5. Procexp.exe �۲������


#### ����Ͳ���

����������������ã�  
1. Ϊ����Ĳ�������  
2. �˽⿪����������ܺ������Ŀ�

����һ������ý���ͨ�ÿ�ܡ��͡������Ŀ⡱�г������� google ���֪ʶ��


#### ����־

���ڴ���������ر��Ƕ���̣��̣߳����ֲ�ʽϵͳ�������� debug �������ף���ʱ��Ч��Ҳ�ܵ͡���ʱ������Ч�������ǡ����������������־����  

���Ƽ��������ǽ� ��log�� �� ��source code�� ������������������ô������ο� [��־ƪ](#��־ƪ)��


#### ����ܹ�

���ڴ��������һ��ʼ��Ҫ�����ھ����ʵ��ϸ�ڣ�����Ҫ������������ļܹ��������ⲿ�ܹ������л��������ڲ��ܹ���ģ��֮��Ĺ�ϵ�������巽�����뿴 [�ܹ�ƪ](#�ܹ�ƪ)


#### ��������

##### Debug

�������õ��ֶΣ����Բ鿴 CallStack���ǳ���������⺯���Ĺ�ϵ������Ĳ�Ρ�



#### ���ܹ�

���϶�������ܹ����¼�������MVC��������ģ��Ľ�ɫ����κ��໥��ϵ�����ܹ�ͼ
����ģ�飺Glue��Interface��BI����Implement��BL����Algorithm��Configuration��Task

#### ���ͨ��ģʽ

��д Demo ��������Դ�����õ��ĸ������IPC��callback��


#### Debug

�鿴 callstack and thread context


#### ������������


#### ���ڹ���



### ��־ƪ

���ڴ���������ر��Ƕ���̣��̣߳����ֲ�ʽϵͳ�������� debug �������ף���ʱ��Ч��Ҳ�ܵ͡���ʱ������Ч�������ǡ����������������־����  

��һ��ѡ�� Notepad++ ��������־�������÷��ο� [����ƪ](#����ƪ)��

#### PID_TID

�Ƽ�����־�д�ӡ PID+TID ���ο� glog�����������ڶ���̻���̳߳��򣬿��Ժܷ����ͨ�� PID+TID ���й��ˣ�˳�ų����ִ������ȥ�Ķ� source code �����԰����������ʧ�� Code ��ɭ���С�  

���⣬ͨ�� PID+TID �����Ժ����ɵ��ҵ�**���̺��̵߳����**��

#### FunctionName

����Ƕ�ײ�αȽ���ĺ���������ͨ�� ��FunctionName�� ���˵��Ӻ�����ֻ��ĳ�����������ִ�����С�  

#### Enter_Leave

���ڱȽϴ�ĺ������ߵ��ò�αȽ���ĺ�����һ��Ҫע�⺯���ı߽硣ͨ�� ��Enter >>�� �� ��Leave <<�� ����ȷ�������ı߽硣


#### grep

Notepad++ �ṩ��������ҡ��Ĺ��ܡ����ա�������ҡ�������ʵ�ֺܶ�߼����ң����� exclude ���ҡ����ڡ�������ʽ�������Բο�һ�����Ͽ���ѧϰ��  

- [�����������ڱ��ʽ](https://github.com/SuperSurfing/Design-Pattern-and-Architecture/blob/master/Regular%20Expression%20for%20Python/Quick%20Start%20for%20Regular%20Expression.md)
- [Code-Reading Tools](https://www.spinellis.gr/ismr/tools/indexw.htm)

��Ȼ������д��������ƻ�����Ҫ��Ҳ�����Լ����֣��� python ��дһ������������˵�С���� 



### �ܹ�ƪ

���ڴ������������ʮ�������������е� source code ��һ��ʼ��Ҫȥ�о������ģ��ʵ�ִ��룬����Ҫ�������ļܹ��������ⲿ�ܹ����ڲ��ܹ���  

#### �ⲿ�ܹ�

�ⲿ�ܹ�ʵ���Ͼ��������������л�����������������ϵͳ�еĽ�ɫ���ر��Ƕ��ڷֲ�ʽ���������Ҫ����������Щ�����  
������˵���ⲿ�ܹ�������  
1. ��ɫ  - Server/Client, Master/Slave, UserMode/KernelMode  
2. ���  
3. �������ⲿ��  


#### �ڲ��ܹ�

�ڲ��ܹ���Ҫ��ģ��ֲ㡢��ɫ����֯��ϵ���ⷽ����Ҫ�����֪ʶ�Ļ��ۣ����������ģʽ������ܹ����ڴˣ��Ҳο� [��һ�壺����ܹ�����](http://www.ruanyifeng.com/blog/2016/09/software-architecture.html) ���г����ֳ��õļܹ���  

##### �ֲ�ܹ�

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090302.png)

##### �¼������ܹ�

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090304.png)


##### ΢�˼ܹ�

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090306.png)

##### ΢����ܹ�

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090307.png)

##### �Ƽܹ�

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090311.png)


#### ģ���ɫ

��ģ���ɫ����Ҫ���ҵĸ��˾����ܽᣬ�ش˵����������������������µĽ�ɫ��


Role | Description
---|---
�����ߣ�sender�� | message/request �ķ����ߡ����磺 broswer �� server ����� request��Ӧ�ó���������ݿ��ѯ����IPC ��Ϣ�����ߵ�
�����ߣ�receiver��| �� sender ��Ӧ��
�����ߣ�handler�� | ���Ӽܹ��У�receiver �� handler �Ƿ���ġ����ŵ��ǣ���ȫ����Դ���⡣
�ӿ�����루BI��| ����ģ��ķֽ��ߡ�C++�е�������PImpl�࣬JS �еĺ���������ȶ������ֽ�ɫ�ĵ䷶��
��������루Glue��| �����ڽ�����ģ��ճ����һ�𣬱��磺�ص�����ע�ᣬ����ָ��map���¼�-��Ӧ�󶨡�������룬�����ģ���ʼ���ĵط���
�����ļ�����ģ�飨Cfg Parser��|ר����������ļ���д��ģ�飬���� INI�ļ���XML �ļ���JSON �ļ���ע���ȡ�
I/Oģ�� | �ļ���д��Ӧ�ò㵽�ں˲��I/O
���ݿ��дģ�� | ORM��SQL ���
�쳣����ģ�� | �����쳣��Rollback
�ػ����̣�daemon��| Windows service ����һ��Ὺһ�������߳�ѭ��






### ����ƪ


#### Notepad

����ѡ Notepad++ ��������־���� Linux ��Ҳ����ʹ�� vim ���ı��༭����Notepad++ �� Find ��Ctrl + f���Ĺ������£�  

![](https://github.com/SuperSurfing/Design-Pattern-and-Architecture/blob/master/Read%20The%20Fuck%20Source%20Code/Images/notepad.jpg?raw=true)   

���У��ļ����������� Linux - grep ���  

���⣬���ա�������ҡ�������ʵ�ֺܶ�߼����ң����� exclude ���ҡ����ڡ�������ʽ�������Բο�һ�����Ͽ���ѧϰ��  

- [�����������ڱ��ʽ](https://github.com/SuperSurfing/Design-Pattern-and-Architecture/blob/master/Regular%20Expression%20for%20Python/Quick%20Start%20for%20Regular%20Expression.md)
- [Code-Reading Tools](https://www.spinellis.gr/ismr/tools/indexw.htm)

��Ȼ������д��������ƻ�����Ҫ��Ҳ�����Լ����֣��� python ��дһ������������˵�С����  


#### OpenGrok

OpenGrok �ṩ��һ�� web app �Ĵ����Ķ���ʽ����ƽ̨�����������ô�����ʾ target ���ڵ� Function Name �����������Կ��Բο� [RTFSC with OpenGrok](https://mazhuang.org/2016/12/14/rtfsc-with-opengrok/) ��  

##### ��װ

�ο� [How to setup OpenGrok](https://github.com/oracle/opengrok/wiki/How-to-setup-OpenGrok) �� [win7 ��װ OpenGrok](https://blog.csdn.net/finewind/article/details/47362525)��  

��һ�������ز���װ [JAVA JDK8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)��Ȼ�����û�������

```
JAVA_HOME: C:\Program Files\Java\jdk1.8.0_191
JRE_HOEME: C:\Program Files\Java\jre1.8.0_191
```

�������������롰java -version�����ɲ鿴�汾��Ϣ������֤�Ƿ�װ�ɹ���


�ڶ��������ز���ѹ��װ [TomCat](http://tomcat.apache.org/) ��Ȼ�����û�������   

```
C:\Program Files\Java\apache-tomcat-9.0.13\bin\startup.bat
```

ע�⣺Ҫ�ԡ�����Ա������С� tomcat����ʱ���� localhost:8080 ���Դ� tomcat ��ҳ

�������� ���ز���ѹ��װ [ctags-win32](https://github.com/universal-ctags/ctags-win32/releases)��

���Ĳ��� ���ز���ѹ��װ [opengrok](https://oracle.github.io/opengrok/)

���岽�� �� OpenGrok ��װĿ¼���½�Ŀ¼ data �� source �����Է��������ط������ٽ� OpenGrok\bin\source.war ������ tomcat\whatapps\ Ŀ¼�¡���ʱ���� tomcat ������ localhost:8080/source ���Դ� OpenGrok ��

��������������������

```
java -Xmx524m -jar E:\Code\OpenGrok\opengrok-1.1-rc80\lib\opengrok.jar -W
E:\Code\OpenGrok\opengrok-1.1-rc80\data\configuration.xml -c
E:\Code\OpenGrok\ctags2018\ctags.exe -P -S -v -s E:\Code\AI\source -d
E:\Code\OpenGrok\opengrok-1.1-rc80\data
```

���߲����ο� [RTFSC with OpenGrok](https://mazhuang.org/2016/12/14/rtfsc-with-opengrok/) �޸� tomcat��



#### Understand

�ο� [Understand ��װ](https://my.oschina.net/krysl/blog/2070243)





### Reference

- [7�ַ��������������ߴ����Ķ�����](https://zhuanlan.zhihu.com/p/45493061)




