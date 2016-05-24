一个自动解释thrift javascript依赖的工具,并且提供相应的请求api接口.

使用方法:
1.npm install //安装依赖包
2.创建需要解释的thrift文件的配置文件
如创建thriftList.js文件,文件负责输出对应的thrift路径列表
如{
    "/api/test/getUnit" : "thrift/src/js/ITestServiceGetUnit",
    "/api/test/getUnitById" : "thrift/src/js/ITestServiceGetUnitById",
}
该配置对象对应的key为请求链接,value对应的是thrift的js文件路径

3.编写执行脚本



原理说明
1.分析依赖
1.1根据配置文件,定位具体的thrift js脚本,从当前js文件可知具体的thrift接口名
1.2在thrift文件目录根据thrift接口名定位具体的thrift函数体
1.3在具体thrift函数体分析其参数以及输出的依赖关系

2.生成js依赖文件,即模块化
2.1在具体的js文件中根据其对应的依赖关系以及模块化方式(AMD,CMD OR ES6)生成最终的js文件

3.输出配置文件
3.1输出配置文件,其包含每个接口的js路径,接口地址,输入参数类型,输出参数类型



//todo:english doc
//todo:create command for executing in the sh
