Server

Code Example

Construct a server object
----
```php
$serv = new swoole_server("127.0.0.1", 9501, SWOOLE_BASE, SWOOLE_SOCK_TCP);
```

Set runtime parameters
----
```php
$serv->set(array('worker_num' => 4, 'daemonize' => true));
```

Register event callback functions
----
```php
$serv->on('Connect', 'my_onConnect');
$serv->on('Receive', 'my_onReceive');
$serv->on('Close', 'my_onClose');
```

Property items
----
```php
$serv->manager_pid;  //PID of the management process, you can send signal SIGUSR1 to make a soft reload
$serv->master_pid;  //PID of the main process, you can send signal SIGTERM to shutdown safely
```

Server Workflow

-----
![Workflow of Swoole extension](http://www.swoole.com/static/uploads/swoole.jpg)

Warning
-----
* Do not execute sleep() in any code as it will block the whole process
* It's dangerous to execute exit or die and it will terminate the worker process
* you can use register_shutdown_function() to catch fatal error while the process terminated abnormally

Example:
```php
register_shutdown_function('handleFatal');
function handleFatal()
{
    $error = error_get_last();
    if (isset($error['type']))
    {
        switch ($error['type'])
        {
            case E_ERROR :
            case E_PARSE :
            case E_DEPRECATED:
            case E_CORE_ERROR :
            case E_COMPILE_ERROR :
                $message = $error['message'];
                $file = $error['file'];
                $line = $error['line'];
                $log = "$message ($file:$line)\nStack trace:\n";
                $trace = debug_backtrace();
                foreach ($trace as $i => $t)
                {
                    if (!isset($t['file']))
                    {
                        $t['file'] = 'unknown';
                    }
                    if (!isset($t['line']))
                    {
                        $t['line'] = 0;
                    }
                    if (!isset($t['function']))
                    {
                        $t['function'] = 'unknown';
                    }
                    $log .= "#$i {$t['file']}({$t['line']}): ";
                    if (isset($t['object']) && is_object($t['object']))
                    {
                        $log .= get_class($t['object']) . '->';
                    }
                    $log .= "{$t['function']}()\n";
                }
                if (isset($_SERVER['REQUEST_URI']))
                {
                    $log .= '[QUERY] ' . $_SERVER['REQUEST_URI'];
                }
                error_log($log);
                $serv->send($this->currentFd, $log);
        }
    }
}
```