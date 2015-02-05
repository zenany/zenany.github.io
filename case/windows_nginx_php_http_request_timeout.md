Window 下 nginx + php http 方式获取 localhost 内容的 bug
========

在做 http 代理时遇到的一个诡异现象。大致如下：


php 以 cgi 形式配在 9000 端口，nginx 配两个 server 分布在 80 & 8081 端口，共享 cgi。

80 端口 : index.php 

  <?php
  file_get_contents('http://localhost:8081/test.php');

8081 端口 : test.php

  <?php
  echo 'hi.'
  
运行 index.php 时，页面会锁住，直到超时。

**原因大致如下：**

nginx + cgi 模式运行 php 时，以单进程、单线程形式处理，处理 index.php 时，会激活 test.php 的处理，然后等待它返回结果。  
但此时 test.php 正在等待 index.php 处理结束，于是就行成了死锁。等 index.php 超时后， test.php 才得到处理。
