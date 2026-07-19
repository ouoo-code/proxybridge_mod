# proxybridge mod
自用，源码来自proxybridge官方 https://github.com/InterceptSuite/ProxyBridge 

基于ProxyBridge-Setup-3.2.0版本。  3.2.0 最后的mod在 https://github.com/ouoo-code/proxybridge_mod/releases/tag/mod2 下载。  
  
4.0版本我也mod了下，修正了几个bug，修改了一些界面和功能出来。定期更新。  

---以下为4.0功能更新:---  
1. 修复代理删除，规则引用错乱的问题。已提交至官方bug。  
2. 把原3.2.0增加的流量图标功能、流量统计、查看连接功能、只查看匹配规则的日志功能都移植过来了。  
3. 在代理页面增加一个替换代理功能：把规则中所的proxy类型的规则全部替换为选中的代理。  
4. 代理服务器设置界面修改，原来的有点太难看了。沿用3.2.0原mod后的界面。  
5. 允许字体，字体大小设置。  
  
---4.0 mod--  
1. Fixed the issue where deleting a proxy caused rule references to become misaligned. This bug has been submitted to the official tracker.  
2. Ported over the traffic icon feature, traffic statistics, connection viewer, and "show only matched rule logs" feature that were added in the original 3.2.0.  
3. Added a "Replace Proxy" function on the Proxy page: replaces all proxy-type rules in the ruleset with the selected proxy.  
4. Modified the proxy server settings interface — the original one was not good. Kept using the interface from the modded 3.2.0 version.
5. Supports font and font size settings.
  
----以下为3.2.0功能更新：---  

修复：  
1.规则禁用后，自动启动，某些场景禁用无效。  
2.开机启动的处理，去除最小化窗口。  
3.调整"代理设置"窗口。  

增加：  
1.双击托盘出现主窗口。  
2.启用规则匹配日志。  
3.托盘区流量显示。  
4.增加"查看连接日志"功能。  
 
Fixes:  
1.After a rule is disabled, it automatically re-enables; disabling is ineffective in certain scenarios.  
2.Handling of startup launch: removed window minimization.  
3.Adjusted the "Proxy Settings" window.  

Additions:  
1.Double-clicking the system tray icon brings up the main window.  
2.Added rule matching logs.  
3.Traffic display in the system tray area.  
4.Added "View Connection Logs" feature.  

 ![查看连接日志](viewconlog.png) 
 ![演示](trayicon.png)图标流量显示。 
 ![演示](matchrulelog.png) 
 ![演示](setwindow.png) 

