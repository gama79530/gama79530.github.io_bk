<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML'></script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({ tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]} });
</script>
# 資源
- [docker hub](https://hub.docker.com/)
- [《Docker - 從入門到實踐­》正體中文版](https://legacy.gitbook.com/book/philipzheng/docker_practice/details)

# 常用指令

- pull image

        docker pull [OPTIONS] NAME[:TAG|@DIGEST]
        docker pull registry/repository:tag
        docker pull hello-world

- 確定docker 版本

        docker -v

- List images

        docker images

- 新建container

         docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
         docker run -idt --name hello -p 5000:5000  hello-world


- 啟動container

        docker start [OPTIONS] CONTAINER [CONTAINER...]
        docker start -i hello

- attach container

        docker attach hello-world

- 條列所有container

    docker ps -a


# container參數

# 安裝

## 從Ubuntu預設Repositories安裝
    sudo apt-get update
    sudo apt-get remove docker docker-engine docker.io
    sudo apt install docker.io
    sudo systemctl start docker
    sudo systemctl enable docker

## 安裝 [NVIDIA Docker support](https://github.com/NVIDIA/nvidia-docker)
- Note that with the release of Docker 19.03, usage of nvidia-docker2 packages are deprecated since NVIDIA GPUs are now natively supported as devices in the Docker runtime.

        \# Add the package repositories
        distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
        curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
        curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
        sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
        sudo systemctl restart docker
