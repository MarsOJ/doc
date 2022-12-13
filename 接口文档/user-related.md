## user-related API
1. 获取基本信息：用户名、总积分、参与场次、pk胜场次、答题次数、正确题数、等级、是否为管理员、个人签名
   * url: /account/info
   * method: GET
   * request:
      ```json
      {
         'username':,
         'credits':,
         'totalCompetitionsNum':,
         'victoriesNum':,
         'totalAnswersNum':,
         'correctAnswersNum':,
         'authority': False,//是否为管理员
         'slogan':'', //个人签名
      }
      ```

2. 改密码(account-related.md)
   * url: /account/change-password
   * method: POST
   * request:
      ```json
      {
         'password':
         'newPassword':
      }
      ```

3. 上传头像
   * url: /account/profile
   * method: POST
   * request
   ```json
   {
      'profile':''//base64
   }
   ```

4. 获取头像
   * url: /account/profile
   * method: GET
   * return base64，200

5. 修改签名
   * url: /account/signature
   * method: POST
   * request:
      ```json
      {
         'signature':,
      }
      ```

6. 周榜排行榜：top10 用户名、签名、本周比赛得分（冠军3分，亚军2分...）
   * url: /record/rank
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

7. 个人对战记录，一直往下拖，一次五条
   * url: /record/personal
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
            'date':,
         },
         {
            
         }
      ]
   ```

8. 管理员查询对战记录
   * url: /record/all
   * note: 其余同个人对战记录