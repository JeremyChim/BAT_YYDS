# BAT_YYDS



# grep 打印后几行

```bash
adb shell
ifconfig | grep -A 7 "rmnet_data0"
```

# ping 10下百度

```bash
adb shell
ping www.baidu.com -w 10
```

# 匹配最后3次

```bash
adb shell
cat /sdcard/log/bdlog/bdLog | grep "testEcallNum" | tail -3
```

# 重定向输出

```bash
echo %date% %time% >> data.log
```

# 重定向输入

```bash
adb shell < airplane_mode_off.txt
```

```textile
ql_sdk_api_test
11
0
14
1

```

# 输入

```bash
set /p a=请输入数字：
echo 输入的数字是：%a%
```

# 变量

```bash
set a=100
echo %a%
```

# 菜单1

```bash
@echo off

title menu
mode con: cols=50 lines=30

:menu

cls
echo author : Jer
echo date : 2023-7-15
echo version : v3.0
echo.

echo 0	monitor
echo 1	pull_log
echo 2	auto_call
echo 3	manual_call
echo 4	update_num
echo 5	tailf_bdLog
echo 6	airplane_mode_on
echo 7	airplane_mode_off
echo 8	reboot
echo 9	sound
echo 10	cat_network
echo 11	ql_sdk_api_test
echo 12	cat_iccid
echo 13	tailf_dislog
echo 14	debug
echo 15	cat_bdLog
echo 16	start_log.sh
echo 17	done_log.sh.bat
echo 18	grep_signa
echo 19	grep_eu_ecall
echo 20	grep_gnss
echo 21	grep_monitor
echo 22	grep_logread
echo -1	exit
echo.

set /p a= ...... 

if %a%== -1		exit
if %a%== 0		goto monitor
if %a%== 1		start pull_log.bat
if %a%== 2		start auto_call.bat
if %a%== 3		start manual_call.bat
if %a%== 4		start update_num.bat
if %a%== 5		start tailf_bdLog.bat
if %a%== 6		start airplane_mode_on.bat
if %a%== 7		start airplane_mode_off.bat
if %a%== 8		start reboot.bat
if %a%== 9		start sound.bat
if %a%== 10		start cat_network.bat
if %a%== 11		start ql_sdk_api_test.bat
if %a%== 12		start cat_iccid.bat
if %a%== 13		start tailf_dislog.bat
if %a%== 14		start debug.bat
if %a%== 15		start cat_bdLog.bat
if %a%== 16		start start_log.sh.bat
if %a%== 17		start done_log.sh.bat
if %a%== 18		start grep_signa.bat
if %a%== 19		start grep_eu_ecall.bat
if %a%== 20		start grep_gnss.bat
if %a%== 21		start grep_monitor.bat
if %a%== 22		start grep_logread.bat


pause
goto menu

:monitor
start info.bat
start ps.bat
start ccmni.bat
goto menu
```

# 菜单2

```bash
@echo on
:menu
@mode con: cols=120 lines=55
@cmd < txt/color_code.txt
@CLS
@title 7B120——4GTBOX测试脚本——Jer小铭
@echo -----------欢迎使用4GTBOX测试脚本-----------
@echo ---------------作者：Jer小铭----------------
@echo --------------脚本版本：v3.7----------------
@echo.
@echo 当前日期：%date:~0,4%年%date:~5,2%月%date:~8,2%日
@echo 当前时间：%time:~0,2%时%time:~3,2%分%time:~6,2%秒
@echo 记录点：%date:~0,4%.%date:~5,2%.%date:~8,2%-%time:~0,2%:%time:~3,2%:%time:~6,2%
@echo.
@echo ==========TBOX软件版本（oemapp/tbox-version）==========
@echo.
@adb shell cat oemapp/tbox-version
@echo.
@echo ==========功能菜单==========
@echo.
@echo  1、进入ADB Shell					 2、日志功能
@echo  3、网络功能						 4、OTA功能  
@echo  5、查xcall号码						 6、查vin
@echo  7、查iccid						 8、查sn  
@echo  9、查版本						10、查配置文件 
@echo 11、写入vin						12、写入ecall号码（手动）
@echo 13、写入ecall号码（自动）				14、写入icall号码
@echo 15、写入xcall号码（所有xcall号码）			16、写入sn码 
@echo 17、查productkey					18、查devicesecret
@echo 19、写入productkey					20、写入devicesecret 
@echo 21、查设备tsp登录信息					22、打开设备管理器 
@echo 23、软件版本查询（自动刷新脚本）			24、证书状态查询和切换（硬PKI和软证书）
@echo 25、运行hal进程监测脚本					26、切换脚本背景色和文字色
@echo 27、ARP监测脚本（自动刷新脚本）				28、清除productkey 
@echo 29、清除devicesecret					30、清除sn 
@echo 31、清除vin											
@echo 32、导入私钥  client.key（client.key放在脚本根目录）
@echo 33、导入公钥  client.pub（client.pub放在脚本根目录）  
@echo 34、导入Tbox证书  TBOX.crt（TBOX.crt放在脚本根目录）
@echo 35、导入Tbox证书  OTA.crt（OTA.crt放在脚本根目录）	
@echo 36、运行进程监测脚本
@echo 37、查看GPS信息更新									
@echo 0、刷新 
@echo.
@set /p a=请输入选项：
@if %a%==1 goto shell
@if %a%==2 goto log
@if %a%==3 goto network
@if %a%==4 goto ota
@if %a%==5 goto cat_xcall
@if %a%==6 goto cat_vin
@if %a%==7 goto cat_iccid
@if %a%==8 goto cat_sn
@if %a%==9 goto cat_ver
@if %a%==10 goto cat_7B120
@if %a%==11 goto send_vin
@if %a%==12 goto send_ecall
@if %a%==13 goto send_autoecall
@if %a%==14 goto send_icall
@if %a%==15 goto send_xcall
@if %a%==16 goto send_sn
@if %a%==17 goto cat_productkey
@if %a%==18 goto cat_devicesecret
@if %a%==19 goto send_productkey
@if %a%==20 goto send_devicesecret
@if %a%==21 goto cat_tspinfo
@if %a%==22 goto open_devmgmt
@if %a%==23 goto ver_du
@if %a%==24 goto http_addr_type
@if %a%==25 goto grep_hal
@if %a%==26 goto color_change
@if %a%==27 goto cat_arp
@if %a%==28 goto send_productkey000
@if %a%==29 goto send_devicesecret000
@if %a%==30 goto send_sn000
@if %a%==31 goto send_vin000
@if %a%==32 goto push_client_key
@if %a%==33 goto push_client_pub
@if %a%==34 goto push_tbox_crt
@if %a%==35 goto push_ota_crt
@if %a%==36 goto adb_killserver
@if %a%==0 goto menu
@if %a%==Jerxiaoming goto game
@echo 输入错误！！！
@pause
@goto menu

:push_client_key
adb push  client.key  /oemdata/configs/
@pause
@goto menu

:push_client_pub
adb push  client.pub  /oemdata/configs/
@pause
@goto menu

:push_tbox_crt
adb push  TBOX.crt  /oemdata/configs/
@pause
@goto menu

:push_ota_crt
adb push  OTA.crt  /oemdata/configs/
@pause
@goto menu


:color_change
@CLS
@echo 第一个对应于背景，第二个对应于前景。每个数字可以为以下任何值:
@echo.
@echo    0 = 黑色       8 = 灰色
@echo    1 = 蓝色       9 = 淡蓝色
@echo    2 = 绿色       A = 淡绿色
@echo    3 = 浅绿色     B = 淡浅绿色
@echo    4 = 红色       C = 淡红色
@echo    5 = 紫色       D = 淡紫色
@echo    6 = 黄色       E = 淡黄色
@echo    7 = 白色       F = 亮白色
@echo.
@echo 示例：
@echo.
@echo    07=黑底白字
@echo    0B=黑底蓝字
@echo    03=黑底黄字
@echo    70=白底黑字
@echo    F0=大白底黑字
@echo.
@set /p a=请输入颜色代码：
@echo.
@echo.
@echo @color %a% > txt/color_code.txt
@echo @CLS >> txt/color_code.txt
@pause
@goto menu

:grep_hal
@start txt\grep_hal.bat
@goto menu

:cat_arp
@start txt\cat_arp.bat
@goto menu

:http_addr_type
@mode con: cols=120 lines=40
@cmd < txt/color_code.txt 
@CLS
@echo.
@echo.
@echo ==========证书状态查询和切换（硬PKI和软证书）==========
@echo.
@adb shell < txt/cat_http_addr_type.txt
@echo.
@echo.
@echo 说明：
@echo 软证书：http_addr_type="0"
@echo 硬PKI：http_addr_type="1"
@echo.
@echo 证书切换后，重启后生效
@echo.
@echo ==========证书切换功能==========
@echo.
@echo A、切换到软证书
@echo B、切换到硬PKI
::@echo 3、重启4g模块
@echo 4、查询hal日志————————上报数据
@echo 0、返回上一层
@echo.
@set /p a=请输入选项：
@if %a%==A goto send_http_addr_0
@if %a%==B goto send_http_addr_1
::@if %a%==3 goto reboot
@if %a%==4 goto log_hal_now2
@if %a%==0 goto menu
@echo 输入错误！！！
@pause
@goto http_addr_type

:send_http_addr_0
@echo.
@adb shell < txt/send_http_addr_0.txt
@pause
@goto http_addr_type

:send_http_addr_1
@echo.
@adb shell < txt/send_http_addr_1.txt
@pause
@goto http_addr_type

:reboot
@echo.
adb shell reboot
@pause
@goto http_addr_type

:log_hal_now2
@start /max cmd /k adb shell tail -f /oemdata/logs/hal_info.log
@goto http_addr_type

:ver_du
@start txt\ver_du.bat
@goto menu

:shell
@start /max cmd /k adb shell
@goto menu

:open_devmgmt
@start C:\Windows\System32\devmgmt.msc
@goto menu

:log
@mode con: cols=120 lines=40
@cmd < txt/color_code.txt 
@CLS
@echo.
@echo.
@echo ==========日志路径预览（/oemdata/logs/）==========
@echo.
@adb shell ls /oemdata/logs/
@adb shell ls /media/sdcard/data/tbox_log/
@echo.
@echo ==========日志功能==========
@echo.
@echo 1、查询b.log————————校时
@echo 2、查询gps日志————————定位数据
@echo 3、查询hal日志————————上报数据
@echo 4、查询gprs日志————————电话数据
@echo 5、查询mcu日志————————mcu_info
@echo 6、查询ota日志————————otaApp.log
@echo 7、查询是否成功连接tsp平台
@echo 8、查询手动输入的日志文件名（tail -f）
@echo 9、查询手动输入的日志文件名（cat）
@echo 10、导出所有log（至adb根目录）（以当前时间命名）
@echo 11、导出指定log（至adb根目录）（自定义命名）
@echo 12、导出艾拉比OTA的log（至adb根目录）
@echo 13、清除所有log文件（/oemdata/logs/）
@echo 0、返回上一层
@echo.
@set /p a=请输入选项：
@if %a%==1 goto log_blog_now
@if %a%==2 goto log_gps_today_now
@if %a%==3 goto log_hal_now
@if %a%==4 goto log_gprs_now
@if %a%==5 goto log_mcu_now
@if %a%==6 goto log_ota_now
@if %a%==7 goto log_tsp_connect
@if %a%==8 goto log_xx_now
@if %a%==9 goto log_xx
@if %a%==10 goto log_pull_now
@if %a%==11 goto log_pull
@if %a%==12 goto pull_ota_log
@if %a%==13 goto log_rm
@if %a%==0 goto menu
@echo 输入错误！！！
@pause
@goto log

:pull_ota_log
@set a=ota_log_%date:~0,4%%date:~5,2%%date:~8,2%_%time:~0,2%%time:~3,2%%time:~6,2%
@adb pull /sdcard/ota/log %a%
@goto log

:log_ota_now
@start /max cmd /k adb shell tail -f /sdcard/ota/log/file/otaApp.log
@goto log

:log_tsp_connect
@echo.
@echo.
@adb shell < txt/cat_tsp_connect.txt
@echo.
@pause
@goto log

:log_gps_today_now
@start /max cmd /k adb shell tail -f /oemdata/logs/gps_info.log
@goto log

:log_blog_now
@start /max cmd /k adb shell tail -f /oemdata/logs/b.log
@goto log

:log_xx_now
@echo.
@echo.
@set /p filename2=请输入日志文件名：
@echo.
@echo.
@start /max cmd /k adb shell tail -f /oemdata/logs/%filename2%
@goto log

:log_xx
@echo.
@echo.
@set /p filename2=请输入日志文件名：
@echo.
@echo.
@start /max cmd /k adb shell cat /oemdata/logs/%filename2%
@goto log

:log_hal_now
@start /max cmd /k adb shell tail -f /oemdata/logs/hal_info.log
@goto log

:log_gprs_now
@start /max cmd /k adb shell tail -f /oemdata/logs/gprs_info.log
@goto log

:log_mcu_now
@start /max cmd /k adb shell tail -f /oemdata/logs/mcu_info.log
@goto log

:log_rm
@echo.
@echo.
adb shell rm -r /oemdata/logs/*
::adb shell rm -r /oemdata/logs/*.log.*
@echo.
@echo.
@pause
@goto log

:log_pull
@echo.
@echo.
@set /p a=请输入日志文件名：
@echo.
@echo.
@adb pull /oemdata/logs %a%
@pause
@echo.
goto log

:log_pull_now
@echo.
@echo.
@set a=log_%date:~0,4%%date:~5,2%%date:~8,2%_%time:~0,2%%time:~3,2%%time:~6,2%
@adb pull /oemdata/logs %a%
@adb pull /media/sdcard/data/tbox_log/  %a%
@echo.
goto log

:network
@mode con: cols=120 lines=40
@cmd < txt/color_code.txt 
@CLS
@echo.
@echo ==========ip地址说明（vlan）==========
@echo.
@echo tbox：192.168.2.43
@echo 网关：192.168.4.55
@echo mapecu：192.168.2.14
@echo mpc3：192.168.4.28
@echo 车机：192.168.4.32
@echo.
@echo ==========ip地址说明（产线pc端测试）==========
@echo.
@echo tbox：192.168.225.1
@echo mapecu：192.168.88.106
@echo.
@echo ==========网络功能==========
@echo.
@echo 1、查看Tbox网络拨号状态
@echo 2、ping 百度
@echo 3、ping 网关
@echo 4、ping mapecu
@echo 5、ping mpc3
@echo 6、ping 4gtbox
@echo 7、ping 车机
@echo 0、返回上一层
@echo.
@set /p a=请输入选项：
@if %a%==1 goto ifconfig
@if %a%==2 goto ping_baidu
@if %a%==3 goto ping_gateway
@if %a%==4 goto ping_mapecu
@if %a%==5 goto ping_mpc3
@if %a%==6 goto ping_4gtbox
@if %a%==7 goto ping_cheji

@if %a%==0 goto menu
@echo 输入错误！！！
@pause
@goto network

:ifconfig
@start /max cmd /k adb shell ifconfig
@goto network

:ping_baidu
@start /max cmd /k adb shell ping www.baidu.com
@goto network

:ping_gateway
@start /max cmd /k adb shell ping 192.168.4.55
@goto network

:ping_mapecu
@start /max cmd /k adb shell ping 192.168.2.14
@goto network

:ping_mpc3
@start /max cmd /k adb shell ping 192.168.4.28
@goto network

:ping_4gtbox
@start /max cmd /k adb shell ping 192.168.2.43
@goto network

:ping_cheji
@start /max cmd /k adb shell ping 192.168.4.32
@goto network

:ota
@mode con: cols=120 lines=40
@cmd < txt/color_code.txt 
@CLS
@echo.
@echo ==========TBOX本地升级包路径预览（/sdcard/ota/）==========
@echo.
@adb shell du -sh /sdcard/ota/*
@echo.
@set /p "size=总大小："<nul
@adb shell du -sh /sdcard/ota/
@echo.
@echo ==========艾拉比升级包路径预览（/sdcard/ota/package/file）==========
@echo.
@adb shell du -sh /sdcard/ota/package/file/*
@echo.
@set /p "size=总大小："<nul
@adb shell du -sh /sdcard/ota/package/file/
@echo.
@echo ==========OTA功能==========
@echo.
@echo 1、导入OTA升级包(.tar文件)
@echo 2、删除路径下的OTA升级包(.tar文件)
@echo 3、删除指定文件
@echo 4、升级
@echo 5、OTA路径查询（自动刷新脚本）
@echo 6、艾拉比fsm查询（自动刷新脚本）
@echo 7、查询ota日志————————otaApp.log
@echo 8、跳转到nvram目录下（cd /oemdata/abup/nvram)
@echo 0、返回上一层
@echo.
@set /p a=请输入选项：
@if %a%==1 goto push_ota_flie
@if %a%==2 goto rm_ota_flie
@if %a%==3 goto rm_flie
@if %a%==4 goto ota_updata
@if %a%==5 goto ota_du
@if %a%==6 goto fsm_cat
@if %a%==7 goto log_ota_now2
@if %a%==8 goto cd_nvram
@if %a%==9 goto pull_ota_log2
@if %a%==0 goto menu
@echo 输入错误！！！
@pause
@goto ota

:pull_ota_log2
@adb pull /sdcard/ota/log/file/otaApp.log otaApp.log
@goto ota

:cd_nvram
@start /max cmd /k adb shell
@goto ota

:fsm_cat
@start txt\fsm_cat.bat
@goto ota

:log_ota_now2
@start /max cmd /k adb shell tail -f /sdcard/ota/log/file/otaApp.log
@goto ota

:ota_du
@start txt\ota_du.bat
@goto ota

:push_ota_flie
@echo.
@set /p ota_flie=将ota升级文件(.tar文件)拖入此处：
adb push %ota_flie% /sdcard/ota/
@pause
@goto ota

:rm_ota_flie
@echo.
@echo.
@set /p a=请输入"yes"确认来删除 ：
@if %a%==yes goto rm_ota_flie_yes
@echo.
@echo.
@echo 取消删除~
@echo.
@echo.
@pause
@goto ota

:rm_ota_flie_yes
@echo.
@echo.
adb shell rm -r /sdcard/ota/*.tar
@echo.
@echo.
@pause
@goto ota

:rm_flie
@echo.
@echo.
@set /p filename=请输入要删除的文件名（包含后缀）：
@echo.
@echo.
adb shell rm -r /sdcard/ota/%filename%
@echo.
@echo.
@pause
@goto ota

:cat_xcall
@echo.
@adb shell < txt/cat_xcall.txt
@echo.
@pause
@goto menu

:cat_vin
@echo.
@adb shell < txt/cat_vin.txt
@echo.
@pause
@goto menu

:cat_iccid
@echo.
@adb shell < txt/cat_iccid.txt
@echo.
@pause
@goto menu

:ota_updata
@echo.
@set /p filename=请输入升级包的文件名（包含后缀）：
@echo.
@echo 删除之前的升级脚本......
@del txt\ota_updata.txt
@echo.
@echo 创建新的升级脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/ota_updata.txt
@echo /oemapp/app/bin/set_tuid -u /sdcard/ota/%filename% >> txt/ota_updata.txt
@echo exit >> txt/ota_updata.txt
@echo.
@echo 执行新的升级脚本.....
@start txt\ota_updata.bat
@start txt\timeout.bat
@echo.
@pause
@goto ota

:cat_sn
@echo.
@adb shell < txt/cat_sn.txt
@echo.
@pause
@goto menu

:cat_ver
@echo.
@adb shell < txt/cat_ver.txt
@echo.
@pause
@goto menu

:cat_7B120
@echo.
@echo 执行查询脚本.....
@start txt\cat_7B120.bat
@echo.
@pause
@goto menu

:send_vin
@echo.
@set /p vin_num=请输入要修改的vin：
@echo.
@echo 删除之前的写入脚本......
@del txt\send_vin.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_vin.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:terminal string:VIN string:%vin_num% >> txt/send_vin.txt
@echo exit >> txt/send_vin.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_vin.bat
@echo.
@pause
@goto menu

:send_vin000
@echo.
@echo.
@echo 删除之前的写入脚本......
@del txt\send_vin.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_vin.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:terminal string:VIN string:00000000000000000 >> txt/send_vin.txt
@echo exit >> txt/send_vin.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_vin.bat
@echo.
@pause
@goto menu


:send_ecall
@echo.
@set /p ecall_num=请输入要修改的ecall号码（手动）：
@echo.
@echo 删除之前的写入脚本......
@del txt\send_ecall.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_ecall.txt
@echo dbus-send --session --type=method_calldbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:server string:ecall_manual_num string:%ecall_num% >> txt/send_ecall.txt
@echo exit >> txt/send_ecall.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_ecall.bat
@echo.
@pause
@goto menu

:send_autoecall
@echo.
@set /p autoecall_num=请输入要修改的ecall号码（自动）：
@echo.
@echo 删除之前的写入脚本......
@del txt\send_autoecall.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_autoecall.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:server string:ecall_auto_num string:%autoecall_num% >> txt/send_autoecall.txt
@echo exit >> txt/send_autoecall.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_autoecall.bat
@echo.
@pause
@goto menu

:send_icall
@echo.
@set /p icall_num=请输入要修改的icall号码：
@echo.
@echo 删除之前的写入脚本......
@del txt\send_icall.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_icall.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:server string:icall_num string:%icall_num% >> txt/send_icall.txt
@echo exit >> txt/send_icall.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_icall.bat
@echo.
@pause
@goto menu

:send_xcall
@echo.
@set /p xcall_num=请输入要修改的xcall号码（所有xcall号码）：
@echo.
@echo 删除之前的写入脚本......
@del txt\send_xcall.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_xcall.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:server string:icall_num string:%xcall_num% >> txt/send_xcall.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:server string:ecall_auto_num string:%xcall_num% >> txt/send_xcall.txt
@echo dbus-send --session --type=method_calldbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:server string:ecall_manual_num string:%xcall_num% >> txt/send_xcall.txt
@echo exit >> txt/send_xcall.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_xcall.bat
@echo.
@pause
@goto menu

:send_sn
@echo.
@set /p num=请输入要修改的sn码：
@echo.
@echo 删除之前的写入脚本......
@del txt\send_sn.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_sn.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:terminal string:TBOXSN string:%num% >> txt/send_sn.txt
@echo exit >> txt/send_sn.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_sn.bat
@echo.
@pause
@goto menu

:send_sn000
@echo.
@echo.
@echo 删除之前的写入脚本......
@del txt\send_sn.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_sn.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:terminal string:TBOXSN string:0000000000000000 >> txt/send_sn.txt
@echo exit >> txt/send_sn.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_sn.bat
@echo.
@pause
@goto menu

:cat_productkey
@echo.
@adb shell < txt/cat_productkey.txt
@echo.
@pause
@goto menu

:cat_devicesecret
@echo.
@adb shell < txt/cat_devicesecret.txt
@echo.
@pause
@goto menu

:send_productkey000
@echo.
@echo 删除之前的写入脚本......
@del txt\send_productkey.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_productkey.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:terminal string:PRODUCTKEY string:00000000000 >> txt/send_productkey.txt
@echo exit >> txt/send_productkey.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_productkey.bat
@echo.
@pause
@goto menu

:send_productkey
@echo.
@set /p num=请输入要修改的productkey：
@echo.
@echo 删除之前的写入脚本......
@del txt\send_productkey.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_productkey.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:terminal string:PRODUCTKEY string:%num% >> txt/send_productkey.txt
@echo exit >> txt/send_productkey.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_productkey.bat
@echo.
@pause
@goto menu

:send_devicesecret000
@echo.
@echo.
@echo 删除之前的写入脚本......
@del txt\send_devicesecret.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_devicesecret.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:terminal string:DEVICESECRET string:00000000000000000000000000000000 >> txt/send_devicesecret.txt
@echo exit >> txt/send_devicesecret.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_devicesecret.bat
@echo.
@pause
@goto menu

:send_devicesecret
@echo.
@set /p num=请输入要修改的devicesecret：
@echo.
@echo 删除之前的写入脚本......
@del txt\send_devicesecret.txt
@echo.
@echo 创建新的写入脚本......
@echo export DBUS_SESSION_BUS_ADDRESS=`cat /tmp/.default-msgbus-session-address` > txt/send_devicesecret.txt
@echo dbus-send --session --type=method_call --print-reply  --dest=com.yuantel.tbox.file    /com/yuantel/tbox/file  com.yuantel.tbox.file.cfg_data_set string:terminal string:DEVICESECRET string:%num% >> txt/send_devicesecret.txt
@echo exit >> txt/send_devicesecret.txt
@echo.
@echo 执行新的写入脚本.....
@start txt\send_devicesecret.bat
@echo.
@pause
@goto menu

:cat_tspinfo
@echo.
@adb shell < txt/cat_tspinfo.txt
@echo.
@pause
@goto menu

:adb_killserver
adb kill-server
@pause
@goto menu
```