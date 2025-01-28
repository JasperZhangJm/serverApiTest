# serverApiTest
接口功能测试

1、整体控件如下：
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/6730286e-9e7a-47c3-94dc-36a0360db324">

2、读取txt文件，该文件是整理的问题集即测试数据：
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/0f93cf99-5962-42cb-afc9-937b929cffe4">

3、生成uuid和时间戳，这里没有用jmeter自带的生成方法，是因为在测试场景中需要记录uuid和时间戳到本地，会发生变化，所以才用了这种方式：
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/2aa87196-081e-44a5-9a02-7366b1a92e09">

4、需要在结果树中生成每个请求的序号，用来对应是那个问题，所以这里生成了序号：
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/ba3d6302-c9b6-43a4-ad7d-0dd708e69cc3">

5、在本地文件中记录了请求和响应两部分数据，在请求部分，记录了请求uuid和请求发送的问题，但要知道当前发送的是第几个问题，这里使用了计数器：
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/be739cbf-f40b-43e6-9599-264da2de3653">

6、这是请求体，这里引用了前面生成的requestNumber
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/7dd50874-8f3d-41fc-9231-d64db8ff68e9">

7、处理响应数据使用了jsr223后置处理程序，没有用beanshell取样器，因为，处理性能原因，前者比后者速度快：
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/d5121ce9-a827-4ef7-9173-4fb83d46fd4d">

8、最后要添加：模块控制器，因为使用测试片段，要使用模块控制器来调用：
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/d9dc734c-6a82-4e41-ab83-3aeaf686e554">
备注：如果测试计划名称被修改，在模块控制器中要重新 找到目标元素。


