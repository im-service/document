### 授权相关接口

#### 1. AccessToken
##### api:/api/auth/getAccessToken
##### method:POST
##### Content-Type:application/json
##### 请求内容实例:
```json
{
  "appid":"ieua1o00imm5mhx",
  "secret":"8920depfr4pzqz3"
}
```
##### 响应内容实例:
```json
{
	"status":200,
	"token":"ieua1o00imm5mhxieua1o00imm5mhxieua1o00imm5mhx",
	"expire":"2020-03-01 23:20:01",
 	"msg":"获取成功"
}
```
#### 响应字段注解
字段|类型|名称|描述
:--:|:--:|:--:|:--:
status|int|状态码|如果为200是成功其他为失败
token|string|授权|用于Api公共头部的`authorization`字段
expire|string|过期时间|格式为`YYYY-MM-DD HH:II:SS` 格式的时间
msg|string|消息反馈|用于错误时排错
#### SDK代码示例
```php
/**
 * 缓存
 */
$cacheDriver = new \Doctrine\Common\Cache\FilesystemCache('./cacheDir');
/**
 * 实例化授权
 */
$accessToken = new \ImService\AccessToken('http://127.0.0.1:9501', 'ieua1o00imm5mhx', '8920depfr4pzqz3');
/**
 * 设置缓存
 */
$accessToken->setCache($cacheDriver);
/**
 * 获取字符串token
 */
//$token = $accessToken->getTokenString();
```