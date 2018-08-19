### 1.查看文件和文件夹
    ll:查看文件和文件夹的详细信息
    cd:进入目录.
        例 如:cd java 回车cd java 回车。就进入当前目java目录
            cd /java 回车。就是进入根目录下的java目录
            cd ~ 回车。就是进入用户目录。
            cd - 回车。退回上次的目录。
            cd 回到用户目录	
    pwd:显示当前目录的绝对路径.

### 2.文件和文件夹
    mkdir :创建文件夹.
        例：mkdir filename 回车。新建文件夹名为filename.
			mkdir filename1 filename2... 回车。新建多个文件夹。
			mkdir -p file1/file2 回车。新建多级文件夹。
    rm  :删除文件和文件夹.
        例：rm -rf file 回车。 删除file（包括里面的文件）
    mv  :移动/重命名一个目录.
        例：mv -rf from to 回车。把from目录转移到to目录，如果文件名不一样，就重命名。
    cp  :复制一个文件
        例：cp from to 回车。复制一个文件。
			cp -a from to 回车。复制一个目录
    echo:(新建)写入一个文件
        例：echo 121212 > dir/temp.txt 回车.把121212覆盖写入temp.txt,如果没有这个文件，会新建。
			echo 121212 >> dir/temp.txt 回车.把121212追加写入temp.txt,如果没有这个文件，会新建。
    less:查看全部内容.
        例：less log.txt 回车。分页查看，还可以方便地搜索（/搜索内容），回翻等操作
        （翻页：空格,往回翻：↑,往下翻:↓,退出：q者 Ctrl+C）
    cat : 查看全部内容。
		例：cat log.txt 回车。
	tail：查看尾部内容。
		例：tail -f user.log   实时刷新显示文件的尾部，这条命令对于观察调试程序的运行非常重要。
	tar :打包压缩/解压缩。
		例：tar -czvf tet.tar tet 回车。c 新建的压缩文件，z 要压缩。就是把tet目录压缩成tet.tar。
		    tar -xzvf tet.tar 回车。把 tet.tar解压到前文件夹。
			tar -xzvf tet.tar -C ttt 回车。把tet.tar解压到ttt文件夹。
            
### 3.文件权限
    用户种类|		用户	|		用户组	|	不相关		|
	操作	|	读	写	执行|	读	写	执行|	读	写	执行|
	chmod	|	0	0	0	|	0	0	0	|	0	0	0	|
	
	1是拥有，0是不拥有，正好是三个八（0到7）进制的数：000到777，用chmod来设置权限。
	例：chmod 000 log.txt 回车。就是任何权限都没有。
		chmod 123 log.txt 回车。用户可执行，用户组可写，不相关用户可写可执行。
		chmod 642 log.txt 回车。用户可读可写，用户组可读，不相关用户可写。

### 4.用户操作
    su		: 切换用户。
		例：su guzi 回车。然后会让输入密码，就切换到了guzi用户。
	useradd	：添加用户，只有root用户可以用。-g 
		例：useradd test 回车。就添加了一个用户叫test,但还是不能使用的。要设置密码。
	passwd	：重置或设置密码。
		例	：passwd test 回车。给用户test重新设置密码。然后会显示让输入密码。
	userdel	:删除用户。
		例 	：userdel test 回车。删除test用户。不删除用户目录。
			  userdel -r test 回车。删除test用户。并删除用户目录。
			  userdel -r -f test 回车。暴力删除。
	chown	:修改文件所有人。
		例	：chown 用户：用户组 目录 把目录的拥有人改成用户。

### 5.网址操作
    ifconfig :查看网址

### 6.实用语句
    ps –ef |grep tomcat : 查看还在运行的tomcat，里面会显示tomcat的进程ID
	kill -9 进程ID：强杀后台进程。
	./startup.sh : 运行一个程序前面加 ./
	tail -f log.txt :实时刷新显示文件的尾部，这条命令对于观察调试程序的运行非常重要。
	service iptables stop :关闭防火墙
	chkconfig iptables off :修改自动启动防火墙配置文件。

### 7.java
    在/etc/profile文件最后面添加
	export JAVA_HOME=请指定JDK的目录
	export PATH=$PATH:$JAVA_HOME/bin
	
	source /etc/profile 让这个文件生效。