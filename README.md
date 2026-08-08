# proxybridge mod
自用，源码来自proxybridge官方 https://github.com/InterceptSuite/ProxyBridge 

基于ProxyBridge-Setup-3.2.0版本  [v3.2.0 mod last version](https://github.com/ouoo-code/proxybridge_mod/releases/tag/mod2)。  
  
基于ProxyBridge 4.0版本我也mod了下，修正了几个bug，修改了一些界面和功能出来。定期更新。  

**以下为4.0功能更新:**  
#20260808  
mod v4 重大功能升级：  
1.实现代理子进程，规则内允许配置为代理此规则的程序底下的所有子进程，优先本规则或匹配子进程规则（如没设置则回落到本规则）  
2.实现代理回环保护，主要是因为实现子进程代理后，有较大概率出现各种程序进程相互调用的情况，特别是代理服务又被代理到自己的情况。当出现保护时日志会显示[LOOP GUARD]。  
3.增加“允许代理链”开关，只有用户明确需要多级代理时才关闭防回环。程序默认启用“代理端点防回环”（即关闭允许代理链），发现目标等于代理端点时自动直连。  
4.日志和规则上添加符号，闪电图标表示为子进程代理，双箭头图标为父进程代理。  
5.测试版本，不知道稳定性怎么样，欢迎反馈。  
  
  
#20260710
1. 修复代理删除，规则引用错乱的问题。已提交至官方bug。  
2. 把原3.2.0增加的流量图标功能、流量统计、查看连接功能、只查看匹配规则的日志功能都移植过来了。  
3. 在代理页面增加一个替换代理功能：把规则中所的proxy类型的规则全部替换为选中的代理。  
4. 代理服务器设置界面修改，原来的有点太难看了。沿用3.2.0原mod后的界面。  
5. 允许字体，字体大小设置。
6. 代理流量统计。

#修复源码缺陷：连接映射清理和端口决策缓存没有同步失效  
1.stale 清理连接时同步 port_clear(src_port) // 只free(to_free)，没有 port_clear(src_port)  
2.remove_connection也同步清端口缓存  
3.TCP 映射保留时间从 2 分钟提高到 30 分钟  
4.UDP 仍保留 2 分钟  
5.TCP/UDP 连接记录加区分，避免误清理策略混用  

  
**--4.0 mod--**

Here is the English translation:

---20260808

**Mod v4 Major Feature Upgrade:**

1. **Implemented proxy subprocess support**: Rules can now be configured to proxy all child processes under the program matching the rule. Child process rules take priority, or fall back to the parent rule if no child process rule is set.

2. **Implemented proxy loopback protection**: This is mainly necessary because subprocess proxying significantly increases the likelihood of various program processes calling each other, especially when the proxy service itself gets proxied. When protection triggers, the log will display `[LOOP GUARD]`.

3. **Added "Allow Proxy Chain" toggle**: Only disable loopback prevention when the user explicitly needs multi-level proxying. By default, "Proxy Endpoint Loopback Prevention" is enabled (i.e., "Allow Proxy Chain" is off), automatically using direct connection when the target equals the proxy endpoint.

4. **Added symbols to logs and rules**: A lightning bolt icon indicates subprocess proxying, and a double-arrow icon indicates parent process proxying.

5. **Test version**: Stability is uncertain; feedback is welcome.

---20260710


1. Fixed the issue where deleting a proxy caused rule references to become misaligned. This bug has been submitted to the official tracker.  
2. Ported over the traffic icon feature, traffic statistics, connection viewer, and "show only matched rule logs" feature that were added in the original 3.2.0.  
3. Added a "Replace Proxy" function on the Proxy page: replaces all proxy-type rules in the ruleset with the selected proxy.  
4. Modified the proxy server settings interface — the original one was not good. Kept using the interface from the modded 3.2.0 version.
5. Supports font and font size settings.
6. Proxy traffic statistics function

#Fix source code defects: connection mapping cleanup and port decision cache are not invalidated synchronously  
1.During stale cleanup, synchronize port_clear(src_port) when cleaning connections // Currently only frees to_free, without calling port_clear(src_port)  
2.Also synchronously clear the port cache in remove_connection  
3.Increase TCP mapping retention time from 2 minutes to 30 minutes  
4.UDP remains at 2 minutes  
5.Add distinction for TCP/UDP connection records to avoid mixed use of cleanup policies by mistake  

**4.0 GUI mod:**
![traffic status](trafstatus.png)
![con log](conlog.png)
![font & log](font-log.png)
![proxy setting](proxyset.png)
![proxy traffic](proxytraf.png)
![proxy replace](replace.png)
![rules gui](rules.png)


**--以下为3.2.0功能更新：--**  

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

**3.2.0 GUI mod:**

 ![查看连接日志](viewconlog.png) 
 ![演示](trayicon.png)图标流量显示。 
 ![演示](matchrulelog.png) 
 ![演示](setwindow.png) 

