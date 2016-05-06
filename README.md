# Dữ liệu minh họa ứng dụng sulieu-web

Dữ liệu dùng để chạy ứng dụng sulieu-web. Dữ liệu bao gồm 2 loại:

* Các tệp hình ảnh.
* Dữ liệu xuất (dump) từ CSDL MongoDB.

Khi clone mã nguồn sulieu-web, tất cả dữ liệu này đồng thời được tải luôn về thư mục
`./data` của sulieu-web. Đối với các tệp hình ảnh, chúng ta không cần phải làm gì cả.
Đối với dữ liệu xuất từ MongoDB, chúng ta thực hiện `restore` trở lại theo các bước sau:

Mở cửa sổ dòng lệnh (Terminal), chuyển vào làm việc trong thư mục `./data/mongodata`.

Chạy các lệnh `mongorestore` để khôi phục dữ liệu vào mongodb:

```bash
mongorestore -d suviet-timeline ./suviet-timeline
mongorestore -d suviet-skywall  ./suviet-skywall
```

Sau khi thực hiện xong, kiểm tra lại bằng cách dùng `mongo` để truy vấn dữ liệu:

```
$ mongo
> use suviet-timeline
> db.figure.find()
```

Nếu hiển thị danh sách các danh nhân lịch sử, có thể xem quá trình import thành công.
