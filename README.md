# spring-cloud-bus+springcloud config server
## 配置
server:
  port: 10003
spring:
  application:
    name: config
  main:
    allow-bean-definition-overriding: true
  cloud:
    config:
      server:
        git:
          uri: https://github.com/YangZhengXing0/springcloud-Config-sell-test.git
          #basedir: C:/Users/yang/Desktop/base/ #把远端git上的配置文件缓存到本地一个仓库，这里是设置的目录
  rabbitmq:#spring-cloud-starter-bus-amqp的rabbitMQ默认连接的是
#localhost:5672,所以这里需要自己配置自己的启动的rabbitMQ的地址
#我这里是在window安装的docker上安装的RabbitMQ
    host: 192.168.99.100
    port: 5672
eureka:
  instance:
    prefer-ip-address: true
    instance-id: config:${server.port}
  client:
    service-url:
      defaultZone: http://weifuwukt.com:9000/eureka
