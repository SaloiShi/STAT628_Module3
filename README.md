# STAT628_Module3

## 四个任务：
1 是否取消：二分类，输出取消概率。
2 出发延误时长：预测分钟数，允许负值表示提前。
3 到达延误时长：预测分钟数，允许负值表示提前。
4 滑行是否异常长：可以做二分类，先定义“异常长”的标准；反映滑行风险。

## 选取数据：
2023 年 9–12 月；
2024 年 9–12 月；
2025 年 9–11 月。
至少使用两个年份，必须包括 2025 年。条件允许，可以保留全部指定月份。
选至少 10 个不同城市，至少两家公司，优先选择在所选机场之间都有较多航班、且部分航线重叠的公司。
【WN AA DL UA 始发city前十 三年所有数据,去除diverted为1的数据】
23-24同月份合并
9-11baseline
23 24的12作为模型调整验证

## 数据清洗：
检查重复记录、机场和航空公司代码、计划日期时间等；加入机场时区和海拔，并标准化时间（处理 UTC、跨日及夏令时）。

## Main Purpose
- whether their flight will be canceled
- whether their flight will depart on-time and, if not, the length of the departure delay (which may be negative for early departure)
- whether their flight will arrive on-time and, if not, the length of the arrival delay (which may be negative for early arrival)
- whether taxi-out or taxi-in is a big factor in departure or arrival delay
- the associated uncertainty for each prediction.

## Focus on...
- If the center (airport) of the airline affect the delay time?（影响delay time的因素）
- 不同航司之间航班执行效率差异，影响因素（重点关注航司总部城市的机场）
- 出发和到达延误呈现怎样的规律（年份、季节、工作日与休息日因素）？

- day of week
- flight date
- reporting airline
- originAirportID
- Origin origincityname
- dest destcityname
- Depdelay
- taxiout
- taxiin
- Arrdelay
- cancelled
- cancellationcode
- AirTime
- ActualElapsedTime CRSElapsedTime
- DistanceGroup
- CarrierDelay WeatherDelay NASDelay SecurityDelay LateAircraftDelay TotalAddGTime
