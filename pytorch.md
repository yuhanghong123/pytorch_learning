# Torch随笔

1. 分类任务和回归任务的区别：分类任务是对离散值的预测、回归任务是对连续值的预测

2. @staticmethod：Python 中的一个装饰器，用于将一个方法转换为静态方法。静态方法是不依赖于类实例的方法，可以直接通过类名调用。

3. ```python
   parser = argparse.ArgumentParser('Swin Transformer training and evaluation script', add_help=False)
   ```

   表示创建ArgumentParser对象，解析命令行参数的类。在这个例子中，我们为这个对象指定了一个描述（'Swin Transformer training and evaluation script'），以及一个add_help参数，设置为False，表示在解析命令行参数时不会自动添加一个帮助选项。这个ArgumentParser对象将用于解析命令行参数，例如在训练和评估Swin Transformer模型时可能需要的参数。在后续的代码中，我们可以使用add_argument()方法向这个ArgumentParser对象添加所需的参数。

4. ```python
   args, unparsed = parser.parse_known_args()
   ```

   用于解析命令行参数，并将解析结果存储在args对象中。

5. ```python
   config = get_config(args)
   ```

   将命令行参数解析并转换成配置信息

6. 编写主函数时，可以将传参过程写成函数形式

7. 