# rokidos-cli

为`RokidOS`极客们量身打造的命令行工具，主要用于安装、构建、测试以及发布你的`RokidOS`应用。

```sh
Usage: rokid/ro [command]

ro help                 Get helps
ro devices              List connected devices
ro run [file]           Run scripts on device
ro shell <command>      Wait for an connectable device and shell
ro test <dir>           Run tests on your device
ro log <filter>         Show the logs of connected device by comma-based filter
ro install <dir>        Install the Rokid App from directory
ro build <dir>          Build the Rokid App to .rpp

rokid@${VERSION}
```

### 如何安装

我们通过`npm`提供该工具包，因此确保你成功安装了`Node.js`环境后：

```sh
$ npm install rokidos-cli -g
```

### 已支持命令

在该章节，我们将会介绍一些基本用法。

##### 应用相关

使用下面的命令可以在本地构建命令

```sh
$ ro build ./
```

然后使用`ro install`安装到设备中。

##### 脚本运行

```sh
$ ro run /path/to/your/js/file
```

上述命令会将你电脑中的脚本推到设备中的临时文件夹，再运行该文件

##### shell

使用`ro shell`可以直接进入设备终端

##### 测试

测试你的应用，首先你需要在当前目录下创建一个`tests`目录，然后在测试脚本中的代码样例如下：

```js
test('test voice play', (t) => {
  t.send(<asr>, <nlp>, <action>);
  t.assert(<event>, <value>, (data) => {
    // got event
    t.done();
  });
});
```

##### 日志

使用如下命令可以输出所有日志：

```sh
$ ro log
```

如果想输出特定进程的日志，则：

```sh
$ ro log ams
```

一般调试应用查看日志可以使用：

```sh
$ ro log ams,zygote
```

会输出所有`ams`以及应用进程的日志。

### 授权

Rokid, Inc @ Copyright
