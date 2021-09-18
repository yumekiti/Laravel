# laravel-echo

## docker-compose
コメントアウト消す

## env
```
BROADCAST_DRIVER=redis
CACHE_DRIVER=file
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379
```

## config/database.php
```
'redis' => [

        'client' => env('REDIS_CLIENT', 'phpredis'),

        'options' => [
            'cluster' => env('REDIS_CLUSTER', 'redis'),
            // Str::slug(env('APP_NAME', 'laravel'), '_').'_database_' を '' に変更
            'prefix' => env('REDIS_PREFIX', ''),
        ],

        'default' => [
            'url' => env('REDIS_URL'),
            'host' => env('REDIS_HOST', '127.0.0.1'),
            'password' => env('REDIS_PASSWORD', null),
            'port' => env('REDIS_PORT', '6379'),
            'database' => env('REDIS_DB', '0'),
        ],

        'cache' => [
            'url' => env('REDIS_URL'),
            'host' => env('REDIS_HOST', '127.0.0.1'),
            'password' => env('REDIS_PASSWORD', null),
            'port' => env('REDIS_PORT', '6379'),
            'database' => env('REDIS_CACHE_DB', '1'),
        ],

    ],
```

## config/app.php
```
// App\Providers\BroadcastServiceProvider::class,
```
コメントアウト消す

## make
```
make:event TestEvent
```

## app/Events/TestEvent.php
```
class TestEvent implements ShouldBroadcast
```