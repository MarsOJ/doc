## Favorite-related API Documentation

### 题目

* 缩略题目

  * url: `/favorite/problem`

  * param:`/?p=&itemPerPage=&id=`
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
            'type': //
            'date':
          },
          {
          }
        ]
    ```

* 题目移动

  * method: PUT

  * request

    ```json
    {
        'sourceID':'',
        'destID':'',
        'problemID':[],
        'delete': true/false, //
    }
    ```

* 题目删除

  * method: DELETE

  * request

    ```json
    {
        'sourceID':'',
        'problemID':[],
    }
    ```

  * return

  ```json
    [success_num, notfound_num, failed_num]
  ```

* 题目增加

  * method: POST

  * request

    ```json
    {
        'destID':'',
        'problemID':[],
    }
    ```

  * return

    ```json
   [success_num, repeated_num, failed_num]
    ```



### 收藏夹

* 收藏夹增加

  * url: `/favorite/list`
  * method: POST
  * request

  ```json
  {
      'name':
  }
  ```

  * return 200,400

* 收藏夹删除

  * method: DELETE

  * request

    ```json
    {
        'id':
    }
    ```

* 收藏夹改名

  * method: PUT

  * request

    ```json
    {
        'id':
        'newName':
    }
    ```

* 收藏夹查看

  * method: GET

  * return

    ```json
    [
        {
            'id':,
            'name':,
            'default':true/false,
        }
    ]
    ```

  ```

  
