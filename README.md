# Alan.LargeFileUpload
利用JavaScript(主要是FileReader对象)实现大文件异步上传, 支持断点续传. 项目后台代码使用C#完成, 其他语言也可以, 主要代码量在JavaScript(SeperateFile.js)里面.

### 项目简单描述
SeperateFile.js 文件实现分割文件, 并放到队列(queues)里, 队列里的每一小块文件都有状态标识(unsend, sending, sent), 这个状态有两个作用, 1: 使数据发送时按照顺序上传的, 这样可以减轻服务器端逻辑代码. 2: 用于实现断点续传.

后台代码的逻辑很简单, 主要步骤:

	* 接收Ajax发送过来的base64字符串, 然后将base64转换成字节数组.
	* 根据客户端传来的文件名标识(fileName), 往文件里追加数据(如果是第一次请求, 文件不存在, 需要先创建一个同名的空文件).
	* 没了

后台代码极其简单, 其他语言PHP/Java很容易就实现.

项目的Screentshot文件夹有几张运行截图.


