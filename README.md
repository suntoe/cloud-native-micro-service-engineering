# 一个演示实践性项目：云原生的微服务开发工程

下面长文，但主要的目的其实只有一个：招兵不买马。这个项目是开放的，不过，对参加者还是有一定要求，感兴趣的话请坚持看完，往下看到底。

## 想法：
   - 采用云原生的微服务架构: Docker, Kubernetes, ServiceMesh。
   - 实现一个功能需求上能覆盖计划技术栈的Web应用，目前考虑是一个二手计算机图书电商系统，是<b>真的准备把大家的书上架的</b>！
   - 前后端分离，以后端为主，后端最初会以JAVA的Spring Boot全家桶开始，包括MySQL、Redis、RabbitMQ、ElasticSearch等基本的主流技术栈，然后一步步增加别的，包括支持GO等其他语言；前端最初用React或Vue的全家桶开发SPA Web应用，然后扩展到小程序和手机App，建立大前端体系。
   - 自动化测试：单元测试、集成测试、性能测试、压力测试、端对端功能测试。整体测试覆盖率达到100%。
   - 以DevOps和GitOps为理念的工程开发体系：
     - 持续集成（CI），持续部署（CD）
     - 自动化运维、自动化监控报警、集中式日志
     - 部署私有仓库
     - 分布式调用链路追踪，
     - 整合常见开发工具，譬如SonarQube, Slack，GITHUB Issue、GITHUB Project等。
     - 建立开发者本机开发环境、测试环境、预生产环境和线上生产环境
   - 所使用的每一个技术都建立指南文档。
   - 后续会加入大数据分析。
   - 考虑演进成Serverless/FaaS，目前还没定，也可能会是另一个新项目。

## 目标：

  - 一期开发：
    - 阶段性目标：
      - 最小化功能实现，前后端打通，但只实现书店顾客前端，不做管理员后端
      - 单体应用，但是高度模块化
      - 手动部署，直接上线运行
    - 阶段性技术栈：
      - 后端 -> Java技术栈:
         - [ ] Spring MVC: REST API(JSON), Swagger (Spring Fox)
         - [ ] 测试: Junit5 (单元测试), Mockito (Mock), JaCoCo (测试覆盖率分析)
         - [ ] 数据库访问：Spring Data JPA（Hibernate），QueryDSL（动态查询），Flyway（数据库升级管理）
         - [ ] 日志：Logback
         - [ ] Jar包依赖管理：Maven
         - [ ] Spring Boot Actuator：监控数据采集和管理
         - [ ] 其他：Guava（工具类），Lombok (Java Bean代码生成)
      - 前端 -> React全家桶：
         - [ ] Webpack
         - [ ] 路由：React Router
         - [ ] UI库：Material Design或Ant Design
         - [ ] REST客户端：Axios
         - [ ] 测试：Jest或Mocha
      - [ ] Nginx做前端静态页面和后端API的统一入口
      - [ ] 关系数据库：MySQL单节点，H2（测试用）
      - [ ] 持续集成（CI）：Jenkins, GITHUB Hook/Action, SonarQube (代码质量检查)
      - [ ] Maven私有仓库：Nexus
      - [ ] 开发者本地Docker开发环境：Docker-compose
      - [ ] 用Helm或Kustomize手动部署到Kubernetes
      - [ ] Spring Boot Admin

  - 二期开发：
    - 阶段性目标：
      - 主要功能全部实现，包括新增管理员前端
      - 初步实现云原生的微服务架构
      - 自动部署
    - 阶段性技术栈
      - 后端增加：
        - [ ] 参数校验: javax.validation (JSR-303, Hibernate Validator)
        - [ ] 测试: Cucumber, TestContainers (容器化测试)，JMeter (性能测试和压测)，Contract
        - [ ] 权限控制：Spring Security (OAuth + JWT)
        - [ ] 日志：JSON日志格式
        - [ ] REST客户端: Resilience4J，Spring RestTemplate或Open Feign
        - [ ] 缓存：Jedis, Spring Data Redis, Caffeine
        - [ ] 全文检索：Spring Data Elasticsearch
        - [ ] 消息队列：Spring AMQP, RabbitMQ
        - [ ] 定时任务：TBD
      - 前端增加：
        - [ ] 状态管理：Redux或MobX
        - [ ] 测试：Selenium，Puppeteer
    - [ ] 关系数据库：高可用MySQL集群（MySQL Router + Group Replication + MySQL Shell）
    - [ ] 持续部署（CD）：ArgoCD（自动部署到Kubernetes）
    - [ ] 私有Docker仓库：Habor
    - [ ] 分布式缓存：Redis, Redis Sentinel
    - [ ] ELK (Elasticsearch + Logstash + Kibana): 全文检索，日志管理
    - [ ] 配置集中管理：Consul，Vault（MySQL等密码管理），Git2Consul
    - [ ] 分布式调用链路追踪：OpenTracing, Jaeger
    - [ ] 监控报警：Prometheus，Grafana

  - 三期开发：
    - 阶段性目标：
      - 主要功能全部实现
      - 完整实现云原生的微服务架构
      - 支持多语言
      - 云原生的持续集成、持续部署、自动化运维
    - 阶段性技术栈
      - 后端：
        - [ ] 支持用GO，Python，Node.JS，PHP开发微服务
        - [ ] 部分功能改用Serverless/FaaS实现
        - [ ] GraphQL API
        - [ ] gRPC
        - [ ] WebSocket
        - [ ] Workflow
      - 前端：
        - [ ] GraphQL API
        - [ ] 参与全链路数据采集追踪
      - [ ] API网关：Kong，Ambassador，Gloo或Traefix？
      - [ ] ServiceMesh: lstio
      - [ ] NoSQL数据库：MongoDB
      - [ ] 自动化运维：Ansible，Vagrant，Terraform
      - [ ] Jenkins-X, Skaffold
     
  - 四期开发：
    - 阶段性目标：
      - 对接云供应商：阿里云，AWS，Azure等
      - 大数据分析：Flink，Hive, Kafka等
      - 全面高可用
      - 尝试新技术
      - 手机App
    - 阶段性技术栈
      - 异步/Reactive Java, WebFlux
      - GraalVM, Quarkus
      - Flutter
      - Crossplane
     
## 问答：

> 1. "太多了，一看就跟不上，就连这个简介都看不懂"

  首先，我的观点是：看得懂就不用一起学了。一步一步来，让我们在实践中一起学习。

  现在的趋势就是云原生、微服务、DevOps，列出的这些技术是在跟着大趋势走，避免走弯路，避免重复发明轮子，希望走到主流的前排里。所以很自然，很多技术要么只能在它们的官方网站上才学得到，要么在网上零零散散的而且大部分还是重复的或过时的，跟着教程书学效果不好，真正的技术只可能在系统化的实践中才学得到学得好。

  然后，确实有太多技术点了（实际上还只是一小部分），这恰恰也是为什么要发起这个项目的原因之一：想展示如何系统的使用这些技术。有一定经验的程序员一定会不以为然，会觉得列出这么多名词术语有些唬人，确实这些大部分其实是成熟公司里已经用起来的技术，但是对刚入门的程序员来说会懵，一旦用过了、过了这个门槛，我们会发现很多方面其实只是知道不知道的区别，真正决定自己能走得多远站得多高的还是自己的基础能力和努力程度。

 > 2. “为什么不是Spring Cloud，为什么不是Dubbo （Spring Cloud Dubbo）？”

  微服务架构有两个主要路线，一是Sping Cloud，二是云原生，云原生的微服务架构里，服务治理的实现需要代码修改量少甚至不修改，那意味着代码侵入性小，跨语言支持方便，扩展性强，所以个人更喜欢云原生的方案。

  另一方面，Spring Cloud的开源演示项目已经非常多了，相对来说云原生方案因为比较新，数量还不多，有一定空白和更大项目发展空间，而且，云原生架构对基础架构和工程规范化的要求更高，而演示基础架构和规范化的工程开发正是这个项目的主要目标之一，希望能通过这个项目为促进云原生方案的普及作出贡献。

  Dubbo最初是阿里的RPC开源项目，中间暂停废弃过一段时间，现在阿里在大力推动，Spring Cloud Dubbo就是成果之一。坦率地讲是不太放心的：看着Dubbo的历史，再看看Dubbo现在这么极度依赖阿里一己之力...。和Dubbo接近的是gRPC，两相比较，gRPC的社区更开放更成熟，gRPC明确的是在这个项目的目标技术栈里的。

  另外，项目里会用到一些Spring Cloud体系内的组件，但总体来说，并不是Spring Cloud的方案。

> 3. “我不喜欢或者不习惯你提到的技术，我还想尝试一个更新的技术，能不能换成xx？”，譬如，有群友提到：“最近正好有计划做一个类似的，想做的平台是基于vertex的kotlin和actix的rust，以及尽量全套的异步组件，顺便试试postgresql。”

  选择成熟的主流技术是刻意的，这个项目的目标不是调研和尝鲜，它的目标是让大家脱离教程和作坊式的开发，让大家有机会实践贴近真实的规范化的工程开发。由此涉及的方方面面的细节必然会很多很杂，所以，为了降低项目失败的可能性，至少在前两阶段的计划中，我刻意采取了保守的技术选择策略。打个比方，去一个从零开始的初创团队，第一目标自然是要能迅速拿出一个MVP，在拿到市场反馈和调整产品迎合市场需求的循环中反复快速迭代，这时候，技术成熟好用更重要。

  以选择成熟的主流技术作为初始选择和尝试更新的技术并没有矛盾，在初期的迭代取得了阶段性成果以后，我们会得到一个合适的平台，我们会更有士气更有真实需求去实践更多的东西，甚至做些重复发明轮子的事情都可以。

  所以，就拿上面这个问题提到的“异步/非阻塞”的这个话题来说，因为在典型的Java Web应用系统里异步还不是主流，所以虽然这个想法不错，但并不适合初始阶段，将来，肯定会尝试把某个微服务改成异步，或者增加一个新的异步的微服务。

  其实，新技术的应用对程序员自身成长的价值，很多时候并不在于具体技术的本身，而在于从原有技术向新技术的迁移过程，这种迁移过程甚至比纯粹使用一个新技术去解决一个问题更具有意义和挑战性，好比现在如果有机会去参与淘宝双十一的话，肯定是没有早期从有到无、从个位数并发到亿级并发的技术演化对一个程序员成长的推动得有那么大。我个人也很想看看一个传统的同步/阻塞的架构向异步/非阻塞的架构迁移过程会产生什么故事，其他新技术的采用也是类似。

> 4. “一开始关注后端就好了，也不仅仅限制于前后端分离，需要的是提供如何将自己的前端技术栈接入该后端项目的接口规范和指南，像react，vue，或者后端渲染，或者模板引擎等等”

  第一期计划里是安排了实现一个书店顾客的Web前端，因为定位是一个系统化的工程化的演示性项目，前后端一起联动着实践才能体现工程中一个接口的开发过程。

> 5. "可以提供一些项目额外的包，例如该项目叫awesome, 就可以提供awesome-react-starter, awesome-vue-starter, awesome-blazor-starter, 毕竟专注后端，在一个项目集成与前端相关的一些东西多少会有些不好"

  是的，会产出一些框架性的胶水性的代码和工具，会控制在很薄的一层封装上，目的是减少重复代码，提高工程效率和架构细节上的的一致性。顺便强调一下，这个项目并不是专注后端，而是因为通常产品开发围绕着后端作为中心，所以目前重点演示以后端为主的完整产品开发工程。

> 6. “为什么要发起这么一个开源项目”

  一方面，对我自己而言，在公司内，即使螺丝钉拧得不亦乐乎，但是现在公司里技术的历史包袱实在太重太多，做什么都束手束脚，实在不爽，很多技术很有兴趣，实在是想去多多实践一下，需要有这么一个平台。

  另一方面，我看到的是，大部分演示实践性的开源项目，反复地低水平造轮子也好，有意无意地挖坑也好，很多不好的地方我想吐槽：

   - 除了src/main（Java的代码结构）和基本的编译启动说明，别的几乎什么都没有，我理解大部分开源项目是自嗨型，确实是因为作者实在没精力（我自己都这样），但有些项目的代码即使已经相当规模了却还保持这种状态。

   - 不写测试代码！特别是国内的一些作者。我的观点是，示范性项目，测试代码是重中之重，不写测试就是至少是客观上在误导大家

  当然，做这个项目的最重要的一个出发点，是因为我还没看到有哪个演示实践性开源项目是以接近实际工程的方式展示给大家的，它们通常只是专注于某一方面技术或小范围内的整合，譬如有的演示如何实现多数据源，有的演示如何做个helloworld项目在Kubernetes跑起来，有的演示如何部署一套ELK。这没问题，但是存在空白：没看到哪个项目展示了现实工程中应该怎么运！

  所以我们现在可以看到，很多程序员学习参考了这些开源项目后，src/main目录里的代码倒确实日趋统一了：所谓的SSH/CRUD代码重复从代码一致性的角度上看其实并不是一件坏事，但经常可见令人啼笑皆非的测试代码、五花八门的集成和部署方式、乱七八糟的监控和部署、混乱的开发环境管理。工程实践上的技术传递只能靠跳槽同事间的经验交流，没有公开有效的传承和沉淀，也就无从谈起有效的提高和创新。这对于很多初创团队很要命，他们的开发工程体系通常是空白，写代码和简单上线运行可能很快完成，但想搭建起能和代码有效配合的工程研发体系、想实现持续高效的产品研发输出时，却会消耗太多时间，还很可能只得到个勉强凑合的结果，在实现初期的产品交付的突破后，很可能会被低效的工程研发体系拖了后腿，自己好不容易打磨出个切合市场需求的产品，却因为技术拖累不得不放慢脚步，给了对手山寨自己弯道超车的机会，很多时候空降个BAT大牛来做CTO/技术总监也解决不了问题。

  另一方面，现在云原生架构日见成熟，会成为甚至已经成为下一代新的技术，云原生架构对基础架构、开发和运维等各方面都有了更高的要求，不仅是这些方面的各自技术的发展要求，而且需要对这些技术协调一致地使用起来，会产生很多新的工程化上的最佳实践。这是一个新技术的契机，也会是这个项目的主要价值之一。

> 7. "对参加者的要求"

  开源项目，理论上没有门槛，谁想参加都可以，以PR为准，PR一合并GITHUB会自动记入贡献者名单，所以其实有点废话了。

  不过，实践中还是有一定要求的，这个要求还很死板：能写代码。因为最初是以Java为主，所以后端开发最好是会Java和Spring，前端是JS/HTML，其他另外讨论。
  工程团队要简单直接，敏捷高效，开发运维一体（DevOps），不会有传统的运维，也不会有传统的测试，会逐渐有成员专注做测试设计并开发测试框架，也逐渐会有成员专注做自动化运维的框架和工具的开发。

> 8. "如何报名参加？"

  请Fork这个项目，把自己的GITHUB账号名字加到`members.md`那个文件，然后提交PR合并。

  我也新建了一个QQ群（1033056382），方便随时交流。目前不打算用微信。
