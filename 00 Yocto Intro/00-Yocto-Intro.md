# YOCTO
## 00 Yocto Introduction
### Yocto là gì ?
Yocto là một dự án do Linux Foundation phát triển, giúp tạo ra một nền tảng phần mềm nhúng hoàn chỉnh từ mã nguồn. Mục tiêu chính của Yocto là cung cấp các công cụ để tạo ra các hệ điều hành nhỏ gọn, hiệu quả và được tối ưu hóa cho từng thiết bị. Với Yocto, bạn có thể cấu hình chi tiết mọi thành phần trong hệ điều hành, từ kernel Linux, các thư viện cơ bản đến các ứng dụng người dùng.
### Kiến trúc và thành phần chính của Yocto.
Yocto bao gồm nhiều thành phần, nhưng những thành phần quan trọng nhất là:
    - Poky: Là nền tảng phát triển chính trong Yocto, bao gồm hệ sinh thái công cụ, cấu hình, và các lớp (layers) cơ bản.
    - Bitbake: Công cụ xây dựng chính trong Yocto, quản lý quá trình biên dịch và dựng gói phần mềm dựa trên các công thức (recipe).
    - Layers (Lớp): Yocto sử dụng cấu trúc layer để tổ chức các thành phần trong hệ thống. Các lớp này chứa các công thức (recipes) để xây dựng các thành phần cụ thể (như kernel, thư viện hay ứng dụng). Điều này giúp dễ dàng thêm, gỡ hoặc cấu hình lại các thành phần.
    - Recipes (Công Thức): Recipes trong Yocto là các tệp chứa hướng dẫn để tải về, cấu hình, biên dịch và cài đặt phần mềm. Chúng cho phép kiểm soát từng giai đoạn trong quá trình xây dựng phần mềm.
    - Toolchain: Yocto cung cấp bộ công cụ cross-compile để biên dịch mã nguồn cho các kiến trúc phần cứng khác nhau (ARM, x86,...).

