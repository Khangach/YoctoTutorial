# YOCTO
## 02 Thêm chương trình "Hello World" và Build trên Yocto cho Rasbperry pi 4
### Thêm recipe cho chương trình Hello World 
1. Tạo thư mục cho recipe:
```bash 
mkdir -p ../meta-helloworld/recipes-example/helloworld
```
2. Tạo 1 file (helloworld_0.1.bb) trong thư mục helloworld:
```bash
nano ../meta-helloworld/recipes-example/helloworld/helloworld_0.1.bb
```

3. Nội dung của file helloworld_0.1.bb:
```bash
SUMMARY = "Hello World Program"
LICENSE = "MIT"
LIC_FILES_CHKSUM = "file://${COREBASE}/meta/COPYING.MIT;md5=3da9cfbcb788c80a0384361b4de20420"

SRC_URI = "file://helloworld.c"

S = "${WORKDIR}/build"

do_compile(){
	${CC} ${CFLAGS} ${LDFLAGS} ${WORKDIR}/helloworld.c -o ${S}/helloworld
}

do_install(){
	install -d ${D}${bindir}
	install -m 0755 ${S}/helloworld ${D}${bindir}/
}
```
Trong đó:
* SUMMARY: Mô tả ngắn gọn về công thức (Recipe).
* LICENSE: Loại giấy phép mà chúng ta sẽ sử dụng, ví dụ: MIT, GPL, BSD, v.v.
* LIC_FILES_CHKSUM: Vị trí của file giấy phép và giá trị checksum md5 của nó. Tính checksum bằng công cụ md5sum.
* SRC_URI: Các tệp nguồn.
* do_compile: Phần này thực hiện biên dịch.
* do_install: Phần này cho công thức biết nơi đặt tệp nhị phân vào ảnh cuối cùng.

4. Tạo mã nguồn cho chương trình "Hello World"(helloworld.c):
```bash
nano ../meta-helloworld/recipes-example/helloworld/helloworld.c
```
Thêm nội dung:
```bash
#include <stdio.h>
int main() {
    printf("Hello, Yocto World!\n");
    return 0;
}
```
### Cấu hình cho Raspberry pi 4
1. Thêm layer meta-raspberrypi vào cấu hình build
- Tải layer
```bash
git clone git://git.yoctoproject.org/meta-raspberrypi -b dunfell
```
- Thêm layer vào cấu hình build
```bash
bitbake-layers add-layer ../meta-raspberrypi 
```
2. Sử dụng tên hợp lệ cho MACHINE:
- Mở file local.conf trong thư mục conf của build, tìm dòng MACHINE và sửa thành
```bash
MACHINE = "raspberrypi4"
```
### Build image và thêm Hello World vào image
1. Mở file local.conf thêm 
```bash
RM_OLD_IMAGE = "1"
INHERIT += "rm-work"
IMAGE_INSTALL:append = " python3"
IMAGE_INSTALL:append = " git"
IMAGE_INSTALL:append = " helloworld"
```
2. Tiến hành build image:
```bash
bitbake core-image-minimal
```
### Chạy trên Raspberry pi 4
1. Sau khi build xong, tìm file image trong thư mục tmp/deploy/images/raspberrypi4.
2. Ghi file image ra thẻ SD và gắn vào Raspberry Pi 4.
Sử dụng lệnh dd để ghi file image:
```bash
sudo dd if=build/tmp/deploy/images/raspberrypi4/core-image-minimal-raspberrypi4.rpi-sdimg of=/dev/sdb bs=4M status=progress
```
3. Khởi động Raspberry pi 4 và chạy chương trình "Hello World":
```bash
./helloworld
```

