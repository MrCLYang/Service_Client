################################
1.此为AIDL的简单通讯,通过客户端实现对服务端的方法调用和数据的获取
编码步骤:1.首先创建服务端项目Server
          (1)创建需要连接的AIDL文件,里面有方法,以及变量的传递,同时Make Project,生成AIDL的接口文件
          (2)创建引用该AIDL文件的服务,实现AIDL的sub方法拿到自身定义的方法
        2.创建客户端项目Client
          (1)在项目创建后,将客户端的AIDL的整个文件连带包名不变拷贝到(src/main)下,然后Make Project,生成AIDL的接口文件
          (2)在主要界面进行Activity和Server的联系,创建ServiceConnection的匿名类,以及重写onServiceConnected()

    重点:绑定服务的时候,采用隐式启动服务,参数与服务器端的action要一致,即"服务器包名.aidl接口文件名"  
         Android5.0后无法只通过隐式Intent绑定远程Service ,需要通过setPackage()方法指定包名 
#################################

