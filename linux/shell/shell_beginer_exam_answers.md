# shell_beginer_exam_answers #
1.按如下格式输出信息
    当前用户名称: 
    当前用户家目录: 
    当前用户登录shell: 
    
    #!/bin/bash
    echo "当前用户名称: $USER"
    echo "当前用户家目录: $HOME"
    echo "当前用户登录shell: $SHELL"
    exit 0

2.
    输入一个整数n，输出1加到n的和,并打印和结果，例如./sum.sh 10
    
    #!/bin/bash
    sum=0
    for i in $(seq 1 $1)
    do
    sum=$(( sum + i ))
    done
    echo "sum: $sum"
    exit 0


3.
    判断当前目录是否有名称为"fiberhome"文件。
    如果没有则用touch建立该文件，并打印“新创建文件fiberhome”。 
    如果存在该文件且不为目录，则删除该文件并创建名称为"fiberhome"的目录,并打印“新创建目录fiberhome”。 
    如果存在该文件且为目录，则删除该目录，并打印“删除目录fiberhome”。 
    
    #!/bin/bash
    if [ ! -e "fiberhome" ]; then
    touch fiberhome
    echo "Created file 'fiberhome'"
    elif [ -f "fiberhome" ]; then
    rm fiberhome
    mkdir fiberhome
    echo "Deleted file and created directory 'fiberhome'"
    elif [ -d "fiberhome" ]; then
    rm -r fiberhome
    echo "Deleted directory 'fiberhome'"
    fi
	
4.
提取/etc/passwd的用户名并打印

    #!/bin/bash
    
    usernames=$(cut -d: -f1 /etc/passwd)
    
    echo "Usernames in /etc/passwd:"
    echo "$usernames"


5.输入一个年份，判断是不是闰年并打印判断结果

    #!/bin/bash
    read -p "请输入一个年份: " year
    
    if [ $((year % 4)) -eq 0 ] && [ $((year % 100)) -ne 0 ] || [ $((year % 400)) -eq 0 ]; then
    echo "$year 是闰年。"
    else
    echo "$year 不是闰年。"
    fi


6.系统生成0~99的随机数，通过输入来猜猜数字。
当输入数据与随机数相同，则打印“猜对了”;
当输入数据大于随机数，则打印“猜大了”;
当输入数据小于随机数，则打印“猜小了”;

    #!/bin/bash
    
    random_num=$((RANDOM % 100))
    
    while true; do
    read guess
    
    if [[ $guess -eq $random_num ]]; then
    echo "猜对了"
    break
    elif [[ $guess -lt $random_num ]]; then
    echo "猜小了"
    else
    echo "猜大了"
    fi
    done
    

7.使用awk来统计文本文件中每行的单词数。
要求：只包含英文单词的文本，以参数的形式传递给脚本；
		当文件不存在要有打印提示；

    #!/bin/bash
    input_file="$1"
    if [ ! -f "$input_file" ]; then
      echo "Error: 文件 '$input_file' 不存在或无法读取。"
      exit 1
    fi
    # 使用awk统计每行的单词数
    awk '{ print "Line " NR " has " NF " words." }' $input_file


8.输入一种水果：
    当是apple，则打印red；
    当是banana，则打印yellow；
    当是orange，则打印orange；
    否则，打印not equal；
    
    #!/bin/bash
    
    echo "Please input a fruit (apple, banana, orange):"
    read fruit
    
    case $fruit in
      "apple")
    echo "You selected an apple. It is red."
    ;;
      "banana")
    echo "You selected a banana. It is yellow."
    ;;
      "orange")
    echo "You selected an orange. It is orange."
    ;;
      *)
    echo "Sorry, I'm not familiar with that fruit."
    ;;
    esac
