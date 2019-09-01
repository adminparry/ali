# 浏览器的缓存规则

题目是浏览器中的缓存有硬盘缓存和内存缓存 请问什么时候是硬盘缓存什么时候是内存缓存

浏览器缓存可以分成 Service Worker、Memory Cache、Disk Cache 和 Push Cache，那请求的时候 from memory cache 和 from disk cache 的依据是什么，哪些数据什么时候存放在 Memory Cache 和 Disk Cache中？

如果开启了Service Worker首先会从Service Worker中拿
如果新开一个以前打开过的页面缓存会从Disk Cache中拿（前提是命中强缓存）
刷新当前页面时浏览器会根据当前运行环境内存来决定是从 Memory Cache 还是 从Disk Cache中拿
这个是浏览器所决定的 以后更加深入研究
