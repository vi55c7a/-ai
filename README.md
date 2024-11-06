完全云端运行：使用谷歌CoLaboratory训练神经网络



谷歌允许使用其服务器上的一台 linux 虚拟机，这样你可以访问终端为项目安装特定包。如果你只在代码单元中输入 !ls 命令（记得命令前加!），那么你的虚拟机中会出现一个 datalab 文件夹。

![2024-11-06](https://github.com/user-attachments/assets/694e3ba5-9c5a-4699-997d-956c60d0469b)


我们的任务是将数据集放置到该机器上，这样我们的 notebook 就可以访问它

![2024-11-06 (1)](https://github.com/user-attachments/assets/5a52089d-dafc-418b-bf4e-87dcef8395fc)


输入 !ls 命令，检查机器上是否有该文件。你将看到 datalab 文件夹和 breast_cancer_data.csv 文件。

![2024-11-06 (2)](https://github.com/user-attachments/assets/5636e752-f424-4b04-af61-c9bc87d7f0a9)


数据预处理：

现在数据已经在机器上了，我们使用 pandas 将其输入到项目中。

![2024-11-06 (3)](https://github.com/user-attachments/assets/69a3348a-c041-4e28-9a5f-9907e88f6c52)


CoLaboratory 上的输出结果图示。

现在，分割因变量（Dependent Variables）和自变量（Independent Variables

![2024-11-06 (4)](https://github.com/user-attachments/assets/f520cae5-df7d-4c00-8c9a-7419b49adb01)


Y 包含一列，其中的「M」和「B」分别代表「是」（恶性）和「否」（良性）。我们需要将其编码成数学形式，即「1」和「0」。可以使用 Label Encoder 类别完成该任务。

![2024-11-06 (5)](https://github.com/user-attachments/assets/f57f46f7-9db6-4559-808e-4f44cd8a51f4)


现在数据已经准备好，我们将其分割成训练集和测试集。在 Scikit-Learn 中使用 train_test_split 可以轻松完成该工作。

![2024-11-06 (6)](https://github.com/user-attachments/assets/fdd19086-1fd1-493d-b2c5-d24574ff8ce8)

安装 Keras：

![2024-11-06 (7)](https://github.com/user-attachments/assets/e03c5ef8-cedf-4a38-bf8b-fb9c4d3620d7)


我们需要定义三个基本参数：units、kernel_initializer 和 activation。units 参数定义每层包含的神经元数量。Kernel_initializer 定义神经元在输入数据上运行时的初始权重

运行人工神经网络，发生反向传播。你将在 CoLaboratory 上看到所有处理过程，而不是在自己的电脑上。

这里 batch_size 是你希望同时处理的输入量。epoch 指数据通过神经网络一次的整个周期。它们在 Colaboratory Notebook 中显示如下：


![image](https://github.com/user-attachments/assets/a379ca69-b0e3-4b84-b8bf-10ef547ff43e)


进行预测，构建混淆矩阵

![image](https://github.com/user-attachments/assets/3bfeda89-3b22-4046-9b06-63296ee7875e)




