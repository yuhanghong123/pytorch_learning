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

7. ```python
   python -m torch.distributed.launch --nnodes=1 --node_rank=0 --nproc_per_node=8 --master_addr="127.0.0.1" --master_port=29501 main.py --cfg </path/to/config> --batch-size 128 --data-path </path/of/dataset> --output /tmp
   ```

   使用分布式PyTorch进行训练。

   `python -m torch.distributed.launch`：使用 PyTorch 的分布式启动工具启动训练脚本。

   `--nnodes=1`：指定总共的节点数为1（单节点训练）。

   `--node_rank=0`：指定当前节点的排名（对于单节点训练，总是0）。

   `--nproc_per_node=8`：在每个节点上启动的进程数（这里是8个进程）。

   `--master_addr="127.0.0.1"`：主节点的地址（单节点情况下是本地地址）。

   `--master_port=29501`：主节点的端口号。

   `main.py`：要运行的主训练脚本。

   `--cfg </path/to/config>`：配置文件路径（你需要替换为实际路径）。

   `--batch-size 128`：批处理大小。

   `--data-path </path/of/dataset>`：数据集路径（你需要替换为实际路径）。

   `--output /tmp`：输出目录。

8. 