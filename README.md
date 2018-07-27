# jquery-page
一款小的jquery分页插件
该插件会根据数据量不同展现不同效果
1. 数据小于等于3页,这时候不会出现分页条，而是n个分页代码块
2. 数据大于3页,出现分页条
3. 数据只有一页时,隐藏分页条
4. csdn介绍用法: https://blog.csdn.net/lqx_sunhan/article/details/81251916
```
var pageObj = $("xx").page({
    url: '', // 后台接口地址
    data: {}, // 第一次请求时需要携带的参数
    getRes: function(r){},//用户自定义处理数据方法
    pageSize: 10,// 每页显示的记录数
    pageNo: 1,// 页码
    mapping: null,// 该插件要求后台返回的数据包括  currentPage  pageSize  total   如果用户的数据结构不是这样的,可以通过此属性配置映射关系
	initComplete: null // 用户可以配置一个在dom初始化完成后执行的函数
}) // 此初始化返回一个page对象,调用该page对象可以刷新数据,携带查询参数,更改url地址和处理数据的方法

pageObj.reload({
        url: 'xx',   // 在reload的配置中传入url,则分页器会以这个新的url来请求后台
        name: 'xx',// 一些用户自定义的参数
        age: 'xx'
    }, function(data){
        // 这个作为reload方法的第二个参数是个函数,若有此参数,则分页器会以这个方法作为处理数据的方法
})
```
![1.png](https://github.com/lqxsunhan123/jquery-page/blob/master/page/img/1.jpg "1.png")<br />
![2.png](https://github.com/lqxsunhan123/jquery-page/blob/master/page/img/2.jpg "2.png")