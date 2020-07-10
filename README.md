# 食用MyCloudflareScanner
Cloudflare IP扫描工具

## 食用方式  

先下载并解压整个包  
如果仅测试ip，则直接运行程序  
如果要自动化配置host，先在host文件内添加域名（ip随便写），然后再在domainlist内写入域名，然后以管理员身份运行程序  

## 工作流程  

    所有ip ping50次，按结果排序  
    取好的30个节点进行下载测速  
    按结果综合排序  
    取分数最高的ip，写入host文件  

计算方式：ping收到的包的个数×5-ping平均延迟（ms）+下载速度（mb/s）×10  
（随便写的，可能不科学）  

## 配置文件格式  
config.txt  

下载测速url  
重解析域名  
ping线程数  
ping次数  
取分数高的ip的个数  
下载的秒数  
创建下载间隔的秒数  

## domainlist.txt  

一行一个域名，程序会对应host里面的ip替换掉  

## 输出结果格式  
[分数，ip，ping延迟，收到的包的个数，下载速度]
