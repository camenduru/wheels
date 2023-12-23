🐣 Please follow me for new updates https://twitter.com/camenduru <br />
🔥 Please join our discord server https://discord.gg/k5BwmmvJJU <br />
🥳 Please join my patreon community https://patreon.com/camenduru <br />

### 🧬 Code
https://github.com/NVlabs/tiny-cuda-nn  <br />
https://github.com/open-mmlab/mmcv <br />
https://github.com/facebookresearch/xformers <br />
https://github.com/facebookresearch/pytorch3d <br />
https://github.com/nerfstudio-project/nerfacc <br />
https://github.com/facebookresearch/detectron2 <br />
https://github.com/NVIDIAGameWorks/kaolin <br />
https://github.com/mit-han-lab/torchsparse <br />
https://github.com/mapillary/inplace_abn <br />
https://github.com/modelscope/modelscope <br />
https://github.com/facebookresearch/detectron2/tree/main/projects/DensePose <br />
https://github.com/NVlabs/nvdiffrast <br />
https://github.com/haotian-liu/LLaVA <br />
https://github.com/chengzeyi/stable-fast <br />
https://github.com/open-mmlab/mmhuman3d <br />

### 🦒 Colab T4

![Screenshot 2023-12-18 17gfd0946](https://github.com/camenduru/wheels/assets/54370274/4c35a534-6269-4d86-89b3-af8cb770bc75)

### mmcv_full-1.7.1-cp310-cp310-linux_x86_64.whl
`-std=c++14` to `-std=c++17`
```py
%cd /content
!git clone -b v1.7.1 https://github.com/open-mmlab/mmcv
%cd /content/mmcv
!MMCV_WITH_OPS=1 pip wheel -v .
```

### tinycudann-1.7-cp310-cp310-linux_x86_64.whl
```py
!pip wheel -v git+https://github.com/NVlabs/tiny-cuda-nn/#subdirectory=bindings/torch
```

### nerfacc-0.5.3-cp310-cp310-linux_x86_64.whl
```py
!pip wheel -v git+https://github.com/nerfstudio-project/nerfacc@v0.5.3
```

### detectron2-0.6-cp310-cp310-linux_x86_64.whl
```py
!pip wheel -v git+https://github.com/facebookresearch/detectron2
```

### pytorch3d-0.7.5-cp310-cp310-linux_x86_64.whl
```py
!pip wheel -v git+https://github.com/facebookresearch/pytorch3d
```

### kaolin-0.15.0a0-cp310-cp310-linux_x86_64.whl
```py
%cd /content
!git clone --recursive https://github.com/NVIDIAGameWorks/kaolin
%cd /content/kaolin
!pip wheel -v .
```

### inplace_abn-1.1.0-cp310-cp310-linux_x86_64.whl
```py
!pip wheel -v inplace-abn
```

### torchsparse-2.0.0b0-cp310-cp310-linux_x86_64.whl

```py
!apt install libsparsehash-dev
%cd /content
!git clone -b v2.0.0 --recursive https://github.com/mit-han-lab/torchsparse
%cd /content/torchsparse
!pip wheel -v .
```

### modelscope-1.10.0-py3-none-any.whl

```py
%cd /content
!git clone -b v1.10.0 --recursive https://github.com/modelscope/modelscope
%cd /content/modelscope
!pip install -q addict yapf simplejson
!pip wheel -v .
```

### detectron2_densepose-0.6-py3-none-any.whl
```py
!pip wheel -v git+https://github.com/facebookresearch/detectron2@main#subdirectory=projects/DensePose
```

### nvdiffrast-0.3.1-py3-none-any.whl
```py
%cd /content
!git clone -b v0.3.1 --recursive https://github.com/NVlabs/nvdiffrast
%cd /content/nvdiffrast
!pip wheel -v .
```

### llava-ShareGPT4V-1.1.3-py3-none-any.whl
```py
%cd /content
!git clone -b v1.1.3 --recursive https://github.com/haotian-liu/LLaVA
%cd /content/LLaVA
#delete torch==2.0.1, torchvision==0.15.2 in pyproject.toml
!pip wheel -v .
```

### https://github.com/CMU-Perceptual-Computing-Lab/openpose
```py
%cd /content
!git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose
%cd /content/openpose
!git submodule update --init --recursive --remote
!apt install -qq libprotobuf-dev protobuf-compiler libgoogle-glog-dev
!mkdir /content/openpose/build
%cd /content/openpose/build
!cmake ..
!cmake ..
!make -j`nproc`
!wget https://huggingface.co/camenduru/openpose/resolve/main/models/pose/body_25/pose_iter_584000.caffemodel -O /content/openpose/models/pose/body_25/pose_iter_584000.caffemodel
!wget https://huggingface.co/camenduru/openpose/resolve/main/models/pose/coco/pose_iter_440000.caffemodel -O /content/openpose/models/pose/coco/pose_iter_440000.caffemodel
!wget https://huggingface.co/camenduru/openpose/resolve/main/models/pose/mpi/pose_iter_160000.caffemodel -O /content/openpose/models/pose/mpi/pose_iter_160000.caffemodel
!wget https://huggingface.co/camenduru/openpose/resolve/main/models/face/pose_iter_116000.caffemodel -O /content/openpose/models/face/pose_iter_116000.caffemodel
!wget https://huggingface.co/camenduru/openpose/resolve/main/models/hand/pose_iter_102000.caffemodel -O /content/openpose/models/hand/pose_iter_102000.caffemodel
!/content/openpose/build/examples/openpose/openpose.bin --image_dir /content/images --write_json /content/images --display 0 --render_pose 0
```
