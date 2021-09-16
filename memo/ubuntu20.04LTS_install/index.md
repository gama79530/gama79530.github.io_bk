<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML'></script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({ tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]} });
</script>

# 分割配置
種類 | 大小 | 說明
--- | --- | ---
EFI | 512 mb | 不確定要不要
swap | 1 ~ 2 倍記憶體大小 | 如果記憶體本來就夠大且不用休眠功能可以不用設定
/ | 剩下的空間 | 偷懶的設定，系統壞掉就要全部重裝

# 安裝軟體 (整理板)

        sudo apt install ibus-chewing
        sudo apt-get install vim
        sudo apt-get install vlc
        sudo apt install libreoffice
        sudo apt install grub-customizer
        sudo apt install git
        sudo apt install python3-pip
        sudo apt-get install python3-venv
        sudo apt-get install ntpdate
        sudo apt-get install filezilla

        sudo ntpdate time.windows.com
        sudo hwclock --localtime --systohc
        

        
        sudo apt-get autoremove -y --purge docker-engine
        sudo apt-get autoremove -y --purge docker
        sudo apt-get autoremove -y --purge docker.io
        sudo apt-get autoremove -y --purge docker.ce
        sudo apt install docker.io
        sudo systemctl start docker
        sudo systemctl enable docker


# 安裝軟體

- 新酷音

        sudo apt install ibus-chewing  
        # 裝完後必須重新登入

- vim

        sudo apt-get install vim

- VLC media player

        sudo apt-get install vlc
        # 或者可用ubuntu software安裝

- LibreOffice

        sudo apt install libreoffice
        # 或者可用ubuntu software安裝

- Grub Customizer

        sudo apt install grub-customizer

- git

        sudo apt install git

- python 相關

        sudo apt install python3-pip
        sudo apt-get install python3-venv

- ntpdate 自動網路校時

        sudo apt-get install ntpdate
        sudo ntpdate time.windows.com
        sudo hwclock --localtime --systohc

- filezilla

        sudo apt-get install filezilla

- cuda 11.2 + cudnn 

        # 先安裝GPU Driver

        wget https://developer.download.nvidia.com/compute/cuda/11.2.0/local_installers/cuda_11.2.0_460.27.04_linux.run
        sudo sh cuda_11.2.0_460.27.04_linux.run
        # 只安裝cuda其他全部不安裝
        sudo nano ~/.bashrc
        # 最後面增加下面幾段
        export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64
        export CUDA_HOME=/usr/local/cuda
        export PATH=$PATH:/usr/local/cuda/bin

        # 下載cudnn 8.1.1 for cuda 11.2
        tar -zvxf cudnn-11.2-linux-x64-v8.1.1.33.tgz

        sudo cp cuda/include/*.h /usr/local/cuda/include/
        sudo cp cuda/lib64/libcudnn* /usr/lib/cuda/lib64/
        sudo chmod a+r /usr/local/cuda/include/cudnn.h

- docker (先移除在安裝)

        sudo apt-get autoremove -y --purge docker-engine
        sudo apt-get autoremove -y --purge docker
        sudo apt-get autoremove -y --purge docker.io
        sudo apt-get autoremove -y --purge docker.ce
        sudo apt install docker.io
        sudo systemctl start docker
        sudo systemctl enable docker
        sudo gpasswd -a $USER docker

- [NVIDIA Docker support](https://github.com/NVIDIA/nvidia-docker)

        distribution=$(. /etc/os-release;echo $ID$VERSION_ID) && curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - && curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
        sudo apt-get update
        sudo apt-get install -y nvidia-docker2
        sudo systemctl restart docker
        docker run --rm --gpus all nvidia/cuda:11.0-base nvidia-smi