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
## II. Bài tập thực hành (Bổ sung)
**Bước 1: Xây dựng image từ Dockerfile**

Trước tiên, mở terminal và điều hướng đến thư mục chứa Dockerfile của bạn. Sau đó, chạy lệnh sau để xây dựng image:

```docker docker build -t your-image-name .```

Trong đó, ```your-image-name``` là tên mà bạn muốn đặt cho image Docker của mình. Dấu chấm (.) cuối cùng trong lệnh nói cho Docker biết bạn muốn xây dựng image từ Dockerfile trong thư mục hiện tại.


**Bước 2: Chạy container từ image**

Sau khi bạn đã xây dựng image, bạn có thể chạy một container từ image đó bằng cách sử dụng lệnh docker run, ở đây mình sẽ ánh xạ cổng, cụ thể là ánh xạ cổng 8888 của máy chủ của bạn đến cổng 5901 của container, bạn có thể chạy lệnh sau:

```docker run -it -p 8888:5901 your-image-name```


**Bước 3: Khởi tạo và chạy vncserver**

Đầu tiên chúng ta phải vào container bằng lệnh:

```docker exec -u 0 -it container_id_or_name /bin/bash```

Sau khi đã vào được container, ta chạy lệnh sau để set user:

```export USER=root```

Sau đó vì phần vncserver đã được cài đặt và set password trước trong Dockerfile, nên ở đây chúng ta sẽ chỉ cần chạy VNC server bằng lệnh:

```vncserver```

Nếu xuất hiện log tương tự như sau:
```
Warning: c9c0a1d930f5:1 is taken because of /tmp/.X1-lock
Remove this file if there is no X server c9c0a1d930f5:1
```
Đơn giản sẽ chỉ cần xóa file ```.X1-lock``` bằng lệnh: ```rm /tmp/.X1-lock``` và reset lại VNC server là có thể đến bước tiếp theo.

**Bước 4: Kết nối sử dụng VNC Viewer**

Ta sẽ kết nối đến cổng ```127.0.0.1:8888``` như đã config ở các bước trước đây
![alt text](<proof.png>)
