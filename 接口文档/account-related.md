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