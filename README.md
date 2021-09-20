# Modbus_DTU_Gateway

# 第一阶段：读取ModbusRTU协议的空调面板信息

>已知注意事项：
>1.江森T7600寄存器为16位，即访问一个寄存器最大可返回0xFF 0xFF
>2.对于温度这类具体数字，访问一个寄存器返回0xFF 0xFF（16位全部返回）
>3.对于Bool值表征状态的，访问一个寄存器返回0xFF（仅仅返回寄存器的低8位）
>4.部分功能码没有开放，继电器无法控制

已经实现读取/预置面板信息，由于寄存器写操作只开放了16功能码，只能写入部分面板信息

# 第二阶段：决定开发方向：

1.使用ModbusRTU转TCP设备 + 设备厂家的云平台——成本：100 + 云平台流量费用（较高）

<img src="https://img.alicdn.com/imgextra/https://img.alicdn.com/imgextra/i1/3159274970/O1CN01ClvJYT1maJ9MlmnKq_!!3159274970.png_430x430q90.jpg" style="zoom: 50%;" />



2.使用嵌入式Linux开发板作网关，内网web控制——成本：600~800，开发速度较慢

<img src="https://gd1.alicdn.com/imgextra/i2/880983124/O1CN01Xx0k731YwpzsaVigi_!!880983124.jpg" style="zoom: 33%;" />

3.使用RTOS单片机作网关，外网web控制——成本：100~200

<img src="https://img.alicdn.com/imgextra/i1/4160407286/O1CN01gFgjSP23h2MNbII1t_!!4160407286.png_430x430q90.jpg" style="zoom: 67%;" />
