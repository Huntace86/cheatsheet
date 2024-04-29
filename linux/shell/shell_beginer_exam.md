# shell beginer exam #
## 1.按如下格式输出信息 ##
    	当前用户名称: 
    	当前用户家目录: 
    	当前用户登录shell: 
    
    运行示例：
    	./xxx.sh
    	当前用户名称: root
    	当前用户家目录: /root
    	当前用户登录shell: /bin/bash

## 2.输入一个整数n，输出1加到n的和,并打印和结果 ##
    
    运行示例：
    	./xxx.sh 10
    	sum: 55

## 3.写一个shell脚本 ##
    	判断当前目录是否有名称为"fiberhome"文件。
    	如果没有则用touch建立该文件，并打印“新创建文件fiberhome”。 
    	如果存在该文件且不为目录，则删除该文件并创建名称为"fiberhome"的目录,并打印“新创建目录fiberhome”。 
    	如果存在该文件且为目录，则删除该目录，并打印“删除目录fiberhome”。 
    运行示例：
    	./xxx.sh
    	Created file 'fiberhome'
    	./xxx.sh
    	Deleted file and created directory 'fiberhome'
    	./xxx.sh
    	Deleted directory 'fiberhome'

## 4.提取/etc/passwd的用户名并打印 ##
    
    运行示例：
    	./xxx.sh
    	Usernames in /etc/passwd:
    	root
    	daemon
    	bin
    	sys
    	sync
    	games
    	man
    	...............

## 5.输入一个年份，判断是不是闰年并打印判断结果 ##
   
    运行示例：
    	./xxx.sh
    	请输入一个年份: 2024
    	2024 是闰年。

## 6.系统生成0~99的随机数，通过输入来猜猜数字 ##
    
    	当输入数据与随机数相同，则打印“猜对了”;
    	当输入数据大于随机数，则打印“猜大了”;
    	当输入数据小于随机数，则打印“猜小了”;
    
    运行示例：
    	./xxx.sh
    	50
    	猜小了
    	90
    	猜大了
    	80
    	猜对了

## 7.使用awk来统计文本文件中每行的单词数 ##

    要求：只包含英文单词的文本，以参数的形式传递给脚本；
    		当文件不存在要有打印提示；
    运行示例：
    	./xxx.sh passwd.sh
    	Line 1 has 1 words.
    	Line 2 has 0 words.
    	Line 3 has 6 words.
    	Line 4 has 1 words.
    	Line 5 has 4 words.
    	Line 6 has 1 words.
    	Line 7 has 3 words.
    	Line 8 has 4 words.
    	Line 9 has 1 words.
    	Line 10 has 2 words.

## 8.写一个shell脚本 ##
    	输入一种水果：
    	当是apple，则打印select red；
    	当是banana，则打印select yellow；
    	当是orange，则打印select orange；
    	否则，打印not equal；
    
    运行示例：
    	./xxx.sh
    	Please input a fruit (apple, banana, orange):
    	apple
    	select red
    
    	./xxx.sh
    	Please input a fruit (apple, banana, orange):
    	tomato
    	not equal