#### shell脚本的本质:shell命令的有序集合
#### 建立shell脚本的过程
###  1 建立文件并编译 （文件以 .sh 为后缀。文件名原则上用字母数字下划线的组合，通常以字母开头有一定意义为好）
###  2 修改权限  将编辑的脚本添加可执行权限
###  3 执行  如果脚本有可执行权限 可以用./filename 直接执行
###         如果没有执行权限 可以使用 bash filename 声明解释器执行
#### 变量：需要是合法的标示符
###  1 数字字母下划线组成
###  2 不能以数字开头
###  3 不能和关键字重名（shell 命令）
###  4 shell中是区分大小写的
#### 数字和字符串类型
     shell是弱类型语言
### 注意点：变量赋值时等号两边不要有空格
###        可以用unset删除一个变量的赋值
###        在取变量值的时候用$
#### 位置变量：在执行脚本时，通过命令行进入的参数就叫做位置变量
###  $0 脚本名
###  $1 -9 表示1-9 9个位置的传入
###  ${10}
###  传入字符串中间有空格需要用“”
###  $# 命令行参数的个数，不包含命令本身
###  $? 显示前一个命令的推出状态，如果正常为0，否则为非0
#### export 添加环境变量
###  HOME PATH
     export PATH+=":/home/linux/shell"
#### read:从终端获取变量
###  1 一个read对应一个回车
#### expr 简单的表达式运算
          注意：运算符两边药加空格
          eg： echo `expr 1 + 5`
#### let: 多种运算
###  + - * / % += -+。。。。。
###  << >> ^ & | ~
#### bc:小数运算
#### 测试：
#### True False
#### test 语句
###  数字 字符串 文件
###  用[]的形式 不要忘了空格
#### &&=-a ||=-o ！
###  与：一假则假 [ 1 -eq 2 -a 1 -eq 1]  [ 1 -eq 2 ] && [ 1 -eq 1 ]
###  或：一真则真 [ 1 -eq 2 -o 1 -eq 1]  [ 1 -eq 2 ] || [ 1 -eq 1 ]
###  非：真变假 假变真 ！ [ 1 -eq 2 ]
#### if语句
###  1.简单的if语句
     if  表达式
     then 
         命令表
     fi
#### case语句
     case 字符串变量 in
     模式1）
         命令表1
         ；；
     模式2 | 模式3）
         命令表2
         ；；
     模式n）
         命令表n
         ；；
     esac
     
