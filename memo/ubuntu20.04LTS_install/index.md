<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML'></script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({ tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]} });
</script>

# 分割配置

1. EFI
   - 512 MB
   - 不確定要不要

1. Swap Area
   - 1 ~ 2 倍記憶體大小
   - 如果記憶體本來就夠大且不用休眠功能可以不用設定

1. / (root)
   - 剩下的空間
   - 偷懶的設定，系統壞掉就要全部重裝

# 安裝軟體
## 指令安裝
        
        # 安裝常用軟體 #
        sudo apt-get update
        sudo apt install ibus-chewing # 新酷音
        sudo apt-get install vim # vim
        sudo apt-get install vlc # VLC media player
        sudo apt install libreoffice # LibreOffice
        sudo apt install grub-customizer # Grub Customizer
        sudo apt install git # Git
        sudo apt install python3-pip # python pip
        sudo apt-get install python3-venv # python venv
        sudo apt-get install ntpdate # auto sync time
        sudo ntpdate time.windows.com
        sudo hwclock --localtime --systohc
        sudo apt-get install filezilla # Filezilla
        sudo apt-get install -y openssh-server # As ssh server
        sudo service ssh status # check ssh server state
        sudo systemctl stop cups-browsed # 關閉自動搜尋網路印表機
        sudo systemctl disable cups-browsed

        # 用內建的Software & Updates安裝GPU Driver #
        # NVIDIA driver metapackage from nvidia-driver-460

        # 安裝 cuda 11.2 + cudnn #
        wget https://developer.download.nvidia.com/compute/cuda/11.2.0/local_installers/cuda_11.2.0_460.27.04_linux.run
        sudo sh cuda_11.2.0_460.27.04_linux.run
        # 只安裝cuda其他全部不安裝

        sudo nano ~/.bashrc
        # 最後面增加下面3行
        export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64
        export CUDA_HOME=/usr/local/cuda
        export PATH=$PATH:/usr/local/cuda/bin
        
        # 從官網下載cudnn 8.1.1 for cuda 11.2
        tar -zvxf cudnn-11.2-linux-x64-v8.1.1.33.tgz
        sudo cp cuda/include/*.h /usr/local/cuda/include/
        sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64/
        sudo chmod a+r /usr/local/cuda/include/cudnn.h
        source ~/.bashrc
        
        # 安裝docker #
        sudo apt-get autoremove -y --purge docker-engine
        sudo apt-get autoremove -y --purge docker
        sudo apt-get autoremove -y --purge docker.io
        sudo apt-get autoremove -y --purge docker.ce
        sudo apt install docker.io
        sudo systemctl start docker
        sudo systemctl enable docker

        # 安裝 NVIDIA Docker support #
        distribution=$(. /etc/os-release;echo $ID$VERSION_ID) && curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - && curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
        sudo apt-get update
        sudo apt-get install -y nvidia-docker2
        sudo systemctl restart docker
        docker run --rm --gpus all nvidia/cuda:11.0-base nvidia-smi

## 透過buntu software 安裝

- skype

## 自行下載deb後透過 dpkg 安裝

- chrome
- vscode

## Others
- tensorflow 2.6.0
- PyTorch 1.8.2(LTS) [with cuda 11.1 ver]

## 參考資料

- [NVIDIA Docker support](https://github.com/NVIDIA/nvidia-docker)