1.项目介绍
    这是 用django框架,能实现简单的网上商城,他的功能包括.登录注册.各类商品的展示,以及对应的详情页展示.能够实现加入购物车和立即购买.生成订单表.
2.用到的知识点.
    django 的MVT之间的关系.以及各个之间调用关系
    数据库是mysql
    前端用的是:部分页面是js,部分是jq.

这是第一个python初学者的项目,只是实现了基本功能,代码在健壮性,简洁性上没有太多考虑.



存在的bug 
    1.立即购买后,不提加订单,继续添加商品到购物车.会存在修改订单页面数据问题!
    刚开始的时候生成订单页面上的数据是根据购物车表中的一个字段生成的.就会存在一个问题
     立即购买商品后,会在购物车列表中生成购买商品的信息,但是一个 isSettle 字段会变成true
     通过这个字段来判断这个人购买的.但是这时候会有一个问题.假如他不付款.再次加入购物车.这时候数据就会修改购物车表中的商品数据.同样订单页面展示也会出问题.
     初步解决:在增加商品时,判断这个商品是否被提交了,如果被提交了,就从新创建一个一条数据库.存入.
2016 11.8
