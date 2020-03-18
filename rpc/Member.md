### 用户相关接口

#### 1. 创建用户

##### api:/api/member/createMember

##### method:POST

##### Content-Type:application/json

##### Headers.authorization:[公共AccessToken](/rpc/AccessToken.md)

##### 请求内容实例:

```json
{
  "account":"test1",
  "nickname":"佚名",
  "portrait":"http://www.domain.com/files/86876870.jpg",
  "extras":"{\"member_level\":1,\"member_level_name\":\"普通会员\"}"
}
```

##### 响应内容实例:

```json
{
	"status":200,
 	"msg":"获取成功"
}
```

#### 响应字段注解

|  字段  |  类型  |   名称   |                  描述                  |
| :----: | :----: | :------: | :------------------------------------: |
| status |  int   |  状态码  |       如果为200是成功其他为失败        |
|  msg   | string | 消息反馈 |             用于错误时排错             |

#### SDK代码示例

```php
try{
    $member = new \ImService\Member\Member($accessToken);
    /**
     * 创建用户
     */
    $res = $member->makeMember('aaaa','bbb','hhh',['level'=>1]);
}catch (\Throwable $throwable){
    var_dump("Error:{$throwable->getMessage()}");
}
```