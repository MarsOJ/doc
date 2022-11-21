## Web-Socket API Documentation

url：`/competition`

### 后端接受on

1. 连接
  * url: `/competition/pair`

2. 取消配对
  * url: `/competition/cancel`
  * TODO: 取消

3. 开始发题
  * url: `/competition/start`

4. 接收一个答案
  * url: `/competition/finish`
  * params: problemID, answer
  * answer是一个list，内容是ABCD

5. 确认最后一道题
  * url: `/competition/result`
  * 备注：接收`next`且`lastQuestion`为真，发送

### 后端发送emit

1. 匹配成功准备完毕
   * url: `/competition/prepare`
   * return form:
   ```json
   []	// list of username
   ```

2. 发题
   * url: `/competition/problem`
   * return form:
   ```json
   {
       'problemID':1, // from 0 to n
       'content': 'xxx', // description of the problem
       'type': 0, // 0 单选， 1/2大题
       'time': 30,// 单位：second
       'subproblem': // 单选就一个元素，大题可能5-6个
       [{
           'content':'',//题干，如果为单选题则为空字符串
           'choice':['']//2或4个
   	},
       ],    
   }
   ```

3. 发送答题结果(群发)
   * url:` /competition/answer`
   * return form:
   ```json
   {
       'username':
       'correct':true/false,
       'score': //总分
   }
   ```

4. 下一道题（群发）
   * url: `/competition/next`
   * 注：等三秒发送problem，若为

   ```json
   {
       'lastQuestion':true/false,
   }
   ```

5. 断开连接(前端不用显式emit)

   * url: `/competition/disconnect`

   * 踢出群聊，不等待他的timeout

6. 发送最终结果
  * url: `/competition/result`
  * 备注：接收result后发
  * return form
   ```json
  {
          "points": [
              {"name": "user1", "points": 58},
              {"name": "user2", "points": 40},
              {"name": "user3", "points": 38},
              {"name": "user4", "points": 35},
              {"name": "user5", "points": 12},
              {"name": "user6", "points": 10},
          ],
          "problems": [
              {
                  "num": 1,
                  "id": 12345,
                  "title": "这是一道题目。预计在这里显示题型、正确率、平均分",
                  "points": [10, 5, 10, 10, 6, 3],
              },
              {
                  "num": 2,
                  "id": 12346,
                  "title": "这是一道题目",
                  "points": [7, 10, 7, 10, 7, 10],
              },
              {
                  "num": 3,
                  "id": 12348,
                  "title": "这是一道题目",
                  "points": [0, 10, 0, 0, 5, 0],
              },
          ]
      }
   ```







