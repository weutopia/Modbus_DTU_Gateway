# Modbus_DTU_Gateway

# 第一阶段：读取ModbusRTU协议的空调面板信息

>注意事项：
>1.江森T7600寄存器为16位，即访问一个寄存器最大可返回0xFF 0xFF
>2.对于温度这类具体数字，访问一个寄存器返回0xFF 0xFF（16位全部返回）
>3.对于Bool值表征状态的，访问一个寄存器返回0xFF（仅仅返回寄存器的低8位）
