Swoole User Document
====

swoole_server
----
* Function List
    * [swoole_server::__construct](server/construct.md)
    * [swoole_server::set](server/set.md)
    * swoole_server::on
    * swoole_server::handler
    * swoole_server::start
    * swoole_server::addlistener
    * swoole_server::addtimer
    * swoole_server::send
    * swoole_server::sendfile
    * [swoole_server::close](server/close.md)

* Event Callback
    * onConnect
    * onReceive
    * onClose
    * onTask
    * onFinish
    * onTimer

swoole_client
-----
* Function List
    * swoole_client::__construct
    * swoole_client::on
    * swoole_client::connect
    * swoole_client::send
    * swoole_client::recv
    * swoole_client::close
    * swoole_client::$errCode

* Event Callback
    * onConnect
    * onReceive
    * onError
    * onClose

swoole_event
-----
* swoole_event_add
* swoole_event_set
* swoole_event_del
* swoole_event_wait

swoole_async
-----
* swoole_async_read
* swoole_async_write
* swoole_async_readfile
* swoole_async_writefile
* swoole_async_dns_lookup

swoole_lock
-----

