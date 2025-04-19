---
title: "Crawl dữ liệu Sofascore bằng Python"
date: 2025-04-17 22:00:00 +0700
categories: [Projects, Data Collection]
tags: [python, crawl, sofascore, data]
---
# Sofascore Football Crawler

## Giới thiệu
**Sofascore Football Crawler** là một công cụ thu thập dữ liệu bóng đá từ trang [Sofascore](https://www.sofascore.com/). Dự án này giúp bạn lấy thông tin về cầu thủ, đội bóng, và thống kê các chỉ số của cầu thủ một cách tự động.

## Tính năng
- Lấy dữ liệu theo giải đấu (Premier League, UEFA Champions League, La Liga, Serie A,...).
- Trích xuất thông tin chi tiết cầu thủ:
  - Season
  - Team
  - Name
  - Goals
  - Successful dribbles
  - Tackles
  - Assists
  - Accurate passes %
  - Average Sofascore Rating
- Xuất dữ liệu ra file `.csv`.

## Cài đặt

### Yêu cầu hệ thống
- Python 3.x
- Các thư viện cần thiết: `selenium`, `pandas`, `beautifulsoup4`, ...

### Cách cài đặt
1. Clone repo này về máy:
   ```sh
   git clone https://github.com/BAOTIN2004/sofascore-football-crawler.git
2. Di chuyển đến thư mục:
    ```shsh
   cd "code crawl sofascore"
3. Chạy chương trình:
    ```sh 
    python EPL_sofa_crawl.py
## Đóng góp
Nếu bạn muốn đóng góp cho dự án:
1. Fork repo này.
2. Tạo branch mới:
    ```sh
    git checkout -b branch-moi
3. Commit thay đổi:
    ```sh
    git commit -m "Mô tả thay đổi"
4. Push lên Github:
    ```sh
    git push origin branch-moi

## Liên hệ
Nếu có bất kỳ câu hỏi nào, hãy liên hệ qua emai hoặc tạo issue trên GitHub.

---
## Người phát triển
**Phạm Phước Bảo Tín (tinppb)**  
📧 Email: [baotinphamphuoc@gmail.com](mailto:baotinphamphuoc@gmail.com)  
