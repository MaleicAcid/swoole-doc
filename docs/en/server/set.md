swoole_server::set
===

Set swoole_server configuration

Method
---

```php
public function set(array $setting);
```

Parameters
---

* array $setting

Provide `["option" => "value"]` array

Available Options
---

* reactor_num => int

`reactor_num` must be less or equal than `worker_num` otherwise swoole will automatically adjust `reactor_num` same as `worker_num`

* worker_num => number

Number of worker process, each process takes up to `40M` of memory and maximum process is `100`

* max_request => int

Set maximum request of worker process. Worker will automatically restarted after take request equal to max_request. This parameter is to prevent PHP memory overflow. Set 0 if you dont want worker automatically restarted but it will result memory overflow.

* max_conn => int

Set max connection that allow to access swoole. Swoole will reject new request if amount of connection equal with `max_conn` param.

* task_worker_num => int

Set number of worker for task function

* task_ipc_mode => int

Set communication process between task and worker process

    * 1 => using unix socket
    * 2 => use message queue
    * 3 => use message queue and scramble it

* task_max_request => int

Set maximum task per worker, worker will restarted when receive number of request equal with `task_max_request`

* task_tmp_dir => string

Set directory for temporary task data.

* dispatch_mode => int

Incoming request distribution policy.

    * 1 => round robin mode
    * 2 => fixed mode, every request served by same worker
    * 3 => least busy modey, request will be assigned to the least busy worker

`dispatch_mode` can't be used when swoole running as `SWOOLE_BASE`
