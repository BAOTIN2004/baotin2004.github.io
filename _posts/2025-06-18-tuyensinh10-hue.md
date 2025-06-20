---
title: "Kết quả tuyển sinh lớp 10 Tp.Huế"
date: 2025-06-18 22:00:00 +0700
categories: [Projects, Data Collection]
tags: [python, crawl, data, tuyensinh10]
---

# Thu thập và Phân tích dữ liệu tuyển sinh lớp 10 ở TP Huế

## Giới thiệu
Bên cạnh kỳ thi trung học phổ thông quốc gia thì kỳ thi tuyển sinh lớp 10 cũng là một trong những kỳ thi quan trọng đối với học sinh tại Việt Nam. Với mục tiêu khám phá dữ liệu tuyển sinh ở Tp Huế năm 2025, bài viết này hướng dẫn cách **crawl dữ liệu từ trang tra cứu điểm**, đồng thời bài viết này sẽ giúp bạn có cái nhìn rõ hơn các xu hướng như:
- Trường nào có số lượng học sinh đặt nguyện vọng 1 nhiều nhất ?
- Môn có phổ điểm cao nhất/thấp nhất ?
- Giới tính "Nam" liệu có học giỏi hơn giới tính "Nữ" trong giai đoạn THCS ?
- Có sự phân hóa rõ rệt về chất lượng học sinh giữa các vùng quận/huyện/thị xã hay không ?,...


Bài viết này phù hợp cho những bạn đọc:
- Muốn tìm hiểu về kỹ thuật crawl dữ liệu thực tế.
- Yêu thích phân tích dữ liệu giáo dục.
- Muốn khám phá kỳ thi tuyển sinh lớp 10 ở Huế bằng góc nhìn số liệu.

## 1. Thu thập dữ liệu tuyển sinh lớp 10 ở Tp.Huế

Dữ liệu được thu thập từ trang tra cứu điểm tuyển sinh Tp Huế: `http://117.3.133.1:8080/tracuu/index.html`. Theo Báo Giáo dục và Thời đại đăng tin có hơn 12.400 thí sinh đăng ký dự thi tuyển sinh vào lớp 10 tại địa bàn thành phố. Tuy nhiên trong bài viết này chỉ thực hiện crawl được kết quả khoảng 11.000 thí sinh, số báo danh có định dạng 6 chữ số "010001",...với phương pháp khi tra cứu 3 số báo danh liên tiếp không có thông tin thí sinh thì cộng lên 100 đơn vị. Hiện tại vẫn chưa tìm ra phương pháp hiệu quả nhất, rất mong được đóng góp từ bạn đọc.

Giới thiệu dữ liệu:
- SBD: Số báo danh, mỗi thí sinh có duy nhất một số báo danh.
- Họ và Tên: Tên đầy đủ của thí sinh.
- Giới tính: Nam hoặc Nữ.
- Ngày sinh: Ngày tháng năm sinh của thí sinh.
- Trường TH/THCS: Trường THCS nơi thí sinh học lớp 9.
- Quận/Huyện/Thị xã: Khu vực của trường THCS hoặc nơi thí sinh cư trú.
- Nguyện vọng 1, 2, 3: Các trường THPT thí sinh đăng ký theo thứ tự ưu tiên.
- Điểm Toán, Ngữ văn/Tiếng Việt, Ngoại ngữ: Điểm thi của từng môn, tính theo thang điểm 10.
- Điểm THCS: Điểm xét tuyển dựa trên kết quả học tập 4 năm THCS.
- Tổng xét phổ thông/NTP: Tổng điểm xét tuyển, được tính bằng công thức: DXT = Điểm(Toán + Văn + Anh) + Điểm THCS.
- Kết quả: Trúng tuyển hoặc không trúng tuyển, kèm theo trường THPT trúng tuyển.
- Ghi chú: Thông tin bổ sung, chuyên Tin, Hóa,...

### 1.1 Yêu cầu hệ thống
- Python 3.x
- Các thư viện: `selenium`, `bs4`, `time`,...

### 1.2 Cài đặt
1. Clone repo này về máy:
   ```git clone https://github.com/BAOTIN2004/sofascore-football-crawler.git ```
2. Di chuyển đến thư mục:
    ```cd "code crawl"```
3. Chạy chương trình:
    ```python l10.ipynb ```
4. Sau khi chạy thành công, file `.csv` chứa dữ liệu được tạo ra trong thư mục làm việc.

### 1.3. Tiền xử lý dữ liệu
Bài viết này tập trung chủ yếu vào phân tích nên quá trình [tiền xử lý dữ liệu](https://github.com/BAOTIN2004/sofascore-football-crawler/blob/main/code%20crawl/data_preprocessed_tuyensinh10.ipynb) được thực hiện chi tiết qua đường dẫn.
Bộ dữ liệu ban đầu có chất lượng tương đối tốt, chỉ phát sinh một số vấn đề nhỏ trong khâu tiền xử lý như chuẩn hóa định dạng điểm, xử lý trùng lặp và chuẩn hóa văn bản. Do đó, bước tiền xử lý được thực hiện khá nhanh chóng và không yêu cầu thao tác quá phức tạp.
## 2. Phân tích dữ liệu tuyển sinh lớp 10 ở Tp.Huế

### 2.1. Khám phá tổng quan dữ liệu

Thống kê số lượng thí sinh đặt nguyện vọng 1 vào các trường (**không tính Quốc học Huế**).

| STT | Trường THPT            | NV1  | NV2 | NV3  |
| --- | ---------------------- | ---- | --- | ---- |
| 1   | THPT Hai Bà Trưng      | 1.031 | 14  | 49   |
| 2   | THPT Nguyễn Huệ        | 841  | 286 | 29   |
| 3   | THPT Cao Thắng         | 613  | 573 | 524  |
| 4   | THPT Phan Đăng Lưu     | 594  | 352 | 249  |
| 5   | THPT Gia Hội           | 580  | 611 | 534  |
| 6   | THPT An Lương Đông     | 502  | 73  | 95   |
| 7   | THPT Thừa Lưu          | 470  | 59  | 95   |
| 8   | THPT Nguyễn Chí Thanh  | 414  | 82  | 19   |
| 9   | THPT Đặng Huy Trứ      | 410  | 367 | 173  |
| 10  | THPT Phú Bài           | 403  | 272 | 68   |
| 11  | THPT Thuận An          | 400  | 557 | 253  |
| 12  | THPT Nguyễn Trường Tộ  | 379  | 832 | 158  |
| 13  | THPT Bùi Thị Xuân      | 346  | 753 | 644  |
| 14  | THPT A Lưới            | 340  | 122 | 7    |
| 15  | THPT Nguyễn Đình Chiểu | 334  | 309 | 179  |
| 16  | THPT Vinh Xuân         | 304  | 170 | 314  |
| 17  | THPT Hương Thủy        | 284  | 449 | 100  |
| 18  | THPT Hương Trà         | 254  | 320 | 85   |
| 19  | THPT Phong Điền        | 248  | 392 | 127  |
| 20  | THPT Nguyễn Sinh Cung  | 242  | 486 | 605  |
| 21  | THPT Vinh Lộc          | 229  | 68  | 58   |
| 22  | THPT Trần Văn Kỷ       | 210  | 291 | 201  |
| 23  | THPT Tam Giang         | 210  | 108 | 87   |
| 24  | THPT Nam Đông          | 185  | 62  | 110  |
| 25  | THPT Hà Trung          | 159  | 228 | 270  |
| 26  | THPT Hương Vinh        | 158  | 367 | 1065 |
| 27  | THPT Tố Hữu            | 148  | 78  | 95   |
| 28  | THPT Hoá Châu          | 143  | 290 | 91   |
| 29  | THPT Phú Lộc           | 130  | 916 | 78   |
| 30  | THPT Bình Điền         | 101  | 22  | 322  |
| 31  | THCS\&THPT Hồng Vân    | 83   | 175 | 113  |
| 32  | Không đăng ký          | 70   | 629 | 3181 |
| 33  | THPT Đặng Trần Côn     | 67   | 491 | 854  |
| 34  | THCS\&THPT Trường Sơn  | 48   | 151 | 123  |
| 35  | THPT Trần Văn Kỷ NT    | 25   | –   | –    |


Thống kê số lượng thí sinh theo địa lý.

| STT | Địa phương        | Số lượng thí sinh |
| --- | ----------------- | ----------------- |
| 1   | Quận Thuận Hóa    | 2.906             |
| 2   | Quận Phú Xuân     | 1.807             |
| 3   | Huyện Phú Lộc     | 1.513             |
| 4   | Huyện Phú Vang    | 1.115             |
| 5   | Thị xã Phong Điền | 1.027             |
| 6   | Huyện Quảng Điền  | 718               |
| 7   | Thị xã Hương Thủy | 693               |
| 8   | Thị xã Hương Trà  | 632               |
| 9   | Huyện A Lưới      | 474               |
| 10  | Ngoài tỉnh        | 69                |


### 2.2. 


## Liên hệ
Nếu có bất kỳ câu hỏi hay đóng góp, hãy liên hệ qua email hoặc tạo issue trên GitHub.

---
## Người phát triển
**Phạm Phước Bảo Tín (tinppb)**  
📧 Email: [baotinphamphuoc@gmail.com](mailto:baotinphamphuoc@gmail.com)  
