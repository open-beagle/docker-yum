# Linux yum pkg

```bash
# build
sudo podman run -it --rm \
-v $PWD/:/docker-yum \
-w /docker-yum \
--privileged \
registry.cn-qingdao.aliyuncs.com/wod/centos:7.2.1511-amd64 \
bash 
./mkimage-yum.sh -y /etc/yum.conf centos7

# image
docker build \
-f .beagle/Dockerfile \
-t registry.cn-qingdao.aliyuncs.com/wod/centos:7.2-amd64 \
./ \
--load

# debug
docker run -it --rm \
-v $PWD/:$PWD/ \
-w $PWD/ \
registry.cn-qingdao.aliyuncs.com/wod/centos:7.2-amd64 \
bash
```
