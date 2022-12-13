## Account-related API Documentation

* register

  * Description:  用户注册

  * URL：`POST /account/register/`

  * Request:

    ```json
    {
        'username' : 'xuhb20',
        'password' : '123456',
    }
    ```

  * Return

    * `"Success", 200`
    * `"Repeated Username" / "Register Error" / "Bad Request", 400`

  

* login

  * Description:  用户登录

  * URL：`POST /account/login/`

  * Request:

    ```json
    {
        'username' : 'xuhb20',
        'password' : '123456',
    }
    ```

  * Return
    * `"Success", 200`
    * `"Username/Password Error / "Bad Request", 400`

  

* logout
  
  * Description:  退出登录
  * URL：`POST /account/logout/`
  * Return
    * `Success, 200`

* state
  * Description:  查询用户登录状态
  * URL：`GET /account/state/`
  * Return
    * `<username>, 200`
    * `"Not Logged In", 400`



* change-password

  * Description:  用户修改密码

  * URL：`POST /account/change-password`

  * Request:

    ```json
    {
        'username' : 'xuhb20',
        'password' : '123456',
        'newPassword' : '987654'
    }
    ```

  * Return 

    * `"Success", 200`
    * `"Username/Password Error" / "Change Password Error" / "Bad Request", 400`

  

* delete

  * Description:  删除一个用户（销户而非注销）

  * URL：`DELETE /account/delete/`

  * Request:

    ```json
    {
        'username' : 'xuhb20',
        'password' : '123456',
    }
    ```

  * Return

    * `"Success", 200`
    * `"Username/Password Error" / "Delete User Error" / "Bad Request", 400`


* 获取基本信息：用户名、总积分、参与场次、pk胜场次、答题次数、正确题数、等级、是否为管理员、个人签名
   * url: /account/info
   * method: GET
   * request:
      ```json
      {
         'username':,
         'credit':,
         'totalCompetitionsNum':,
         'victoriesNum':,
         'totalAnswersNum':,
         'correctAnswersNum':,
         'authority': False,//是否为管理员
         'slogan':'', //个人签名
         'profile':'',
      }
      ```

* 改密码(account-related.md)
   * url: /account/change-password
   * method: POST
   * request:
      ```json
      {
         'password':
         'newPassword':
      }
      ```

* 上传头像
   * url: /account/profile
   * method: POST
   * request
   ```json
   {
      'profile':''//base64
   }
   ```

* 获取头像
   * url: /account/profile
   * method: GET
   * return base64，200

* 修改签名
   * url: /account/signature
   * method: POST
   * request:
      ```json
      {
         'signature':,
      }
      ```
