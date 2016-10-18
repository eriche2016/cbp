# Multimodal Compact Bilinear Pooling for Torch7

***Welcome to send pull requests to resolve uncovered issues!*** 

This implements a module of Multimodal Compact Bilinear Pooling for Torch7 [cunn](https://github.com/torch/cunn).

### Dependencies
* [spectral-lib](https://github.com/eriche2016/spectral-lib) by @mbhenaff for CuFFT wrappers
###
***when install spectral-lib, you may need to run the following command to create soft symbol link to avoid error when compiling spectralnet***,
```
sudo ln -s /usr/local/cuda/lib64/libcufft.so /usr/lib/libcufft.so
```
###
### Installation
```
luarocks make rocks/cbp-scm-1.rockspec
```

### References
* [Multimodal Compact Bilinear Pooling for Visual Question Answering and Visual Grounding](https://arxiv.org/abs/1606.01847) by Fukui et al. (2016)
* [Compact Bilinear Pooling](https://arxiv.org/abs/1511.06062) by Gao et al. (2015)
* [Compact Bilinear Pooling Caffe and MatConvNet implementation](https://github.com/gy20073/compact_bilinear_pooling)

### Note
in my case, when i compile all the stuff and then load the package by followng command:
```
>> require 'cbp'
```
i run accross the following error:
```
/home/hxw/torch/install/share/lua/5.1/luarocks/loader.lua:117: error loading module 'libspectralnet' from file '/home/hxw/torch/install/lib/lua/5.
1/libspectralnet.so':
        libcufft.so.7.5: cannot open shared object file: No such file or directory
stack traceback:
```
so i change my `.bashrc` file by command below: 
```
export LD_LIBRARY_PATH=/usr/local/cuda-7.5/lib64:$LD_LIBRARY_PAT
```
and then source it:
```
source .bashrc 
```
then all the stuff is okay now. enjoy yourself by using cbp technique.
### License
BSD 3-Clause
