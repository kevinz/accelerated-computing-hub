# Python GPU 开发入门教程

**欢迎参加 Python GPU 开发入门教程。**

自从加入 NVIDIA 以来,我逐渐掌握了在 Python 中编写加速代码的基础知识。令我惊讶的是,我不需要学习 C++,也不需要新的开发工具。如今在 Python 中编写 GPU 代码比以往任何时候都更容易。在本教程中,我将分享我所学到的知识以及如何开始加速您的代码。

本教程将涵盖:
- GPU 是什么?它与 CPU 有何不同?
- CUDA 开发模型概述
- Numba: Python 的高性能编译器
- 用 Python 编写您的第一个 GPU 代码
- 内存管理
- 使用 pyNVML 了解 GPU 的工作状态(内存使用、利用率等)
- RAPIDS: 一套 GPU 加速的数据科学库
- 在 GPU 上使用 NumPy 风格的数组
- 在 GPU 上使用 Pandas 风格的数据框
- 在 GPU 上执行类似 scikit-learn 的机器学习

学员需要具备 Python 和编程概念的基本知识,但不需要 GPU 经验。学员的主要收获将是认识到,要让代码在 GPU 上运行,他们不需要做太多不同的事情。

## 运行教程

本教程已更新为可在 [Google Colab](https://colab.google/) 上运行(截至2023年12月),这使得任何拥有 Google 账户的人都可以获得一个带 GPU 的交互式 Python 环境。

要运行每个笔记本,您需要点击下表中的链接在 Colab 中打开它,然后设置运行时包含 GPU。**您需要为每个笔记本都这样做。**

具体步骤:
- 点击右上角"Connect"旁边的箭头
- 选择"Change runtime type" 
- 选择 GPU(免费版中提供的 T4 对本教程来说已经足够)
- 点击保存

![](images/colab-runtime-type.png)

![](images/colab-t4.png)

## 笔记本目录

| 笔记本      | 链接 |
| ----------- | ----------- |
| 0.0 欢迎 | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/0.0_Welcome_cn.ipynb)|
| 1.0 CPU GPU 比较 | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/1.0_CPU_GPU_Comparison_cn.ipynb)|
| 2.0 Numba | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/2.0_Numba_cn.ipynb)|
| 2.1 Numba 实验 | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/2.1_Numba_lab_cn.ipynb)|
| 2.2 Numba 实验(解答) | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/2.2_Numba_lab_solution_cn.ipynb)|
| 3.0 Numba 高斯模糊 | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/3.0_Numba_gauss_cn.ipynb)|
| 3.1 Numba 实验 2 | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/3.1_Numba_lab_2_cn.ipynb)|
| 3.2 Numba 实验 2(解答) | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/3.2_Numba_lab_2_solution_cn.ipynb)|
| 4.0 pyNVML | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/4.0_pyNVML_cn.ipynb)|
| 4.1 CUDA 数组接口 | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/4.1_CUDA_Array_Interface_cn.ipynb)|
| 5.0 Cupy | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/5.0_Cupy_cn.ipynb)|
| 5.1 Cupy 实验 | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/5.1_Cupy_Lab_cn.ipynb)|
| 5.2 Cupy 实验(解答) | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/5.2_Cupy_Lab_solution_cn.ipynb)|
| 6.0 cuDF | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/6.0_cuDF_cn.ipynb)|
| 7.0 cuML | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/7.0_cuML_cn.ipynb)|
| 8.0 使用 Dask 进行多 GPU 计算 | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kevinz/accelerated-computing-hub/blob/main/gpu-python-tutorial/8.0_Multi-GPU_with_Dask_cn.ipynb)|
