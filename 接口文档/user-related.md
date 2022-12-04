1. 获取基本信息：用户名、总积分、参与场次、pk胜场次、胜率、答题次数、正确题数、正确率、等级、是否为管理员

2. 改密码(account-related.md)

   ```json
   {
       'oldPassword':
       'newPassword':
   }
   ```

3. 上传头像

4. 获取头像

   return url_str，200

5. 修改签名

   ```json
   {
       'signature':,
   }
   ```

6. 周榜排行榜：top10 用户名、签名、本周比赛得分（冠军3分，亚军2分...）

   ```json
   [
       {'username':,
        'signature':,
        'score':,
       },
       {
       }
   ]
   ```

7. 个人对战记录，一直往下拖，一次五条

   ```json
   [
       {
           'rank':[],
           'date':,
   	},
       {
           
       }
   ]
   ```

8. 管理员查询对战记录

   同上