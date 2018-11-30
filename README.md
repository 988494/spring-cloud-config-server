# spring-cloud-bus+springcloud config server
## 配置
server:<br>
  port: 10003<br>
spring:<br>
  application:<br>
    name: config<br>
  main:<br>
    allow-bean-definition-overriding: true<br>
  cloud:<br>
    config:<br>
      server:<br>
        git:<br>
          uri: https://github.com/YangZhengXing0/springcloud-Config-sell-test.git<br>
          #basedir: C:/Users/yang/Desktop/base/ #把远端git上的配置文件缓存到本地一个仓库，这里是设置的目录<br>
  rabbitmq:#spring-cloud-starter-bus-amqp的rabbitMQ默认连接的是<br>
#localhost:5672,所以这里需要自己配置自己的启动的rabbitMQ的地址<br>
#我这里是在window安装的docker上安装的RabbitMQ<br>
    host: 192.168.99.100<br>
    port: 5672<br>
eureka:<br>
  instance:<br>
    prefer-ip-address: true<br>
    instance-id: config:${server.port}<br>
  client:<br>
    service-url:<br>
      defaultZone: http://weifuwukt.com:9000/eureka<br>
