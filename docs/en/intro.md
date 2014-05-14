Swoole Project
==============

Swoole is a PHP extension written in C, and can be used to develop high-performance concurrent TCP/UDP server with PHP. It utilized a full asynchronous, non-blocking epoll/kqueue event loop for networking I/O and running its business logic part in synchronous multiprocess blocking paradigm. By taking this structure Swoole can handle both the high concurrency TCP connect as well as making it easier to code the business logic.

> The asynchronous feature has been added to Swoole since version 1.6.2. One can code asynchronous callback functions with Swoole, just like node.js now.

But Swoole is more powerful than Node.js, It support both sync/async code, builtin multiprocess, and has provided the life cycle management of processes along with memory protection mechanism. Developers are not required to know the mechanism behind the scene and can be focused on building applications and business logic.

Swoole is an Open Source software and Licensed in Apache 2.0. Any enterprises and developers can use the code of Swoole for free and choose not to distribute the modified code based on Swoole.

Related Projects
----------------

* [swoole_framework](https://github.com/matyhtf/swoole_framework) An industrial grade web server written in pure PHP code, based on swoole extension, which has good performance.
* [zphp](https://github.com/shenzhe/zphp) A lightweight server-side developing framework designed for game, social network and mobile pages, providing real time high performance communication solution. It uses swoole as low-level networking communication.
* [EPServer](https://github.com/ewenlaz/epserver) A high performance TCP server framework based on Swoole.
* [php-webserver](https://github.com/matyhtf/php-webserver) A high performance PHP web server based on swoole and http_parser, twice faster than php-fpm in our pressure test.
* [zchat](https://github.com/shenzhe/zchat) A realtime web chat system based on zphp framework and swoole.
* [WebSocket & WebIM](https://github.com/matyhtf/swoole_framework)
* [SOA服务器](https://github.com/matyhtf/swoole_framework)
* [swoole-ide-auto-complete](https://github.com/EagleWu/swoole-auto-complete) You can use this code fragment to make your IDE/Editor recognize the classes, functions and macroes of Swoole which also can be used on auto completing function names.
* [PHPWebIM](https://github.com/matyhtf/phpwebim) A websocket web chat system based on Swoole.
* [PHP-ftp-server](https://github.com/matyhtf/phpwebim) A high performance FTP server based on Swoole. It features active/passive mode and virtual directory. It has good performance and can be used in production environment.
* [Upload-Server](https://github.com/matyhtf/swoole/blob/master/examples/server/upload_server.php) A high performance TCP file uploading server based on Swoole using full asynchronous, non-blocking multiprocess paradiam, which can serve up to 10000 connections on uploading files.
* [swoole_flash_game](https://github.com/matyhtf/swoole_flash_game) A Flash game based on Swoole, can take realtime interaction to server.

Donate to Swoole
----------------

Your donations are the biggest encouragement for the continuous development of Swoole. We will presist in maintaining this project and your donations will used in these field:

continuous development of Swoole;
the build and maintenance of its document and community;

If you want to donate this project, click:

> !!!此处应有PayPal!!!

The community
-------------

You can join the Swoole QQ Group(321637118) to communicate whit developers and users of swoole and can open an issue or ask for solutions on [Swoole Community](http://group.swoole.com/)  
Google Mail list: swoole@googlegroups.com
> !!!此处还应该有IRC!!!