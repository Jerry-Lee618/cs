- 删除空行
>- 删除空行 :g/^$/d. 
>- 删除空行以及只有空格的行 :g/^\s*$/d. 
>- 删除以# 开头或空格# 或tab#开头的行 :g/^\s*#/d.
- 大小写替换
>- 全部变成小写 :%s/.*/\L&/g
>- 全部变成大写 :%s/.*/\U&/g
>- 正则匹配的变成大写 :%s/pattern/\U&/g
