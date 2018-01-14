# TensorflowSharp教程

Tensorflow是一个人工智能框架。TensorflowSharp是对Tensorflow C语言版接口的封装，便于.net开发人员在项目中使用Tensorflow。

## 目录

[01 HelloWorld](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p01_HelloWorld/Program.cs)：TensorflowSharp入门。

[02 UsePlaceholder](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p02_UsePlaceholder/Program.cs)：占位符的使用。

[03 UseVariable](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p03_UseVariable/Program.cs)：变量的使用。

[04 InitVariable](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p04_InitVariable/Program.cs)：变量的初始化。

[05 UseMatrix](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p05_UseMatrix/Program.cs)：矩阵相加、数乘、矩阵相乘。

[p06_LinearRegression](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p06_LinearRegression/Program.cs)：线性回归。

[p07_MNIST](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p07_MNIST/Program.cs)：手写数字识别。

[p08_UseTensor](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p08_UseTensor/Program.cs)：张量的使用。

[p09_GenerateData](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p09_GenerateData/Program.cs)：产生序列、正态分布随机数和随机位置。

[p10_CalculateGradient](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p10_CalculateGradient/Program.cs)：计算倾斜度（偏导数）。

[p11_ReduceMethod](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p11_ReduceMethod/Program.cs)：ReduceMean、ReduceSum计算原理和方法。

[p12_ClipMatrix](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p12_ClipMatrix/Program.cs)：裁剪矩阵（限制矩阵的最小、最大值）。

[p13_BitwiseOperation](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p13_BitwiseOperation/Program.cs)：按位与、按位或、按位异或运算。

[p14_UseStack](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p14_UseStack/Program.cs)：使用堆栈。

[p15_PartialRun](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p15_PartialRun/Program.cs)：部分运行。

[p16_ModelSave](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p16_ModelSave/Program.cs)：保存模型。（未实现）

[p17_TFCoreTest](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p17_TFCoreTest/Program.cs)：TFCore测试。

[p18_TFBufferTest](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p18_TFBufferTest/Program.cs)：TFBuffer测试。

[p19_TFDataTypeTest](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p19_TFDataTypeTest/Program.cs)：TFDataType测试。

[p20_ComparisonOperators](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p20_ComparisonOperators/Program.cs)：比较运算符。

[p22_ConditionalOperators](https://github.com/tengge1/learn-tensorflow-sharp/blob/master/p22_ConditionalOperators/Program.cs)：条件运算符。

## 示例

TensorflowSharp的用法还是很简单的

```C#
// 创建图
var g = new TFGraph();

// 定义常量
var a = g.Const(2);
var b = g.Const(3);

// 加法和乘法运算
var add = g.Add(a, b);
var mul = g.Mul(a, b);

// 创建会话
var sess = new TFSession(g);

// 计算加法
var result1 = sess.GetRunner().Run(add).GetValue();
Console.WriteLine("a+b={0}", result1);

// 计算乘法
var result2 = sess.GetRunner().Run(mul).GetValue();
Console.WriteLine("a*b={0}", result2);

// 关闭会话
sess.CloseSession();
```

执行后输出结果

```
a+b=5
a*b=6
```

## 注意事项

1. 国内目前无法访问Tensorflow官网，但是可以访问谷歌提供的[Tensorflow官网镜像](https://tensorflow.google.cn/)。

2. TensorflowSharp项目使用的.net版本**必须**高于4.6.1，本教程使用的版本是4.7.0，可以在属性选项卡中设置。

3. TensorflowSharp项目必须使用64位CPU，需要在属性选项卡生成中，**去掉首选32位的勾选**。

4. 本教程需要在根目录新建`Libs`文件夹，请将第二步解压出来的`TensorFlowSharp.dll`放在该文件夹；另外运行示例还需要把`libtensorflow.dll`复制到每个项目的`bin/Debug`目录。如果提示找不到Tensorflow命名空间，请重新添加引用。

5. 最新版libtensorflow.dll下载：http://ci.tensorflow.org/view/Nightly/job/nightly-libtensorflow-windows/lastSuccessfulBuild/artifact/lib_package/libtensorflow-cpu-windows-x86_64.zip

## 网站

* Tensorflow官网：http://www.tensorflow.org

* Google Tensorflow镜像：https://tensorflow.google.cn/

* Tensorflow开源项目：https://github.com/tensorflow/tensorflow

* TensorflowSharp开源项目：https://github.com/migueldeicaza/TensorFlowSharp

* TensorflowSharp NuGet主页：https://www.nuget.org/packages/TensorFlowSharp/

* Tensorflow中文社区：http://www.tensorfly.cn/
