ts.get_hist_data('600848')

获取全部日线数据, 实际2013/07/08开始到现在的
http://api.finance.ifeng.com/akdaily/?code=sh600848&type=last

ts.get_hist_data('600848',start='2015-01-05',end='2015-01-09')

获取指定日期数据, 实际还是获取全部数据然后本地过滤的

http://api.finance.ifeng.com/akdaily/?code=sh600848&type=last



ts.get_hist_data('600848', ktype='W')

获取全部周K线数据, 注意URL的地址不同
http://api.finance.ifeng.com/akweekly/?code=sh600848&type=last

ts.get_hist_data('600848', ktype='5')

获取全部5分钟K线数据
http://api.finance.ifeng.com/akmin?scode=sh600848&type=5

ts.get_hist_data('600848', ktype='30')

获取全部30分钟K线数据

http://api.finance.ifeng.com/akmin?scode=sh600848&type=30

ts.get_hist_data('sh')

获取上证指数日K线数据

http://api.finance.ifeng.com/akdaily/?code=sh000001&type=last


df = ts.get_stock_basics()

从指定IP地址获取一个股票数据信息的all.csv文件

http://218.244.146.57/static/all.csv



ts.get_h_data('002337')#前复权ts.get_h_data('002337',autype='hfq')#后复权ts.get_h_data('002337',autype=None)#不复权ts.get_h_data('002337',start='2015-01-01',end='2015-03-16')#两个日期之间的前复权数据ts.get_h_data('399106',index=True)#深圳综合指数

获取复权历史数据，默认情况下会从最近时间往前按照每个季度逐一读取数据

例如下面的URL，代表读取2016年第三季度的复权数据
http://vip.stock.finance.sina.com.cn/corp/go.php/vMS_FuQuanMarketHistory/stockid/002337.phtml?year=2016&jidu=3
ts.get_today_all()
一次性获取当前交易所有股票的行情数据（如果是节假日，即为上一交易日，结果显示速度取决于网速）

http://vip.stock.finance.sina.com.cn/quotes_service/api/json_v2.php/Market_Center.getHQNodeData?num=80&sort=changepercent&asc=0&node=hs_a&symbol=&_s_r_a=page&page=1

df = ts.get_tick_data('600848',date='2014-01-09')

获取指定日期的历史分笔数据, 实际是一个xls文件
http://market.finance.sina.com.cn/downxls.php?date=2014-01-09&symbol=sh600848
df=ts.get_realtime_quotes('000581')
获取实时分笔数据, 下面rn实际是一个random的随机值
http://hq.sinajs.cn/rn=5028490283381&list=sz000581

df = ts.get_today_ticks('601333')

获取当天分笔数据，实际下面是返回每5分钟的分笔页面而已
http://vip.stock.finance.sina.com.cn/quotes_service/api/json_v2.php/CN_Transactions.getAllPageTime?date=2016-07-06&symbol=sh601333
这里才是获取每5分钟的分笔数据信息
http://vip.stock.finance.sina.com.cn/quotes_service/view/vMS_tradedetail.php?symbol=sh601333&date=2016-07-06&page=1

http://vip.stock.finance.sina.com.cn/quotes_service/view/vMS_tradedetail.php?symbol=sh601333&date=2016-07-06&page=2

Yahoo财经A股日线数据

雅虎财经网站提供股票日历史数据下载接口。
直接在浏览器地址中数据网址即可 http://table.finance.yahoo.com/table.csv?s=股票代码。上证股票是股票代码后面加上.ss，深证股票是股票代码后面加上.sz。例如查询中国石油的历史数据，直接在浏览器中输入：http://table.finance.yahoo.com/table.csv?s=601857.ss
深市数据链接：http://table.finance.yahoo.com/table.csv?s=000001.sz 上市数据链接：http://table.finance.yahoo.com/table.csv?s=600000.ss
另外，上证综指代码：000001.ss，深证成指代码：399001.SZ，沪深300代码：000300.ss
字段格式

Date Open High Low Close Volume Adj Close 分别是：日期、开盘价、最高价、最低价、收盘价、成交量、复权收盘价 
获取指定时间范围的数据

【例子】 取 2012年1月1日 至 2012年4月19日的数据 http://table.finance.yahoo.com/table.csv?a=0&b=1&c=2012&d=3&e=19&f=2012&s=600000.ss

