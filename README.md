这是一款类似ping命令的小工具，用来测试链路暂态带宽近似工具。

usage:<br>
		-h: help, display speedy help information.<br>
		
  As client:<br>
    -cip:port<br>
		  ip:(default=127.0.0.1)<br>
		  port:(default=55555)<br>
		-n:thread number(default=1)<br>
		-l:blk size(default=1024)<br>
		-m:short linked module(1:进入短链接模式,默认是0,长连接模式.)<br>
		-r:random seconds(单链接模式下,随机发起连接的最大时间间隔n.)<br>
		-t:fix seconds(单链接模式下,n秒发送一条探测消息.)<br>
		 -r 与 -t互斥.<br>
		 
	such as:
	speedy -c[ip:port] [-n2 -l1024]
	speedy -c[ip:port] [-m1 -l10240 -r5]
	
  As server:
		-sport:(default=55555)
		-t:sample time(长连接模式下使用default=1 second)
		-m:short linked module(1:进入短链接模式,默认是0,长连接模式.)
		
	such as:
	speedy -s[port][ -t1]
	speedy -s[port][ -t1][-m1]

display：<br>

  client端：<br>
  ./speedy -c103.7.220.122:55555 -m1 -l512 -t1<br>
  option c:'103.7.220.122:55555'<br>
  103.7.220.122, 55555<br>
  option l:'512'<br>
  option t:'1'<br>
  ======= Client Single Module ========<br>
  sdtm: 1435800360.476238, rvtm: 1435800360.477045, subtm: 0.000807<br>
  sdtm: 1435800361.478122, rvtm: 1435800361.478926, subtm: 0.000804<br>

  server端：<br>
  Pthread 1205675776 is Running!<br>
  1435800410.518684 Recv: 7300 bytes<br>
  1435800410.518698 Send: 7300 bytes<br>
  1435800410.518719 Recv: 2940 bytes<br>
  1435800410.518728 Send: 2940 bytes<br>
  Pthread 1195185920 is Running!<br>
  1435800411.520601 Recv: 7300 bytes<br>
  1435800411.520618 Send: 7300 bytes<br>
  1435800411.520631 Recv: 2940 bytes<br>
  1435800411.520639 Send: 2940 bytes<br>


output：<br>
  时间      链路建立耗时  暂态带宽  测试包长度<br>
  20150702092649,0.000792s,18.54M,10240<br>
  20150702092650,0.000795s,18.63M,10240<br>
  20150702092651,0.000798s,18.34M,10240<br>
  20150702092652,0.000803s,18.54M,10240<br>
  20150702092653,0.000796s,20.89M,10240<br>
  20150702092654,0.000800s,18.63M,10240<br>
  20150702092655,0.000798s,18.28M,10240<br>
