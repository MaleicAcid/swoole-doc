Create a child process
```php
int swoole_process::__construct(mixed $function, $redirect_stdin_stdout = false, $create_pipe = true);
```

* `$function`，This function will be executed after the child process is created
* If you want to change the function executed, you can assign the new function to the object's `callback` attribute
* `$redirect_stdin_stdout`，redirects the standard input and output of the child process。When this option is enabled, instead of printing the information on the screen,`echo()` will  write it to the pipe. Reading the keyboard input will change to read data from the pipe. The default read mode is blocking read.
* `$create_pipe`，whether to create a pipe.It will be forced to `true` if $ redirect_stdin_and_stdout is enabled.
If there is no need for communication in the child process, it can be set to `false`

> $Process object will automatically shut down the pipeline when it is destroyed. If you listen to the pipeline process will receive CLOSE event

> After the 1.7.22 version, the parameter `$create_pipe` is of type int and allows you to set the type of pipe, with a default value of 1:
```php
int swoole_process::__construct(mixed $function, $redirect_stdin_stdout = false, $create_pipe = 1);
```
> When the parameter `$create_pipe` is less than or equal to 0, the pipe will not be created

> When the parameter `$create_pipe` is 1, the pipe type will be set to `SOCK_STREAM`

> When the parameter `$create_pipe` is 2, the pipe type will be set to `SOCK_DGRAM`

> It will be forced to `1` if $redirect_stdin_and_stdout is enabled.

> In addition:
> After 1.9.6-stable 			        The default value for the `$create_pipe` is `2`.And it will be forced to `1` if $redirect_stdin_and_stdout is enabled.

> from 1.8.3-stable to 1.9.5-stable		The default value for the `$create_pipe` is `2`.And it will be forced to `2` if $redirect_stdin_and_stdout is enabled.

> from 1.7.22-stable to 1.8.2			The default value for the `$create_pipe` is `1`.And it will be forced to `1` if $redirect_stdin_and_stdout is enabled.


Create swoole_server in child processes
----
You can use the swoole_server program in the child process created by swoole_process.For security reasons, you must call $worker-> exec to execute the server code after using $process-> start to create the process.

```php
<?php
$process = new swoole_process('callback_function', true);
$pid = $process->start();

function callback_function(swoole_process $worker)
{
    $worker->exec('/usr/local/bin/php', array(__DIR__.'/swoole_server.php'));
}

swoole_process::wait();
``` 
