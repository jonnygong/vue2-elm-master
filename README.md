
__注：此项目纯属个人瞎搞，正常下单请选择饿了么官方客户端。__


## 技术栈

vue2 + vuex + vue-router + webpack + ES6/7 + fetch + sass + flex + svg


## 项目运行

#### 注意：由于涉及大量的 ES6/7 等新属性，nodejs 必须是 6.0 以上版本 ，node 7 是先行版，有可能会出问题，建议使用 node 6 稳定版

```
git clone https://github.com/jonnygong/vue2-elm-master

```


# 目标功能
- [x] 定位功能 -- 完成
- [x] 选择城市 -- 完成
- [x] 搜索地址 -- 完成
- [x] 展示所选地址附近商家列表 -- 完成
- [x] 搜索美食，餐馆 -- 完成
- [x] 根据距离、销量、评分、特色菜、配送方式等进行排序和筛选 -- 完成
- [x] 餐馆食品列表页 -- 完成
- [x] 购物车功能 -- 完成
- [x] 店铺评价页面 -- 完成
- [x] 单个食品详情页面 -- 完成
- [x] 商家详情页 -- 完成
- [x] 登录、注册 -- 完成
- [x] 修改密码 -- 完成
- [x] 个人中心 -- 完成
- [x] 发送短信、语音验证 -- 完成
- [x] 下单功能 -- 完成 ✨✨🎉🎉
- [x] 订单列表 -- 完成
- [x] 订单详情 -- 完成
- [x] 下载App -- 完成
- [x] 添加、删除、修改收货地址 -- 完成
- [x] 帐户信息 -- 完成
- [x] 服务中心 -- 完成
- [x] 红包 -- 完成
- [x] 上传头像 -- 完成
- [ ] 付款 -- 未完成



# 总结

1、因为并不是elm官方，而且因为要开代理，必须在pc端打开，最多只能做到下单这一步，下单成功后可以在手机客户端查看并付款。

2、一般涉及到money的网页逻辑都比较复杂，尤其像饿了么这样一个开放的平台，商家和食品种类繁多，页面与页面之间交互复杂，在写到 购物车 和 下单 功能时众多的数据和逻辑一度让人很头疼，又没有设计和接口api文档，只能一步步摸索。

3、vue因其轻量级的框架在中小型项目中表现亮眼，在大型单页面应用中因为vuex的存在，表现依然出色，在处理复杂交互逻辑的时候，vuex的存在是不可或缺的。所以说利用 vue + vuex 完全可以去做大型的单页面项目。



# 项目布局

```
.
├── build                                       // webpack配置文件
├── config                                      // 项目打包路径
├── elm                                         // 上线项目文件，放在服务器即可正常访问
├── screenshots                                 // 项目截图
├── src                                         // 源码目录
│   ├── components                              // 组件
│   │   ├── common                              // 公共组件
│   │   │   ├── alertTip.vue                    // 弹出框组件
│   │   │   ├── buyCart.vue                     // 购物车组件
│   │   │   ├── computeTime.vue                 // 倒计时组件
│   │   │   ├── loading.vue                     // 页面初始化加载数据的动画组件
│   │   │   ├── mixin.js                        // 组件混合(包括：指令-下拉加载更多，处理图片地址)
│   │   │   ├── ratingStar.vue                  // 评论的五颗星组件
│   │   │   └── shoplist.vue                    // msite和shop页面的餐馆列表公共组件
│   │   ├── footer
│   │   │   └── footGuide.vue                   // 底部公共组件
│   │   └── header
│   │       └── head.vue                        // 头部公共组件
│   ├── config                                  // 基本配置
│   │   ├── env.js                              // 环境切换配置
│   │   ├── fetch.js                            // 获取数据
│   │   ├── mUtils.js                           // 常用的js方法
│   │   └── rem.js                              // px转换rem
│   ├── images                                  // 公共图片
│   ├── page
│   │   ├── balance
│   │   │   ├── balance.vue                     // 余额页
│   │   │   └── children
│   │   │       └── detail.vue                  // 余额说明
│   │   ├── benefit
│   │   │   ├── benefit.vue                     // 红包页
│   │   │   └── children
│   │   │       ├── commend.vue                 // 推荐有奖
│   │   │       ├── coupon.vue                  // 代金券说明
│   │   │       ├── exchange.vue                // 兑换红包
│   │   │       ├── hbDescription.vue           // 红包说明
│   │   │       └── hbHistory.vue               // 历史红包
│   │   ├── city                 
│   │   │   └── city.vue                        // 当前城市页
│   │   ├── confirmOrder
│   │   │   ├── children
│   │   │   │   ├── children
│   │   │   │   │   ├── addAddress.vue          // 添加地址页
│   │   │   │   │   └── children
│   │   │   │   │       └── searchAddress.vue   // 搜索地址页
│   │   │   │   ├── chooseAddress.vue           // 选择地址页
│   │   │   │   ├── invoice.vue                 // 选择发票页
│   │   │   │   ├── payment.vue                 // 付款页
│   │   │   │   ├── remark.vue                  // 订单备注页
│   │   │   │   └── userValidation.vue          // 用户验证页
│   │   │   └── confirmOrder.vue                // 确认订单页
│   │   ├── download
│   │   │   └── download.vue                    // 下载App
│   │   ├── find
│   │   │   └── find.vue                        // 发现页
│   │   ├── food
│   │   │   └── food.vue                        // 食品筛选排序页
│   │   ├── forget
│   │   │   └── forget.vue                      // 忘记密码，修改密码页
│   │   ├── home
│   │   │   └── home.vue                        // 首页
│   │   ├── login
│   │   │   └── login.vue                       // 登录注册页
│   │   ├── msite
│   │   │   └── msite.vue                       // 商铺列表页
│   │   ├── order
│   │   │   ├── children
│   │   │   │   └── orderDetail.vue             // 订单详情页
│   │   │   └── order.vue                       // 订单列表页
│   │   ├── points
│   │   │   ├── children
│   │   │   │   └── detail.vue                  // 积分说明
│   │   │   └── points.vue                      // 积分页
│   │   ├── profile
│   │   │   ├── children
│   │   │   │   ├── children
│   │   │   │   │   ├── address.vue             // 添加地址
│   │   │   │   │   └── children
│   │   │   │   │       ├── add.vue             // 新增地址
│   │   │   │   │       └── children
│   │   │   │   │           └── addDetail.vue   // 搜索地址
│   │   │   │   ├── info.vue                    // 帐户信息
│   │   │   │   └── setusername.vue             // 重置用户名
│   │   │   └── profile.vue                     // 个人中心
│   │   ├── search
│   │   │   └── search.vue                      // 搜索页
│   │   ├── service
│   │   │   ├── children
│   │   │   │   └── questionDetail.vue          // 问题详情
│   │   │   └── service.vue                     // 服务中心
│   │   ├── shop
│   │   │   ├── children
│   │   │   │   ├── children
│   │   │   │   │   └── shopSafe.vue            // 商铺认证信息页
│   │   │   │   ├── foodDetail.vue              // 商铺信息页
│   │   │   │   └── shopDetail.vue              // 单个商铺信息页
│   │   │   └── shop.vue                        // 商铺筛选页
│   │   └── vipcard
│   │       ├── children
│   │       │   ├── invoiceRecord.vue           // 购买记录
│   │       │   ├── useCart.vue                 // 使用卡号购买
│   │       │   └── vipDescription.vue          // 会员说明
│   │       └── vipcard.vue                     // 会员卡办理页
│   ├── plugins                                 // 引用的插件
│   ├── router
│   │   └── router.js                           // 路由配置
│   ├── service                                 // 数据交互统一调配
│   │   ├── getData.js                          // 获取数据的统一调配文件，对接口进行统一管理
│   │   └── tempdata                            // 开发阶段的临时数据
│   ├── store                                   // vuex的状态管理
│   │   ├── action.js                           // 配置actions
│   │   ├── getters.js                          // 配置getters
│   │   ├── index.js                            // 引用vuex，创建store
│   │   ├── modules                             // store模块
│   │   ├── mutation-types.js                   // 定义常量muations名
│   │   └── mutations.js                        // 配置mutations
│   └── style
│       ├── common.scss                         // 公共样式文件
│       ├── mixin.scss                          // 样式配置文件
│       └── swiper.min.css
│   ├── App.vue                                 // 页面入口文件
│   ├── main.js                                 // 程序入口文件，加载各种公共组件
├── favicon.ico                                 // 图标
├── index.html                                  // 入口html文件
.

56 directories, 203 files
```
