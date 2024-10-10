## Directory Enumeration
- Liệt kê các thư mục.
- Công cụ: dirsearch, fuff.
- Nên sử dụng wordlist dành riêng cho framework để có nhiều kết quả hơn.

## Technology Fingerprinting
- Kiểm tra các dịch vụ đang chạy trên ứng dụng. Thông thường, các máy chủ, thư viện và thành phần của bên thứ ba được sử dụng có thể đã lỗi thời và dễ gặp phải các sự cố bảo mật đã biết. 
- Công cụ: Wappalyzer Plugin, whatweb.

## Port Scanning
- Có thể thấy một số cổng đang chạy một số dịch vụ có thể đang sử dụng thông tin xác thực mặc định, bị định cấu hình sai hoặc dễ bị tấn công.
- Công cụ: nmap.

## Broken Link Hijacking
- Nếu ứng dụng có một số hồ sơ truyền thông xã hội, trang web được liên kết của bên thứ ba hoặc tham chiếu đến bất kỳ miền đã hết hạn nào – hãy thử thực hiện tiếp quản.
- Công cụ: Broken Link Hijacking Burp Plugin.
  
## JS Files for Hardcoded APIs & Secrets
- Các tệp JavaScript thường chứa thông tin thú vị. Đi sâu vào từng tệp JavaScript, bạn có thể nhận được nhiều thông tin hữu ích từ API được mã hóa cứng, bí mật (chẳng hạn như thông tin xác thực AWS), thông tin về nhóm S3, tên miền phụ khác, thông tin PII, endpoint, tham số thú vị, logic để vượt qua một số hạn chế nhất định như đối với XSS và Open Redirection, bạn có thể làm được rất nhiều thứ.
- Công cụ: SecretFinder, JFScan, LinkFinder, DetectDynamicJS(Burp Plugin), Retire.js (Burp Plugin/Browser Extension/Standalone), JS Link Finder (Burp Plugin).

## Parameter Discovery
- Khám phá các tham số có thể không hiển thị trực tiếp thông qua điều hướng ứng dụng nhưng vẫn được xử lý ở phía máy chủ. Các tham số này thường dễ bị tấn công như SSRF, Open Redirection, XSS, SQLi, IDOR, v.v.
- Công cụ: Arjun, ParamSpider, Param Miner.

## Wayback History
- Có thể tìm thấy các URL có thể không còn khả dụng thông qua quy trình làm việc của ứng dụng nhưng vẫn có thể truy cập được. Đôi khi, các trang nhạy cảm được lưu vào bộ nhớ đệm tiết lộ thông tin thú vị và bạn cũng có thể lấy một loạt điểm cuối để kiểm tra nhiều lỗ hổng khác nhau.
- Công cụ: Wayback Machine, waybackurls, gau.

## Domain-Specific GitHub & Google Dorking
- Tăng bề mặt tấn công bằng cách tìm ngày càng nhiều điểm cuối, dịch vụ bị lộ, v.v. Tuy nhiên, trong trường hợp điều chỉnh phạm vi nhỏ, bạn có thể kiểm tra mã thông báo xác thực, UUID, mã định danh người dùng/tài sản, tệp sao lưu , thông tin nhạy cảm được lưu trong bộ nhớ đệm bằng cách sử dụng Google Dorks & GitHub Dorking.
- GHDB, Interesting GitHub Dorks List, GitDorker, GitRob, GitHound.

## Data Breach Analysis
- Tìm thông tin xác thực, cơ sở dữ liệu và thông tin nhạy cảm khác của nhiều tổ chức khác nhau bị rò rỉ.
- Intelx, Hacking Forums, Darknet/Darkweb Analysis.

## Misconfigured Cloud Storage
- Các tổ chức đang chuyển sang cơ sở hạ tầng đám mây và sử dụng các tùy chọn lưu trữ đám mây như Nhóm AWS S3, Nhóm GCP, v.v. để lưu trữ tài sản của họ. Tuy nhiên, do cấu hình sai đơn giản, một tổ chức có thể rò rỉ/tiết lộ một loạt thông tin cho những kẻ tấn công. Luôn luôn liệt kê các nhóm và các dịch vụ dựa trên đám mây khác và tìm kiếm cấu hình sai trong đó.
