# Overview
psutil (python system and process utilities) is a cross-platform third-party library used for retrieving information about running processes and system utilization, including CPU, memory, disk, network, and more. It is mainly used for system monitoring, performance analysis, process management, and other related scenarios.

# Getting Started 
### linux
psutil install for linux
pip3 install psutil

### Pycharm
psutil install for Pycharm
settting -- Python Interpreter -- Alt + insert
psutil version 5.9.6

# For example
### Getting CPU information
'''查看cpu物理个数的信息'''
import psutil
print(u"物理CPU个数: %s" % psutil.cpu_count(logical=False))

### Memory Information and Available Memory
'''查看内存信息,剩余内存.free  总共.total'''
'''round()函数方法为返回浮点数x的四舍五入值'''

free = str(round(psutil.virtual_memory().free / (1024.0 * 1024.0 * 1024.0), 2))
total = str(round(psutil.virtual_memory().total / (1024.0 * 1024.0 * 1024.0), 2))
memory = int(psutil.virtual_memory().total - psutil.virtual_memory().free) / float(psutil.virtual_memory().total)
print(u"物理内存： %s G" % total)
print(u"剩余物理内存： %s G" % free)
print(u"物理内存使用率： %s %%" % int(memory * 100))
