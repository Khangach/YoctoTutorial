# YOCTO
## 00 Yocto Introduction
### Yocto là gì ?
Yocto là một dự án do Linux Foundation phát triển, giúp tạo ra một nền tảng phần mềm nhúng hoàn chỉnh từ mã nguồn. Mục tiêu chính của Yocto là cung cấp các công cụ để tạo ra các hệ điều hành nhỏ gọn, hiệu quả và được tối ưu hóa cho từng thiết bị. Với Yocto, bạn có thể cấu hình chi tiết mọi thành phần trong hệ điều hành, từ kernel Linux, các thư viện cơ bản đến các ứng dụng người dùng.
### Kiến trúc và thành phần chính của Yocto.
Yocto bao gồm nhiều thành phần, nhưng những thành phần quan trọng nhất là:
    * Poky: Là nền tảng phát triển chính trong Yocto, bao gồm hệ sinh thái công cụ, cấu hình, và các lớp (layers) cơ bản.
    * Bitbake: Công cụ xây dựng chính trong Yocto, quản lý quá trình biên dịch và dựng gói phần mềm dựa trên các công thức (recipe).
    * Layers (Lớp): Yocto sử dụng cấu trúc layer để tổ chức các thành phần trong hệ thống. Các lớp này chứa các công thức (recipes) để xây dựng các thành phần cụ thể (như kernel, thư viện hay ứng dụng). Điều này giúp dễ dàng thêm, gỡ hoặc cấu hình lại các thành phần.
    * Recipes (Công Thức): Recipes trong Yocto là các tệp chứa hướng dẫn để tải về, cấu hình, biên dịch và cài đặt phần mềm. Chúng cho phép kiểm soát từng giai đoạn trong quá trình xây dựng phần mềm.
    * Toolchain: Yocto cung cấp bộ công cụ cross-compile để biên dịch mã nguồn cho các kiến trúc phần cứng khác nhau (ARM, x86,...).

### Cách hoạt động của Yocto 
Yocto hoạt động theo quy trình gồm các bước như sau: 
    * Cấu hình Build Environment: Bạn tạo một môi trường build với các biến cấu hình cụ thể, xác định loại thiết bị và kiến trúc của nó
    * Chọn và điều chỉnh Layers: Xác định các lớp (layers) cần thiết cho dự án của bạn, như lớp chứa kernel, thư viện cơ bản, hoặc các công cụ quản lý mạng.
    * Viết Recipes: Bạn có thể tạo hoặc tùy chỉnh các recipe để cài đặt phần mềm. Recipes sẽ tải mã nguồn, biên dịch và đóng gói chúng.
    * Sử dụng Bitbake: Bạn chạy Bitbake để bắt đầu quá trình biên dịch và dựng hệ thống. Nó sẽ sử dụng các thông tin từ các lớp và recipes để xây dựng hình ảnh cuối cùng.
    * Kết quả đầu ra: Hệ điều hành Linux được tùy chỉnh sẽ được tạo ra và có thể cài đặt trên thiết bị của bạn.

### Ưu điểm của Yocto
    * Tùy biến cao: Kiểm soát chi tiết từng thành phần trong hệ điều hành, phù hợp với các thiết bị nhúng.
    * Tối ưu tài nguyên: Có thể loại bỏ các thành phần không cần thiết, giúp hệ điều hành nhẹ hơn.
    * Đa nền tảng: Hỗ trợ nhiều kiến trúc phần cứng như ARM, x86, PowerPC, MIPS.
    * Cộng đồng lớn và tài liệu phong phú: Yocto có tài liệu phong phú và cộng đồng hỗ trợ mạnh mẽ.

### Nhược điểm của Yocto
    * Phức tạp:  Đòi hỏi người dùng hiểu biết sâu về Linux và quy trình build.
    * Thời gian xây dựng lâu: Vì Yocto xây dựng hệ điều hành từ mã nguồn nên thời gian biên dịch có thể khá lâu, đặc biệt trên phần cứng yếu.
    * Đường cong học tập cao: Yêu cầu nhiều kỹ năng về phát triển nhúng, cấu hình hệ thống và xây dựng mã nguồn.


