这是一款类似ping命令的小工具，用来测试链路暂态带宽近似工具。

usage:
		-h: help, display speedy help information.
as client:
		-cip:port
		  ip:(default=127.0.0.1)
		  port:(default=55555)
		-n:thread number(default=1)
		-l:blk size(default=1024)
		-m:short linked module(1:进入短链接模式,默认是0,长连接模式.)
		-r:random seconds(单链接模式下,随机发起连接的最大时间间隔n.).
		-t:fix seconds(单链接模式下,n秒发送一条探测消息.).
		 -r 与 -t互斥.
	举例:
	speedy -c[ip:port] [-n2 -l1024]
	speedy -c[ip:port] [-m1 -l10240 -r5]
as server:
		-sport:(default=55555)
		-t:sample time(长连接模式下使用default=1 second)
		-m:short linked module(1:进入短链接模式,默认是0,长连接模式.)
		-h: help, display speedy useage
	举例:
	speedy -s[port][ -t1]
	speedy -s[port][ -t1][-m1]

display：
client端：
./speedy -c103.7.220.122:55555 -m1 -l512 -t1
option c:'103.7.220.122:55555'
103.7.220.122, 55555
option l:'512'
option t:'1'
======= Client Single Module ========
sdtm: 1435800360.476238, rvtm: 1435800360.477045, subtm: 0.000807
sdtm: 1435800361.478122, rvtm: 1435800361.478926, subtm: 0.000804

server端：
Pthread 1205675776 is Running!
1435800410.518684 Recv: 7300 bytes
1435800410.518698 Send: 7300 bytes
1435800410.518719 Recv: 2940 bytes
1435800410.518728 Send: 2940 bytes
Pthread 1195185920 is Running!
1435800411.520601 Recv: 7300 bytes
1435800411.520618 Send: 7300 bytes
1435800411.520631 Recv: 2940 bytes
1435800411.520639 Send: 2940 bytes


output：
时间      链路建立耗时  暂态带宽  测试包长度
20150702092649,0.000792s,18.54M,10240
20150702092650,0.000795s,18.63M,10240
20150702092651,0.000798s,18.34M,10240
20150702092652,0.000803s,18.54M,10240
20150702092653,0.000796s,20.89M,10240
20150702092654,0.000800s,18.63M,10240
20150702092655,0.000798s,18.28M,10240
