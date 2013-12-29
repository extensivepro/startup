# How to collaboration


介绍如何采用BDD(Behavior-driven development)行为驱动开发的方式实现多人协作开发。适用异构（NodeJS/iOS)系统、同种语言（NodeJS/Angular）等多种情况。

## 协议
约定前后端较好的具体形式和标准的全部细节。考虑用户管理的交互协议：

### 新增用户
#### 请求
##### POST /users
```json  
{
    "createdAt": "2013-12-31", 
    "password": "123456", 
    "username": "gbo@extensivepro.com"
}
```
#### 响应

##### 200 OK

```json  
{
    "createdAt": "2013-12-31", 
    "displayName": "gbo", 
    "email": "gbo@extensivepro.com", 
    "password": "123456", 
    "roles": [
        "admin", 
        "user"
    ], 
    "updateAt": "2013-12-31", 
    "username": "gbo@extensivepro.com"
}
```

#### 400 Bad Request
* `username` - is required
* `password` - is required

## BDD脚本
* [Mocha](https://github.com/visionmedia/mocha) - 一套测试框架，用了描述协议中的需求。
* [Should.js](https://github.com/visionmedia/should.js) - 用行为预期的方式保证代码符合协议的要求。
* [Request](https://github.com/mikeal/request) - 简单好用的Http客户端封装。

```javascript  
var request = require('request')
var should = require('should')

describe('# POST /users', function(){
  it('should success create user', function(done){
    var options = {
      url: 'http://your.host/users'
      json: {
        "createdAt": "2013-12-31", 
        "password": "123456", 
        "username": "gbo@extensivepro.com"
      }
    }
    request(options, function(error, ressponse, body){
      should.not.exist(error)
      response.statusCode.should.equal(200)
      done()
    })
  })
  
  it('should failure due to no password', function(done){
    var options = {
      url: 'http://your.host/users'
      json: {
        "createdAt": "2013-12-31", 
        "username": "gbo@extensivepro.com"
      }
    }
    request(options, function(error, ressponse, body){
      should.not.exist(error)
      response.statusCode.should.equal(400)
      body.should.equal('password is required')
      done()
    })
  })
})
```

## 应用程序


`router.js`
---
```javascript
var users = require('../app/controllers/users')
app.post('/users', users.create)
```

`users.js`
---
```javascript  
var mongoose = require('mongoose')
  , User = mongoose.model('User')

/**
 * Create user
 */

exports.create = function (req, res) {
  if(!req.body.username) return res.send(400, 'username is required')
  if(!req.body.password) return res.send(400, 'password is required')
  
  var user = new User(req.body)
  user.save(function (err) {
    if (err) {
      return res.send(400, err.errors)
    }
		if(req.query.login) {
	    req.logIn(user, function(err) {
	      if (err) return next(err)
	      return res.json({_id:user.id});
	    })
		} else {
			return res.json({_id:user.id});
		}
  })
}
```

