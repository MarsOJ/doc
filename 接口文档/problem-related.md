## problem-related API

* 增
    * url: `/question/insert/`
    * method: POST
    * request
        ```json
        {
            'classification': 1,
            'content': '判断以下命题',
            'code':'```C++\n#include <cstdlib>\n...\n```'
            'answer':['B','C', 'A'],
            'explanation':'hk for .hk, us for .us, cn for .cn',
            'subproblem':[
                {'content':'香港的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
                {'content':'美国的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
                {'content':'中国的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
            ],
            'source': 'CSP-J',
            'difficultyInt':1,
        }
        ```

2. 删（批量）
    * url: `/question/delete/`
    * method: DELETE
    * request
        ```json
        {
            'problemID':[]
        }
        ```
    * return: success_num, 200

3. 改
    * url: `/question/update/`
    * method: POST
    * request:
        ```json
        {
            'id': '123fgg',
            'content': '判断以下命题',
            'code':'```C++\n#include <cstdlib>\n...\n```'
            'answer':['B','C', 'A'],
            'explanation':'hk for .hk, us for .us, cn for .cn',
            'subproblem':[
                {'content':'香港的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
                {'content':'美国的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
                {'content':'中国的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
            ],
            'source': 'CSP-J',
            'difficultyInt':1,
        }
        ```
4. 查
    * url: `/question/details/<id>`
    * method: GET
    * return:
        ```json
        {
            'id': '123fgg',
            'content': '判断以下命题',
            'code':'```C++\n#include <cstdlib>\n...\n```'
            'answer':['B','C', 'A'],
            'owner':'xxx',
            'submit_date':'%Y-%m-%d',
            'last_modified_date' :'%Y-%m-%d',
            'explanation':'hk for .hk, us for .us, cn for .cn',
            'subproblem':[
                {'content':'香港的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
                {'content':'美国的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
                {'content':'中国的顶级域名是：', 'choice':['.cn','.hk','.us','.com']}, 
            ],
            'source': 'CSP-J',
            'difficultyInt':1,
        }
        ```

5. 缩略显示所有题目

   * url: `GET /question/list`

   * param:`/?p=&itemPerPage=`
      ```json
       {
          'p':,
          'itemPerPage':,
       }
      ```
      
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

管理员查询题目个数

* url: `GET /question/count`
* return

  ```json
  {
      'count':4,
  }
  ```