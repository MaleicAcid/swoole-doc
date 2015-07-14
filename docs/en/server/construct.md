swoole_server::__construct
===

swoole_server object constructor

Method
---

```php
public function __construct(
    string $host,
    int $port,
    int $mode = SWOOLE_PROCESS,
    int $sock_type = SWOOLE_SOCK_TCP
)
```

Parameters
---

* string $host

Set `0.0.0.0` to listen to all IP address

* int $port

Set valid number and make sure port is available for use

* int $mode

Available mode
    * SWOOLE_BASE
    * SWOOLE_THREAD
    * SWOOLE_PROCESS
    * SWOOLE_PACKET

* int $sock_type

Available socket type
    * SWOOLE_SOCK_TCP
    * SWOOLE_SOCK_TCP6
    * SWOOLE_SOCK_UDP
    * SWOOLE_SOCK_UDP6
    * SWOOLE_SOCK_UNIX_DGRAM
    * SWOOLE_SOCK_UNIX_STREAM

If you want use ssl just or (|) your current socket type with SWOOLE_SSL

Examples
---

Create TCP Server

```php
$server = new swoole_server(
    "localhost",
    1234,
    SWOOLE_PROCESS
);
```

Create Secure TCP Server

You have to set following swoole_server configuration via [set method](set.md)

```
ssl_cert_file => path/to/ssl_cert_file
ssl_key_file => path/to/ssl_key_file
```

```php
$server = new swoole_server(
    "localhost",
    1234,
    SWOOLE_PROCESS,
    SWOOLE_SOCK_TCP | SWOOLE_SSL
);
```
