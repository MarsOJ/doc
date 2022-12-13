## Info-related API Documentation

* get-latest

  * Description:  从指定id的资讯之后获取5条最近资讯，不指定id或指定空字符串id则默认返回当前时间最近5条资讯

  * URL：`POST /info/get-latest/`

  * Request: 

    ```json
    {
        'lastId' : '65465654651saf'
    }
    ```

  * Return: List of info json, 'id' field is a unique string for each info item

    ```json
    [
        {
            'id' : '6997daf6f47afeaef8',
            'title' : '',
            'source' : '',
            'date' : '' // format: "YYYY-MM-DD HH:mm:ss.mmmmmm"
        },
        {
            ...
        },
        ...
    ]
    ```

* List
  * Description: 分页显示info，其中content显示前20个字符

  * url: `GET /favorite/problem`

  * param:`/?p=&itemPerPage=`
   ```json
    {
       'p':,
       'itemPerPage':,
      //  'id':// if not exists -> default favorite
    }
   ```

  * method: GET   

  * return

    ```json
        [
          {
            'title':,//string
            'id':,//string
            'content': //20-30 characters
            'source':
            'date': '%Y-%m-%d'
          },
          {
          }
        ]
    ```

* details

  * Description: 获取某条资讯的详细信息

  * URL：`GET /info/details/<id>`

  * Return: 

    ```json
    {
        'id' : '6997daf6f47afeaef8',
        'title' : '',
        'content': '',
        'source' : '',
        'date' : '' // format: "YYYY-MM-DD HH:mm:ss.mmmmmm"
    }
    
    ```

* delete

  * Description: 删除某条资讯

  * URL：`DELETE /info/delete`

  * Request:
    
     ```json
     'id':[]//id
     ```
  * return success_num, 200
  
* update
  * Description: 更新某条资讯

  * URL：`POST /info/update`

  * Request:
  ```json
    {
        'id' : '',
        'title' : '',
        'content': '',
        'source' : '',
    }
  ```

  * Return:

    * `"Success", 200`

    * `"Update Error" / "Bad Request", 400`


* insert

  * Description: 新建一条资讯

  * URL: `POST /info/insert`

  * Request:

    ```json
    {
        'title' : '',
        'content': '',
        'source' : '',
    }
    
    ```

  * Return:

    * `"Success", 200`

    * `"Insert Error" / "Bad Request", 400`



管理员查询info个数

* url: `GET /info/count`

* return

  ```json
  {
      'count':4,
  }
  ```

  
