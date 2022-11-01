## Account-related API Documentation

* register

  * `POST /account/register/`

  * request:

    ```json
    {
        'username' : 'xuhb20',
        'password' : '123456',
    }
    ```

  * return

    * `"Success", 200`
    * `"Repeated Username" / "Register Error" / "Bad Request", 400`

* login

  * `POST /account/login/`

  * request:

    ```json
    {
        'username' : 'xuhb20',
        'password' : '123456',
    }
    ```

  * return
    * `"Success", 200`
    * `"Username/Password Error"" / "Bad Request", 400`

* logout
  * `POST /account/logout/`