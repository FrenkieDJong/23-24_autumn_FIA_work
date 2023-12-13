# **23-24学年秋 图像分析基础 大作业 《基于NERF的新视角图像合成实践》** #
## **前言** ##
- 大作业参考[https://github.com/autonomousvision/graf](http://https://github.com/autonomousvision/graf "GRAF")
- 汽车数据集在上方的代码中有说明
- X光图像数据集参考[https://github.com/MeioJane/SIXray](https://github.com/MeioJane/SIXray "X光图像数据集")
## **环境配置** ##
你可以使用下方代码创建一个名为graf的anaconda环境  

    conda env create -f environment.yml  
    conda activate graf

接下来，为 nerf-pytorch 安装 torchsearchsorted。请注意，这需要 torch>=1.4.0 和 CUDA >= v10.1。您可以通过以下方式安装 torchsearchsorted  

    cd submodules/nerf_pytorch  
    pip install -r requirements.txt  
    cd torchsearchsorted  
    pip install .  
    cd ../../../  
## **训练** ##
训练GRAF模型  

    python train.py CONFIG.yaml 
其中CONFIG文件根据自己的需要选择，汽车选择`carla.yaml`,X光图像选择`xrays.yaml`  
您可以使用tensorboard在[http://localhost:6006](http://localhost:6006)上监控训练过程：
  
    cd OUTPUT_DIR  
    tensorboard --logdir ./monitoring --port 6006  
其中OUTPUT_DIR为你的输出的文件夹位置   
## **评估** ##
下方命令用于评估训练的模型  
`python eval.py CONFIG.yaml --fid_kid --rotation_elevation --shape_appearance`  
根据需要选择CONFIG文件  
## **其他信息** ##
姓名：赵苗  
最后更新时间：2023/12/13