# md5Sign
## A MD5 encryption algorithm/一个md5加密的签名算法

 [中文文档](./README_zh_CN.md "中文文档")
 
> MD5 algorithm is used to verify and add data to the data, so that different languages, such as PHP, Java and JS, can communicate with each other between API.

## Installation

Require this package in your `composer.json` or install it by running:

```
composer require foryoufeng/md5Sign
```

## Basic Usage
to sign your data
```php
use Foryoufeng\Md5Sign\Md5Utils;

$api_key='123456';//you can get it from your database or .env file or config.php and so on
$data=[
    'user_id'=>1,
    'name'=>'wuqiang'
];
$data=Md5Utils::sign($data,$api_key);
var_dump($data); //you can see what it is look like
```

to verify your data

```php
use Foryoufeng\Md5Sign\Md5Utils;

$sign=[
    'user_id'=>1,
    'name'=>'wuqiang',
    'timeStamp'=>1523519147,
    'sign'=>'4d02bfa8bcbcfb88f99a98e05aa75b33',
];
$flag=Md5Utils::verify($sign,$api_key);
var_dump($flag);
```