* sed在管道中使用
> * 替换一到多个空格为‘，’   cat f | sed 's/[ ][ ]*/，/g'        &emsp;([ ]为一个空格，仅为展示用)
* mac查看端口被哪个进程监听
> * sudo lsof -i :端口
* mac查看进程监听的端口
> * sudo lsof -nP -p 进程号 | grep LISTEN
* 查看监听端口的进程
> * sudo lsof -nP | grep LISTEN | grep 端口号
> * lsof -nP -iTCP -sTCP:LISTEN
