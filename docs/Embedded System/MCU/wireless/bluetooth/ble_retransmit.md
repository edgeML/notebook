1 蓝牙通信中，丢包不会重传的情况有以下几种
1 当数据包的CRC 校验失败时，蓝牙设备会直接丢弃该数据包，而不进行重传
2 当数据包的ACK标志位被设置为0时，表示这个数据包不需要进行确认，因此
即使丢包也不会进行重传
3 当使用的是不可靠的 L2CAP 信道时，数据包的传输不会进行重传。这种情况下，
数据包的可靠性是由上层协议来保证的

注意：蓝牙协议中的重传机制是由 L2CAP 协议来实现的。
蓝牙链路包的 SN序列在L2CAP协议的头部中，占用2个字节，位于第1个字节和2个字节。SN序号用于标识链路包的顺序，以便接收方可以正确的重组链路包。在L2CAP协议中，SN序号的范围是 0 到 65535。
————————————————

                            版权声明：本文为博主原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接和本声明。
                        
原文链接：https://blog.csdn.net/aningxiaoxixi/article/details/130434647