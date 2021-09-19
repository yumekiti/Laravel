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

## ライブラリインストール
```
npm install --save laravel-echo socket.io-client
composer require predis/predis
```

front
```
npm install -g laravel-echo-server
```

## config/database.php
```
'redis' => [

        'client' => env('REDIS_CLIENT', 'phpredis'),

        'options' => [
            'cluster' => env('REDIS_CLUSTER', 'redis'),
            // 'prefix' => env('REDIS_PREFIX', Str::slug(env('APP_NAME', 'laravel'), '_').'_database_'),    '' に変更
            'prefix' => env('REDIS_PREFIX', ''),
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
docker-compose -f ./docker/docker-compose.yml exec php /bin/bash -c "php artisan make:event TestEvent"
```

## app/Events/TestEvent.php
```
class TestEvent implements ShouldBroadcast
```

## package.json
```
-    "socket.io-client": "^4.1.2",
+    "socket.io-client": "^2.4.0",
```