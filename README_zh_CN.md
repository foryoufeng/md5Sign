# md5Sign
## 这是一个md5加密算法

> 使用md5算法来验证和给数据加上签名，从而使不同语言如php,java,js之间进行api之间的相互通讯

## 安装

通过加入 `composer.json` 或者在命令行中输入:

```
composer require foryoufeng/md5Sign
```

## 基本用法

对你的数据进行签名
```php
use Foryoufeng\Md5Sign\Md5Utils;

$api_key='123456';//秘钥可以从数据库或者.env或者config.php等配置文件中获取
$data=[
    'user_id'=>1,
    'name'=>'wuqiang'
];
$data=Md5Utils::sign($data,$api_key);
var_dump($data); //查看数据
```

验证数据

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
