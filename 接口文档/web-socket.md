## Web-Socket API Documentation

url：/competition

接受on

1. 连接

   url: pair

2. 取消配对

   url: cancel

   TODO: 取消

3. 开始发题

   url: start

4. 接收一个答案

   url: finish

   params: problemID, answer


​			answer是一个list，内容是ABCD
​	5.result

​		url: result	

​        备注：接收`next`且`lastQuestion`为真，发送



发送emit

1. 匹配成功准备完毕

   url: prepare

   form:

   ```
   []	// list of username
   ```

2. 发题

   url: problem

   form:

   ```json
   {
       'problemID':1, // from 0 to n
       'content': 'xxx', // description of the problem
       'type': 0, // 0 单选， 1/2大题
       'time': 30,// 单位：second
       'subproblem': // 单选就一个元素，大题可能5-6个
       [{
           'content':'',//题干
           'choice':['']//2或4个
   	},
       ],    
   }
   ```

3. answer(群发)

   form:

   ```json
   {
       'username':
       'correct':true/false,
       'score': //总分
   }
   ```

4. next（群发）

   注：等三秒发送problem，若为

   ```json
   {
       'lastQuestion':true/false,
   }
   ```

   

5. disconnect


​		踢出群聊，不等待他的timeout



6.result

​	备注：接收result后发

```json
详见program.py
```







