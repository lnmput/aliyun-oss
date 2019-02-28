# Flysystem Adapter for Aliyun OSS.

This is a Flysystem adapter for the Aliyun OSS ~2.0.4


## Installation

```bash
composer require apollopy/flysystem-aliyun-oss
```

## for Laravel

edit the config file: config/filesystems.php

add config

```php
'oss' => [
    'driver'     => 'oss',
    'access_id'  => env('OSS_ACCESS_ID','your id'),
    'access_key' => env('OSS_ACCESS_KEY','your key'),
    'bucket'     => env('OSS_BUCKET','your bucket'),
    'endpoint'   => env('OSS_ENDPOINT','your endpoint'),
    'prefix'     => env('OSS_PREFIX', ''), // optional
    'url'        => env('OSS_URL'),
],
```

change default to oss

```php
    'default' => 'oss'
```

## Use

see [Laravel wiki](https://laravel.com/docs/5.7/filesystem)

## Plugins

inspire by https://github.com/apollopy/flysystem-aliyun-oss

```php
Storage::disk('oss')->putFile($path, '/local_file_path/1.png', ['mimetype' => 'image/png']);
Storage::disk('oss')->signedDownloadUrl($path, 3600, 'oss-cn-beijing.aliyuncs.com', true);
Storage::disk('oss')->url($path);
```
