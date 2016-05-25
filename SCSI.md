# scsi   
可热插拔，pin多，I/O由SCSI控制器完成，CPU参与率极低。

---
#### SCSI与SATA的区别
- sata其实是scsi体系里抽取出的一部分，也就是说scsi能兼容sata，但sata反过来就不行。
- SATA需要CPU参与处理中断等，CPU占用率高。
- scsi本质上还是为服务器准备的磁盘系统，它非常强调所有的控制可以由scsi体系自己完成，不需要cpu控制，所以scsi非常省资源，而sata需要cpu介入控制传输过程。

---
#### SCSI启动器与目标器
- 计算机的SCSI主机适配器是一个典型的启动器 (initiator) 
- SCSI接口的硬盘是一个典型的目标器 (target)
- 启动器的SCSI设备接收到系统发出的执行一个I/O进程的任务后，以SCSI命令的形式传给目标器。目标器接收I/O任务，并将其传送到相应的LUN中执行，其中，LUN代表物理外围设备和执行SCSI命令所需要的逻辑电路。

---
#### SCSI总线数据传输控制
- SCSI 控制信号有9个：ATN，BSY，ACK，RST，MSG，SEL，C/D，REQ，I/O。   
- 数据线： 8~16个。  
其中C/D，SEL，MSG，BSY，SEL的状态决定了总线处于什么阶段。根据I/O任务的完成情况可以分成八个不同阶段。它们分别是BUS FREE(总线空闲)、ARBITRATION(仲裁)、SELECTION(选择)、RESELECTION(重选)、COMMAND(命令)、DATA(数据)、MESSAGE(消息)和STATUS(状态)。
- 一个典型的过程： BUS FREE阶段状态的后面是ARBITRATION, SELECTION以及一个MESSAG EOUT阶段状态。在这些阶段状态之后是COMMAND，DATA阶段状态，然后是STATUS阶段状态。

---  
#### SCSI Connector
![](http://d.hiphotos.baidu.com/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=b22963b9b31bb0519b29bb7a5713b1d1/30adcbef76094b36b7f17476a3cc7cd98c109dcd.jpg)
