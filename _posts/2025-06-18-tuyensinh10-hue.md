---
title: "Kết quả tuyển sinh lớp 10 Tp.Huế"
date: 2025-06-18 22:00:00 +0700
categories: [Projects, Data Collection]
tags: [python, crawl, data, tuyensinh10]
---

# Phân tích dữ liệu tuyển sinh lớp 10 ở TP Huế

## Giới thiệu
Tuyển sinh lớp 10 là một trong những kỳ thi quan trọng đối với học sinh THCS tại Việt Nam. Với mục tiêu khám phá dữ liệu tuyển sinh ở TP Huế năm 2025, bài viết này hướng dẫn cách **crawl dữ liệu từ trang tra cứu điểm**, xử lý dữ liệu và phân tích các xu hướng nổi bật: điểm chuẩn, phổ điểm, so sánh các trường...

Dành cho những bạn:
- Muốn tìm hiểu về kỹ thuật crawl dữ liệu thực tế.
- Yêu thích phân tích dữ liệu giáo dục.
- Muốn khám phá kỳ thi tuyển sinh lớp 10 ở Huế bằng góc nhìn số liệu.

## 1. Thu thập dữ liệu tuyển sinh lớp 10 ở Tp.Huế

Dữ liệu được thu thập từ trang [Tra cứu điểm tuyển sinh Tp Huế](https://117.3.133.1:8080/tracuu/index.html). Theo Báo Giáo dục và Thời đại đăng tin có hơn 12.400 thí sinh đăng ký dự thi tuyển sinh vào lớp 10. Tuy nhiên trong bài viết này chỉ thực hiện crawl được khoảng 11.000 thí sinh, số báo danh có định dạng 6 chữ số "010001",...với phương pháp khi tra cứu 3 số báo danh liên tiếp không có thông tin thí sinh thì cộng lên 100 đơn vị. Hiện tại vẫn chưa tìm ra phương pháp hiệu quả nhất, rất mong được đóng góp từ bạn đọc.

### 1.1 Yêu cầu hệ thống
- Python 3.x
- Các thư viện: `selenium`, `bs4`, `time`,...

### 1.2 Cài đặt
1. Clone repo này về máy:
   ```git clone https://github.com/BAOTIN2004/sofascore-football-crawler.git ```
2. Di chuyển đến thư mục:
    ```cd "code crawl"```
3. Chạy chương trình:
    ```python l10.py ```
4. Sau khi chạy thành công, file `.csv` chứa dữ liệu được tạo ra trong thư mục làm việc.

### 1.3 Tiền xử lý dữ liệu
Bài viết này tập trung chủ yếu vào phân tích nên quá trình [tiền xử lý dữ liệu](https://github.com/BAOTIN2004/sofascore-football-crawler/blob/main/code%20crawl/data_preprocessed_tuyensinh10.ipynb) được thực hiện chi tiết qua đường dẫn.

## 2. Phân tích dữ liệu tuyển sinh lớp 10 ở Tp.Huế





## Liên hệ
Nếu có bất kỳ câu hỏi hay đóng góp, hãy liên hệ qua email hoặc tạo issue trên GitHub.

---
## Người phát triển
**Phạm Phước Bảo Tín (tinppb)**  
📧 Email: [baotinphamphuoc@gmail.com](mailto:baotinphamphuoc@gmail.com)  
