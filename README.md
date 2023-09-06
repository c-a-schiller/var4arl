# Virtual Augmented Reality for Atari Reinforcement Learning
Documentation and code related to the paper "Virtual Augmented Reality for Videogame Reinforcement Learning"

# Installation instructions for RL baseline
1. Create conda environment
conda env create -n crlsam python=3.10
2. Install SAM prerequisites
conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia
3. Install SAM
pip install git+https://github.com/facebookresearch/segment-anything.git
4. Install SAM optionals
pip install opencv-python pycocotools matplotlib onnxruntime onnx
5. Install SAM checkpoints (weights for model)
Download https://dl.fbaipublicfiles.com/segment_anything/sam_vit_h_4b8939.pth
https://dl.fbaipublicfiles.com/segment_anything/sam_vit_l_0b3195.pth 
https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth 
6. Install CleanRL
git clone https://github.com/vwxyzjn/cleanrl.git && cd cleanrl
poetry install
7 Install Atari support (ALE) for CleanRL
poetry install -E atari

# Video recording notes
CleanRL requires ffmpeg with libx264 support; unfortunately SAM prerequisites install an ffmpeg version without libx264 support. This additional ffmpeg installation has to be rolled back with conda remove ffmpeg --force in order to revert back to the system-wide installed ffmpeg with libx264 support
