1、group by 查找分组中的最后一条记录的某个值
   substring(max(concat(create_time,auth_status)) from 14)
