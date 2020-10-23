# CVPR2020 Pose-guided Visible Part Matching for Occluded Person ReID
This is the pytorch implementation `on windows` of the CVPR2020 paper *"Pose-guided Visible Part Matching for Occluded Person ReID"*

# Contact
Email: nickhuang1996@126.com

## Modification
1. I fixed the way to load the model weights, or you will have severe errors when model weights are loaded:  
```UnicodeDecodeError: 'utf-8' codec can't decode byte 0xbc in position 0: invalid start byte```
2. I fixed the [rank_cy.pyx](torchreid/metrics/rank_cylib/rank_cy.pyx) and compiled successfully, so you just make this repository and test models.
3. I fixed the [setup.py](setup.py) so you can use cython to compile:  
`with open('README.md', encoding='latin1') as f:`

## Supplementary Specification
### Compile
- You need to download `Visual Studio 2017` or `Visual Studio 2019` to compile this repository.
- Run `python set.up develop`. If you compile successfully, the cmd is:
```
D:\project\Pycharm\PVPM-master>python setup.py develop
D:\project\Pycharm\PVPM-master\torchreid\metrics\rank.py:17: UserWarning: Cython evaluation (very fast so highly recommended) is unavailable, now use python evaluation.
  'Cython evaluation (very fast so highly recommended) is '
Compiling torchreid/metrics/rank_cylib/rank_cy.pyx because it changed.
[1/1] Cythonizing torchreid/metrics/rank_cylib/rank_cy.pyx
D:\software\Anaconda3\lib\site-packages\Cython\Compiler\Main.py:367: FutureWarning: Cython directive 'language_level' not set, using 2 for now (Py2). This will change in a later release! File: D:\project\Pycharm\PVPM-master\torchreid\metrics\rank_cylib\rank_cy.pyx
  tree = Parsing.p_module(s, pxd, full_module_name)
running develop
running egg_info
creating torchreid.egg-info
writing torchreid.egg-info\PKG-INFO
writing dependency_links to torchreid.egg-info\dependency_links.txt
writing requirements to torchreid.egg-info\requires.txt
writing top-level names to torchreid.egg-info\top_level.txt
writing manifest file 'torchreid.egg-info\SOURCES.txt'
reading manifest file 'torchreid.egg-info\SOURCES.txt'
writing manifest file 'torchreid.egg-info\SOURCES.txt'
running build_ext
building 'torchreid.metrics.rank_cylib.rank_cy' extension
creating build
creating build\temp.win-amd64-3.7
creating build\temp.win-amd64-3.7\Release
creating build\temp.win-amd64-3.7\Release\torchreid
creating build\temp.win-amd64-3.7\Release\torchreid\metrics
creating build\temp.win-amd64-3.7\Release\torchreid\metrics\rank_cylib
C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\MSVC\14.27.29110\bin\HostX86\x64\cl.exe /c /nologo /Ox /W3 /GL /DNDEBUG /MT -ID:\software\Anaconda3\lib\site-packages\numpy\core\include -ID:\software\Anaconda3\include -ID:\software\Anaconda3\include "-IC:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\MSVC\14.27.29110\ATLMFC\include" "-IC:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\MSVC\14.27.29110\include" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.18362.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.18362.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.18362.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.18362.0\winrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.18362.0\cppwinrt" /Tctorchreid/metrics/rank_cylib/rank_cy.c /Fobuild\temp.win-amd64-3.7\Release\torchreid/metrics/rank_cylib/rank_cy.obj
rank_cy.c
D:\software\Anaconda3\lib\site-packages\numpy\core\include\numpy\npy_1_7_deprecated_api.h(14) : Warning Msg: Using deprecated NumPy API, disable it with #define NPY_NO_DEPRECATED_API NPY_1_7_API_VERSION
torchreid/metrics/rank_cylib/rank_cy.c(3810): warning C4244: “=”: 从“__int64”转换到“float”，可能丢失数据
torchreid/metrics/rank_cylib/rank_cy.c(4523): warning C4244: “=”: 从“double”转换到“float”，可能丢失数据
torchreid/metrics/rank_cylib/rank_cy.c(4553): warning C4244: “=”: 从“double”转换到“float”，可能丢失数据
torchreid/metrics/rank_cylib/rank_cy.c(5645): warning C4244: “=”: 从“__int64”转换到“float”，可能丢失数据
torchreid/metrics/rank_cylib/rank_cy.c(5808): warning C4244: “=”: 从“double”转换到“float”，可能丢失数据
torchreid/metrics/rank_cylib/rank_cy.c(5858): warning C4244: “=”: 从“double”转换到“float”，可能丢失数据
creating D:\project\Pycharm\PVPM-master\build\lib.win-amd64-3.7
creating D:\project\Pycharm\PVPM-master\build\lib.win-amd64-3.7\torchreid
creating D:\project\Pycharm\PVPM-master\build\lib.win-amd64-3.7\torchreid\metrics
creating D:\project\Pycharm\PVPM-master\build\lib.win-amd64-3.7\torchreid\metrics\rank_cylib
C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\MSVC\14.27.29110\bin\HostX86\x64\link.exe /nologo /INCREMENTAL:NO /LTCG /nodefaultlib:libucrt.lib ucrt.lib /DLL /MANIFEST:EMBED,ID=2 /MANIFESTUAC:NO /LIBPATH:D:\software\Anaconda3\libs /LIBPATH:D:\software\Anaconda3\PCbuild\amd64 "/LIBPATH:C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\MSVC\14.27.29110\ATLMFC\lib\x64" "/LIBPATH:C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\MSVC\14.27.29110\lib\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.18362.0\ucrt\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.18362.0\um\x64" /EXPORT:PyInit_rank_cy build\temp.win-amd64-3.7\Release\torchreid/metrics/rank_cylib/rank_cy.obj /OUT:build\lib.win-amd64-3.7\torchreid\metrics\rank_cylib\rank_cy.cp37-win_amd64.pyd /IMPLIB:build\temp.win-amd64-3.7\Release\torchreid/metrics/rank_cylib\rank_cy.cp37-win_amd64.lib
  正在创建库 build\temp.win-amd64-3.7\Release\torchreid/metrics/rank_cylib\rank_cy.cp37-win_amd64.lib 和对象 build\temp.win-amd64-3.7\Release\torchreid/metrics/rank_cylib\rank_cy.cp37-win_amd64.exp
正在生成代码
已完成代码的生成
copying build\lib.win-amd64-3.7\torchreid\metrics\rank_cylib\rank_cy.cp37-win_amd64.pyd -> torchreid\metrics\rank_cylib
Creating d:\software\anaconda3\lib\site-packages\torchreid.egg-link (link to .)
torchreid 0.8.1 is already the active version in easy-install.pth

Installed d:\project\pycharm\pvpm-master
Processing dependencies for torchreid==0.8.1
Searching for torchvision==0.4.2
Best match: torchvision 0.4.2
Adding torchvision 0.4.2 to easy-install.pth file

Using d:\software\anaconda3\lib\site-packages
Searching for torch==1.4.0
Best match: torch 1.4.0
Adding torch 1.4.0 to easy-install.pth file
Installing convert-caffe2-to-onnx-script.py script to D:\software\Anaconda3\Scripts
Installing convert-caffe2-to-onnx.exe script to D:\software\Anaconda3\Scripts
Installing convert-onnx-to-caffe2-script.py script to D:\software\Anaconda3\Scripts
Installing convert-onnx-to-caffe2.exe script to D:\software\Anaconda3\Scripts

Using d:\software\anaconda3\lib\site-packages
Searching for scipy==1.2.1
Best match: scipy 1.2.1
Adding scipy 1.2.1 to easy-install.pth file

Using d:\software\anaconda3\lib\site-packages
Searching for six==1.12.0
Best match: six 1.12.0
Adding six 1.12.0 to easy-install.pth file

Using d:\software\anaconda3\lib\site-packages
Searching for Pillow==5.4.1
Best match: Pillow 5.4.1
Adding Pillow 5.4.1 to easy-install.pth file

Using d:\software\anaconda3\lib\site-packages
Searching for h5py==2.9.0
Best match: h5py 2.9.0
Adding h5py 2.9.0 to easy-install.pth file

Using d:\software\anaconda3\lib\site-packages
Searching for Cython==0.29.6
Best match: Cython 0.29.6
Adding Cython 0.29.6 to easy-install.pth file
Installing cygdb-script.py script to D:\software\Anaconda3\Scripts
Installing cygdb.exe script to D:\software\Anaconda3\Scripts
Installing cython-script.py script to D:\software\Anaconda3\Scripts
Installing cython.exe script to D:\software\Anaconda3\Scripts
Installing cythonize-script.py script to D:\software\Anaconda3\Scripts
Installing cythonize.exe script to D:\software\Anaconda3\Scripts

Using d:\software\anaconda3\lib\site-packages
Searching for numpy==1.16.2
Best match: numpy 1.16.2
Adding numpy 1.16.2 to easy-install.pth file
Installing f2py-script.py script to D:\software\Anaconda3\Scripts
Installing f2py.exe script to D:\software\Anaconda3\Scripts

Using d:\software\anaconda3\lib\site-packages
Finished processing dependencies for torchreid==0.8.1

``` 

### Test
- Set `--workers` to 0, or `pin_memory error` will be occured.
- `-evaluate` must be here.
- `--load_weights` should be  path of download models.

Then you can `python scripts/main.py`
```
--root
PATH_TO_DATAROOT
-s
market1501
-t
market1501
--save-dir
PATH_TO_EXPERIMENT_FOLDER/market_PCB
-a
pcb_p6
--gpu-devices
0
--fixbase-epoch
0
--open-layers
classifier
fc
--new-layers
classifier
em
--transforms
random_flip
--evaluate
--start-eval
60
--load-weights
PATH_TO_EXPERIMENT_FOLDER/market_PCB/Pretrain_PCB_model.pth.tar-60
--optim
sgd
--lr
0.02
--stepsize
25
50
--staged-lr
--height
384
--width
192
--batch-size
128
--base-lr-mult
0.5
--workers
0
```

## Dependencies
-Python2.7 or Python>=3.6\
-Pytorch>=1.0\
-Numpy

## Related Project
Our code is based on [deep-person-reid](https://github.com/KaiyangZhou/deep-person-reid). We adopt [openpose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) to extract pose landmarks and part affinity fields.

## Dataset Preparation
Download the raw datasets [Occluded-REID, P-DukeMTMC-reID](https://github.com/tinajia2012/ICME2018_Occluded-Person-Reidentification_datasets), and [Partial-Reid](https://pan.baidu.com/s/1VhPUVJOLvkhgbJiUoEnJWg) (code:zdl8) which is released by [Partial Person Re-identification](https://www.cv-foundation.org/openaccess/content_iccv_2015/html/Zheng_Partial_Person_Re-Identification_ICCV_2015_paper.html). Instructions regarding how to prepare [Market1501](https://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Zheng_Scalable_Person_Re-Identification_ICCV_2015_paper.pdf) datasets can be found [here](https://kaiyangzhou.github.io/deep-person-reid/datasets.html). And then place them under the directory like:

```
PVPM_experiments/data/
├── ICME2018_Occluded-Person-Reidentification_datasets
│   ├── Occluded_Duke
│   └── Occluded_REID
├── Market-1501-v15.09.15
└── Partial-REID_Dataset
```

## Pose extraction
Install openopse as described [here](https://github.com/CMU-Perceptual-Computing-Lab/openpose).\
Change path to your own dataset root and run sh files in /scripts:
```
sh openpose_occluded_reid.sh
sh openpose_market.sh
``` 
Extracted Pose information can be found [here](https://pan.baidu.com/s/1Majze1iFo7FytREijmQO5A)(code:iwlz)

## To Train PCB baseline

``` 
python scripts/main.py --root PATH_TO_DATAROOT \
 -s market1501 -t market1501\
 --save-dir PATH_TO_EXPERIMENT_FOLDER/market_PCB\
 -a pcb_p6 --gpu-devices 0 --fixbase-epoch 0\
 --open-layers classifier fc\
 --new-layers classifier em\
 --transforms random_flip\
 --optim sgd --lr 0.02\
 --stepsize 25 50\
 --staged-lr --height 384 --width 192\
 --batch-size 32 --base-lr-mult 0.5
```
## To train PVPM
```
python scripts/main.py --load-pose --root PATH_TO_DATAROOT
 -s market1501\
 -t occlusion_reid p_duke partial_reid\
 --save-dir PATH_TO_EXPERIMENT_FOLDER/PVPM\
 -a pose_p6s --gpu-devices 0\
 --fixbase-epoch 30\
 --open-layers pose_subnet\
 --new-layers pose_subnet\
 --transforms random_flip\
 --optim sgd --lr 0.02\
 --stepsize 15 25 --staged-lr\
 --height 384 --width 128\
 --batch-size 32\
 --start-eval 20\
 --eval-freq 10\
 --load-weights PATH_TO_EXPERIMENT_FOLDER/market_PCB/model.pth.tar-60\
 --train-sampler RandomIdentitySampler\
 --reg-matching-score-epoch 0\
 --graph-matching
 --max-epoch 30
 --part-score
```
Trained PCB model and PVPM model can be found [here](https://pan.baidu.com/s/16lr8m-wv-XOXACqIthC8lw)(code:64zy)

# Citation
If you find this code useful to your research, please cite the following paper:
>@inproceedings{gao2020pose,  
  title={Pose-guided Visible Part Matching for Occluded Person ReID},  
  author={Gao, Shang and Wang, Jingya and Lu, Huchuan and Liu, Zimo},  
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},  
  pages={11744--11752},  
  year={2020}  
}





