# smartops-servicenow
smartops-servicenow项目主要提供smartops平台和servicenow平台互通通讯的问题。两个平台通过restful的方式进行交互实现数据之间的同步。项目主要展示平台时间数据互相打通的POC功能，仅作为方案实现的参考并不是可以直接用到生产环境的最终代码。如果需要使用到生产环境还需要对于异常处理，数据字段对齐等多个细节进行完善。

## 使用说明
应用目录如下图所示

![Hoa4V3zDJ8](https://github.com/swallretu/smartops-servicenow/assets/9640815/f809d88e-5840-450c-98d4-3bcd8746e99b)

- Business Rules: 在Business Rules中主要定义了何时触发调用外部系统的操作，以及对于那些资源等操作会触发外部操作，以及在触发条件发生之后具体执行什么样的script include脚本代码执行业务。
- Script Includes: 定义了具体操作的js代码，一般情况下servicenow调用外部系统或者外部系统调用servicenow所要实现的代码逻辑，通过定义响应的script include脚本实现对应代码功能（Javascript语法）。
- Inbound Integrations: servicenow提供对于外部系统访问的restapi，通过逐步定义Inbound Integration声明对应的Scripted REST APIs来定义响应的api接口，并且结合Scripted REST Resources对于接口实现相应的http GET/PUT/POST/DELETE等方法。
  - Scripted REST APIs
  - Scripted REST Resources 
- Outbound Integrations: 在Outbound Integration中通过定义REST Messages来调用外部系统提供的API，从而实现获取外部数据或者传递数据到外部系统。
  - REST Messages 
