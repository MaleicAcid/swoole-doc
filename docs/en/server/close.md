swoole_server::close
----
Close client connection, the function prototype:

```php
bool swoole_server::close(int $fd, int $from_id = 0);
```
> swoole-1.6 or later do not need $ from_id swoole-1.5.8 version below, be sure to pass the correct $ from_id, it may cause connection leaks

The operation was successful returns true, failure to return false. 
