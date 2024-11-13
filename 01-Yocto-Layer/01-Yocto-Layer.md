# YOCTO
## 01 Tạo layer đơn giản trên Yocto
### Layer 
Layer trong yocto là các lớp giúp tổ chức thành phần của hệ điều hành. Layer chứa các recipes (công thức) để build các phần mềm, thư viện hoặc kernel.

### Tạo môi trường Yocto
Tải về Yocto Project (Poky) và thiết lập môi trường:
1. Chuẩn bị hệ thống
```bash
sudo apt update
sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev zstd liblz4-tool
```

2. Tải về poky:
```bash
mkdir yocto_tutorial
cd yocto_tutorial
git clone git://git.yoctoproject.org/poky -b kirkstone
```

3. Thiết lập môi trường:
```bash
cd poky
source oe-init-build-env
``` 
### Xem và tạo layer mới:
1. Xem layers:
```bash 
bitbake-layers show-layers
```
2. Tạo một layer mới, ví dụ như meta-helloworld:
```bash
bitbake-layers create-layer ../meta-helloworld/
```
3. Thêm layer vào cấu hình build:
```bash
bitbake-layers add-layer ../meta-helloworld/
```





