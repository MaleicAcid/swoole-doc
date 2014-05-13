swoole_server::__construct
----

create the swoole_server object

```php
$serv = new swoole_server(string $host, int $port, int $mode = SWOOLE_PROCESS,
    int $sock_type = SWOOLE_SOCK_TCP);

$serv = swoole_server_create(string $host, int $port, int $mode = SWOOLE_PROCESS,
    int $sock_type = SWOOLE_SOCK_TCP);
```

* $host, the listen host, e.g, "127.0.0.1", "0.0.0.0"
* $port, the listen port, e.g, 9501 


