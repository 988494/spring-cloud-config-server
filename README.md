# spring-cloud-bus+springcloud config server
## 配置
server:<br>
  &nbsp;&nbsp;port: 10003<br>
spring:<br>
  &nbsp;&nbsp;application:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;name: config<br>
  &nbsp;&nbsp;main:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;allow-bean-definition-overriding: true<br>
  &nbsp;&nbsp;cloud:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;config:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;server:<br>
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; git:<br>
         &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; uri: https://github.com/YangZhengXing0/springcloud-Config-sell-test.git<br>
         &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; #basedir: C:/Users/yang/Desktop/base/ #把远端git上的配置文件缓存到本地一个仓库，这里是设置的目录<br>
  &nbsp;&nbsp;rabbitmq:#spring-cloud-starter-bus-amqp的rabbitMQ默认连接的是<br>
#localhost:5672,所以这里需要自己配置自己的启动的rabbitMQ的地址<br>
#我这里是在window安装的docker上安装的RabbitMQ<br>
   &nbsp;&nbsp;&nbsp;&nbsp; host: 192.168.99.100<br>
    &nbsp;&nbsp;&nbsp;&nbsp;port: 5672<br>
eureka:<br>
 &nbsp;&nbsp;&nbsp;&nbsp; instance:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;prefer-ip-address: true<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;instance-id: config:${server.port}<br>
  &nbsp;&nbsp;&nbsp;&nbsp;client:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;service-url:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;defaultZone: http://weifuwukt.com:9000/eureka<br>
