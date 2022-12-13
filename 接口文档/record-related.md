## user-related API

* 周榜排行榜：top10 用户名、签名、本周比赛得分（冠军3分，亚军2分...）
   * url: `/record/rank`
   * method: GET
   ```json
   [
       {
         'username':,
         'signature':,
         'score':,
       },
       {
       }
   ]
   ```

   
   
* 个人对战记录，一直往下拖，一次五条
  
   * url: `/record/personal`
   * method: GET/POST
   * request:
      ```json
         'lastID': 'xxx', // 无此字段或为空字符串则为从头开始
      ```
   * return
      ```json
      [
         {
            'id': 'xxx', // 对战记录的唯一id
            'rank':[],
            'scores':[],
            'date':,
         },
         {
            
         }
      ]
      ```
   
   
* 管理员查询对战记录
   * url: /record/all
   * param:`/?p=&itemPerPage=`
       ```json
        {
           'p':,
           'itemPerPage':,
        }
       ```
   * return:
     ```json
      [
         {
            'id': 'xxx', // 对战记录的唯一id
            'rank':[],
            'scores':[],
            'date':,
         },
         {
            
         }
      ]



* 管理员查询对战记录个数
  * url: `GET /record/count`
  * return

      ```json
      {
          'count':4,
      }
      ```