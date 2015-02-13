---

layout: doc

title: Hybrid framework

description: 本文介绍了WHF framework的API。
category: doc

---

![Mou icon](/images/Mou_128.png)


```Time:2013-12-25 version:1.0```


####1.1	酒店模块1.1.1	国内酒店查询页(5.3新增)
页面名 hotel_ inquire


参数名				| 	参数含义---------- 			| 	---------c1(checkInDate)		|	入住时间（必需，格式YYYYMMDD）c2(checkOutDate)	|	离店时间（必需，格式YYYYMMDD）c3(cityId)			|	酒店城市ID (必需)c4(districtId)		|	景区ID (可选)c5(brandId)			|	品牌ID (可选)c6(brandName)		|	品牌名称 (可选)c7(brandType)		|	品牌类型(可选，0：全部品牌，1：经济型连锁品牌，默认0)URL					|	ctrip://wireless/hotel_inquire?c1=20131217&c2=20131218&c3=2&c4=0&c5=25&c6=君悦&c7=0


1.1.2 国内酒店列表页(5.3新增)

页面入口名称：hotel_inland_list

参数名				| 	参数含义---------- 			| 	---------c1(checkInDate)		|	入住时间（必需，格式YYYYMMDD）c2(checkOutDate)	|	离店时间（必需，格式YYYYMMDD）c3(cityId)			|	酒店城市ID (必需)c4(districtId)		|	景区城市ID (可选)c5(hotelType)		|	酒店类型(0：国内，1：海外) (预留，目前没有海外)c6(brandId)			|	品牌ID (可选)c7(brandName)		|	品牌名称 (可选)c8(brandType)		|	品牌类型(可选，0：全部品牌，1：经济型连锁品牌，默认0)URL					|	ctrip://wireless/hotel_inland_list?c1=20131217&c2=20131218&c3=2&c4=0&c5=0& c6=25&c7=君悦&c8=0


1.1.3 团购酒店列表页(5.3新增)

页面入口名称：hotel_groupon_list

参数名				| 	参数含义---------- 			| 	---------c1(cityId)			|	酒店城市ID (必需)URL					|	ctrip://wireless/hotel_groupon_list?c1=2

1.1.4	国际酒店详情页

页面入口名称：OverseaHotel

参数名				| 	参数含义---------- 			| 	---------checkInDate			| 	入住时间（必需，格式YYYYMMDD）checkOutDate		| 	退房时间（必需，格式YYYYMMDD）hotelId				| 	酒店ID (必需)cityId				| 	酒店城市ID (必需)
URL					|	ctrip://wireless/OverseaHotel?hotelId=123&cityId=2&checkinDate=20131108&checkoutDate=20131118

1.1.5 国内酒店详情页(5.3更新)

页面入口名称：InlandHotel参数名				| 	参数含义---------- 			| 	---------(checkInDate)		| 	入住时间（必需，格式YYYYMMDD）(checkOutDate)		| 	退房时间（必需，格式YYYYMMDD）(hotelId)			| 	酒店ID(cityId)			| 	城市ID
URL					|	ctrip://wireless/InlandHotel?checkInDate =20131217&checkOutDate=20131218&hotelId =422809&cityId=21.1.6	团购酒店详情页(5.3新增)页面入口名称：hotel_groupon_detail
参数名				| 	参数含义---------- 			| 	---------c1(productID)		|	产品ID（必需）
URL					|	ctrip://wireless/hotel_groupon_detail?c1=1234561.1.7	常规酒店订单详情页
页面入口名称：NormalHotelOrder参数名				| 	参数含义---------- 			| 	---------orderId				| 	订单ID（必需）hotelType			| 	酒店类型（必需，酒店类型： 0 = 普通酒店;  1 = 惠选酒店）URL					| 	ctrip://wireless/NormalHotelOrder?&orderId=123&hotelType=2
1.1.8	海外酒店订单详情页页面入口名称：OverseaHotelOrder参数名				| 	参数含义---------- 			| 	---------orderId				| 	订单ID（必需）举例：				| 	ctrip://wireless/OverseaHotelOrder?&orderId=123
1.1.9	团购酒店订单详情页页面入口名称：GrouponHotelOrder参数名				| 	参数含义---------- 			| 	---------orderId				| 	团购订单ID（必需）举例：				| 	ctrip://wireless/GrouponHotelOrder?orderId =123
1.1.10	酒店点评提交页页面入口名称：HotelCommentSubmit参数名				| 	参数含义---------- 			| 	---------hotelId				| 	酒店ID（必需）orderId				| 	订单ID（必需）hotelName			| 	酒店名称（必需）举例：				| 	ctrip://wireless/HotelCommentSubmit?orderId=123&orderId=456&hotelName=
####1.2	机票模块1.2.1	国内机票订单详情页
页面入口名称：InlandFlightOrder参数名				| 	参数含义---------- 			| 	---------orderId				| 	订单ID（必需）举例：				| 	ctrip://wireless/InlandFlightOrder?orderId=123
1.2.2	国际机票订单详情页
页面入口名称：InternationalFlightOrder参数名				| 	参数含义---------- 			| 	---------orderId				| 	订单ID（必需）orderType			| 	机票类型（必需，0：单程，1：单往返，2：多程）举例：				| 	ctrip://wireless/InternationalFlightOrder?&orderId=1231.2.3	值机(国际机票订单详情跳值机页面) ( 5.3不转H5)
页面入口名称：flight_seat_list参数名				| 	参数含义---------- 			| 	---------	举例：				| 	ctrip://wireless/flight_seat_list注：					| 	无需参数，但是需要userID，app能获取到1.2.4	国内/国际机票查询页(5.3新增)
页面入口名称： flight_ inquire参数名				| 	参数含义---------- 			| 	---------c1(SearchType)		| 	查询类型（1国内；2国际）（可选）     删除c1(tripType)		| 	单程/往返( 1/2 )（可选）c2(departCityId)	| 	出发城市id （可选）c3(arriveCityId)	| 	到达城市id（可选）c4(departDate)		| 	出发时间（yyyymmdd）（可选）c5(returnDate)		| 	返程出发时间（yyyymmdd）（可选）c6(intlPassengerType)	| 	国际乘客类型，成人/儿童（1/2）（预留）c7(classType)		| 	仓位（可选）1：经济舱  2：超级经济舱3：公务舱4：头等舱 5：公务/头等舱举例单程：			| 	ctrip://wireless/flight_ inquire?c1=1&c2=1&c3=2&c4=20131125举例往返：			| 	ctrip://wireless/flight_ inquire?c1=2&c2=1&c3=2&c4=20131125&c5=20131225
1.2.5	国内 单程/往返去程 机票列表页(5.3新增)
页面入口名称：flight_inland_singlelist / flight_inland_tolist参数名				| 	参数含义---------- 			| 	---------c1(tripType)		| 	单程/往返(1/2)（必需）c2(departCityId)	| 	出发城市id （必需）c3(arriveCityId)	| 	到达城市id（必需）c4(departDate)		| 	出发时间（yyyymmdd）（必需）c5(returnDate)		| 	返程出发时间（yyyymmdd）（必需）c6(classType)		| 	筛选舱位（可选）1：经济舱  5：公务/头等舱c7(sortType)		| 	排序类型（预留）1:起飞时间升序 2:起飞时间降序 3:价格升序 4：价格降序c8(airportCode)		| 	筛选出发/到达（预留）格式：departFilterAirportCode|arriveFilterAirportCode 通过竖线区分筛选的是出发还是到达机场。c9(timeInterval)	| 	筛选起飞时间（预留）格式：0600|1200c10(craftType)		| 	筛选机型（预留）1大型机 2 中型机 3 小型机c11(airline)		| 	筛选航司（预留）航空公司二字码举例单程：			| 	ctrip://wireless/ flight_inland_singlelist?c1=1&c2=1&c3=2&c4=20131125&c5=1&c6=1&c 7=|SHA&c8=0600|1200&c9=1&c10=MU<br/>ctrip://wireless/flight_inland_tolist?c1=1&c2=1&c3=2&c4=20131125&c5=1&c6=1&c 7=|SHA&c8=0600|1200&c9=1&c10=MU举例往返：			| 	ctrip://wireless/flight_inland_singlelist?c1=2&c2=1& c3=2&c4=20131125&c5=20131225&c6=1&c7=1&c8=|SHA&c9=0600|1200&c10 =1&c11=MU<br/>ctrip://wireless/flight_inland_tolist?c1=2&c2=1& c3=2&c4=20131125&c5=20131225&c6=1&c7=1&c8=|SHA&c9=0600|1200&c10 =1&c11=MU1.2.6	国际 单程/往返去程 机票列表页(5.3新增)
页面入口名称：flight_int_singlelist / flight_int_tolist参数名				| 	参数含义---------- 			| 	---------c1(tripType)		| 	单程/往返( 1/2 )（必需）c2(departCityId)	| 	出发城市id （必需）c3(arriveCityId)	| 	到达城市id（必需）c4(departDate)		| 	出发时间（yyyymmdd）（必需）c5(returnDate)		| 	返程出发时间（yyyymmdd）（必需）c6(intlPassengerType)	| 	国际乘客类型，成人/儿童（1/2）（预留，默认成人）c7(classType)		| 	仓位（可选）1：经济舱  2：超级经济舱3：公务舱4：头等舱c8(sortType)		| 	排序类型（预留）1:起飞时间升序 2:起飞时间降序 3:价格升序 4：价格降序 5:耗时升序6:耗时降序c9(airline)			| 	筛选航司（预留）航空公司二字码举例单程：			| 	ctrip://wireless/flight_int_singlelist?c1=1&c2=1&c3=58&c4=20131125&c5=1&c6=MU<br/>ctrip://wireless/flight_int_tolist?c1=1&c2=1&c3=58&c4=20131125&c5=1&c6=MU举例往返：			|	ctrip://wireless/flight_int_singlelist?c1=2&c2=1& c3=58&c4=20131125&c5=20131225&c6=2&c7=MU<br/>ctrip://wireless/flight_int_tolist?c1=2&c2=1& c3=58&c4=20131125&c5=20131225&c6=2&c7=MU####1.3	火车模块
1.3.1	火车订单详情页页面入口名称：TrainOrder
参数名				| 	参数含义---------- 			| 	---------orderId				| 	订单ID（必需）举例：				| 	ctrip://wireless/TrainOrder?orderId=1231.3.2	继续支付(火车订单详情页) ( 5.3不转H5)
页面入口名称：widget_pay_main参数名				| 	参数含义---------- 			| 	---------c1(orderId)			| 	订单ID（必需）c2(orderType)		| 	订单类型（必需，0：火车票，目前只有火车票）举例：				| 	ctrip://wireless/widget_pay_main?c1=123456&c2=0####1.4	旅游模块
1.4.1	自由行订单详情页页面入口名称：VacationOrder参数名				| 	参数含义---------- 			| 	---------orderId				| 	订单ID（必需）举例：				| 	ctrip://wireless/VacationOrder?orderId=123
1.4.2	查看地图( 5.3不转H5)
页面入口名称：vacation_tour_orderdetailmap参数名				| 	参数含义---------- 			| 	---------C1(hotelName)		| 	酒店名称（必需）C2(latitude)		| 	纬度（必需）C3(longitude)		| 	经度（必需）举例：				| 	ctrip://wireless/vacation_tour_orderdetailmap?c1=上海锦江之星&c2=31.256565&c3=121.565789
####1.5	门票模块
1.5.1	门票订单详情页页面入口名称：TicketOrder参数名				| 	参数含义---------- 			| 	---------orderId				| 	订单ID（必需）举例：				| 	ctrip://wireless/TicketOrder?&orderId=123####1.6	全局模块1.6.1	营销渠道统计
参数名				| 	参数含义---------- 			| 	---------extendSourceID		| 	营销渠道的渠道号，String类型
举例：				| 	ctrip://wireless/TicketOrder?& extendSourceID=8892说明：				| 	该参数是业务无关的，