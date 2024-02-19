# KTPM_01
Bài tập môn KTPM tuần 1

**Nguyễn Việt Hoàng - 21020323**
## I. Trả lời câu hỏi lý thuyết
### 1. Docker là gì ?
Docker là một công cụ được dùng để gói các tài nguyên, chương trình, hệ điều hành... của một môi trường chạy ứng dụng và từ đó có thể triển khai chạy chương trình ở bất kỳ một máy, một môi trường nào khác một cách nhanh chóng, thuận tiện cho công việc phát triển phần mềm. Nó lấy tài nguyên cho môi trường ảo từ máy chủ (CPU, RAM, bộ nhớ...). Môi trường đó được gọi là `container` chứ không phải là máy ảo (Virtual Machine).
### 2. Docker - compose là gì ?
Docker - compose được cung cấp bởi Docker nhằm giúp người dùng tạo và sử dụng các ứng dụng đa môi trường trong Docker, quản lý việc chuyển `image` thành `container`, có thể quản lý `volume`, biến môi trường, kết nối giữa các `container`
### 3. So sánh các hệ điều hành
- Unix là một hệ điều hành được phát triển từ những năm 1970, là nền tảng cho nhiều hệ điều hành khác sau này, mã nguồn đóng
- Unix-like hay *unix là thuật ngữ tổng quát chỉ các hệ điều hành có nguồn gốc hay dựa trên Unix, bao gồm cả BSD, macOS, Linux... Đặc điểm chung của chúng có thể là hệ thống file hướng cây, các công cụ dòng lệnh, hỗ trợ đa người dùng và đa tác vụ.
- BSD là một phiên bản của Unix (Unix - like), mã nguồn đóng
- Linux là một kernel lấy cảm hứng từ Unix, tạo ra bởi Linus Torvalds. Nó kết hợp với GNU tạo thành GNU/Linux là một hệ điều hành hoàn chỉnh, mã nguồn mở.
- macOS là hệ điều hành của Apple cho máy tính Mac. macOS được xây dựng trên một nền tảng dựa trên BSD. Vì vậy, macOS là *unix. Nó cung cấp một giao diện người dùng đồ họa mạnh mẽ, với nhiều tính năng cao cấp như Time Machine (sao lưu tự động), Spotlight (tìm kiếm nhanh), và Mission Control (quản lý cửa sổ).
### 4. So sánh Alpine với Ubuntu
- Kích thước : Alpine nhỏ gọn (tầm 5 MB), Ubuntu dùng `glibc` và nhiều package khác nên nặng hơn nhiều
- Packet manager : Alpine dùng `apk`, Ubuntu dùng `apt`.
- Sử dùng: Alpine tập trung vào tính bảo mật, phù hợp với các hệ thống nhỏ, hệ thống nhúng. Linux nặng hơn, phức tạp hơn, phù hợp với nhiều mục đích sử dụng, có cộng đồng lớn hơn.
### 5. VNC
- VNC (Virtual Network Computing) là một hệ thống giúp điều khiển thiết bị công nghệ từ xa dựa trên kết nối mạng. Có thể truy cập máy tính từ xa, chia sẻ màn hình, điều khiển chuột, bàn phím.
- VNC hoạt động trên một mô hình server / client. VNC Server được cài đặt trên máy tính cần điều khiển và máy tính cần sử dụng để điều khiển
- Về mặt công nghệ phía dưới, nó khác với TeamViewer
## II. Bài tập thực hành
