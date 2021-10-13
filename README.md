# Huawei-route
华为交换机常用命令
[Quidway]dis cur ；显示当前配置
[Quidway]display current-configuration ；显示当前配置
[Quidway]display interfaces ；显示接口信息
[Quidway]display vlan all ；显示路由信息
[Quidway]display version ；显示版本信息

[Quidway]super password ；修改特权用户密码
[Quidway]sysname ；交换机命名
[Quidway]interface ethernet 0/1 ；进入接口视图
[Quidway]interface vlan x ；进入接口视图
[Quidway-Vlan-interfacex]ip address 10.65.1.1 255.255.0.0 ；配置VLAN的IP地址

[Quidway]ip route-static 0.0.0.0 0.0.0.0 10.65.1.2 ；静态路由＝网关
[Quidway]rip ；三层交换支持
[Quidway]local-user ftp

[Quidway]user-interface vty 0 4 ；进入虚拟终端
[S3026-ui-vty0-4]authentication-mode password ；设置口令模式
[S3026-ui-vty0-4]set authentication-mode password simple 222 ；设置口令
[S3026-ui-vty0-4]user privilege level 3 ；用户级别

[Quidway]interface ethernet 0/1 ；进入端口模式
[Quidway]int e0/1 ；进入端口模式
[Quidway-Ethernet0/1]duplex {half|full|auto} ；配置端口工作状态
[Quidway-Ethernet0/1]speed {10|100|auto} ；配置端口工作速率
[Quidway-Ethernet0/1]flow-control ；配置端口流控
[Quidway-Ethernet0/1]mdi {across|auto|normal} ；配置端口平接扭接
[Quidway-Ethernet0/1]port link-type {trunk|access|hybrid} ；设置端口工作模式
[Quidway-Ethernet0/1]port access vlan 3 ；当前端口加入到VLAN
[Quidway-Ethernet0/2]port trunk permit vlan {ID|All} ；设trunk允许的VLAN
[Quidway-Ethernet0/3]port trunk pvid vlan 3；设置trunk端口的PVID
[Quidway-Ethernet0/1]undo shutdown ；激活端口
[Quidway-Ethernet0/1]shutdown ；关闭端口
[Quidway-Ethernet0/1]quit ；返回

[Quidway]vlan 3 ；创建VLAN
[Quidway-vlan3]port ethernet 0/1 ；在VLAN中增加端口
[Quidway-vlan3]port e0/1 ；简写方式
[Quidway-vlan3]port ethernet 0/1 to ethernet 0/4；在VLAN中增加端口
[Quidway-vlan3]port e0/1 to e0/4 ；简写方式

[Quidway]monitor-port <interface_type interface_num>；指定镜像端口
[Quidway]port mirror <interface_type interface_num> ；指定被镜像端口
[Quidway]port mirror int_list observing-port int_type int_num ；指定镜像和被镜像

[Quidway]description string ；指定VLAN描述字符
[Quidway]description ；删除VLAN描述字符
[Quidway]display vlan [vlan_id] ；查看VLAN设置

[Quidway]stp {enable|disable} ；设置生成树,默认关闭
[Quidway]stp priority 4096 　；设置交换机的优先级
[Quidway]stp root {primary|secondary} ；设置为根或根的备份
[Quidway-Ethernet0/1]stp cost 200 ；设置交换机端口的花费

[Quidway]link-aggregation e0/1 to e0/4 ingress|both ;　端口的聚合
[Quidway]undo link-aggregation e0/1|all ; 始端口为通道号

[SwitchA-vlanx]isolate-user-vlan enable ；设置主vlan
[SwitchA]isolate-user-vlan <x> secondary <list> ；设置主vlan包括的子vlan
[Quidway-Ethernet0/2]port hybrid pvid vlan <id> ；设置vlan的pvid
[Quidway-Ethernet0/2]port hybrid pvid ；删除vlan的pvid
[Quidway-Ethernet0/2]port hybrid vlan vlan_id_list untagged 　；设置无标识的vlan
如果包的vlan id与PVId一致，则去掉vlan信息. 默认PVID=1。
所以设置PVID为所属vlan id, 设置可以互通的vlan为untagged.
-----------------------------------
