# Reconnaissance

## Active reconnaissance
Quá trình tìm kiếm thông tin về mục tiêu thông qua các phương tiện tấn công đang hoạt động, tác động trực tiếp đến mục tiêu.
### Ưu điểm
- Cho phép thu thập được các thông tin sâu hơn về hệ thống mục tiêu như các dịch vụ đang chạy, phiên bản phần mềm, cấu trúc mạng nội bộ, v.v.
- Xác định trực tiếp các lỗ hổng và mặt yếu để lên kế hoạch tấn công, thay vì chỉ dựa vào thông tin sẵn có.
- Các kỹ thuật như quét cổng, dò tìm lỗ hổng hay thử nghiệm xâm nhập sẽ cho kết quả chính xác, đáng tin cậy hơn.
## Nhược điểm
- Dễ bị phát hiện bởi các hệ thống giám sát an ninh, tường lửa, IDS/IPS do tạo ra các tương tác bất thường với hệ thống mục tiêu.
- Nếu thực hiện không khéo léo có thể vô tình gây sự cố, làm hỏng hệ thống của mục tiêu.
- Đòi hỏi năng lực kỹ thuật cao hơn, mất nhiều thời gian hơn để thực hiện so với trinh sát thụ động.

## Passive recoonaissance
Quá trình tìm kiếm thông tin thụ động về một mục tiêu thông qua các phương tiện tấn công thụ động, thông qua các website công khai, mạng xã hội, tài liệu,... Phương pháp này không tác động trực tiếp lên mục tiêu do đó không gây ảnh hưởng đến mục tiêu.
### Ưu điểm
- Có thể thu thập một lượng lớn thông tin từ nhiều nguồn công khai như WHOIS, DNS, mạng xã hội, các bộ thông tin rò rỉ,v.v.
- Giúp xác định các tài sản số, thông tin nhạy cảm bị lộ, các lỗ hổng bảo mật đã biết trước khi bắt đầu tấn công chủ động.
- Ít rủi ro bị phát hiện.
### Nhược điểm 
- Phụ thuộc vào lượng thông tin sẵn có và chất lượng của dữ liệu công khai. Không phải lúc nào cũng tìm được đầy đủ thông tin cần thiết.
- Một số thông tin nhạy cảm chỉ có thể thu thập được bằng các phương pháp xâm nhập chủ động như quét cổng, khai thác lỗ hổng.
- Đôi khi thông tin thu thập được có thể lỗi thời, không chính xác do chủ thể thay đổi cấu hình, chính sách bảo mật.

## Recon dựa trên phạm vi
### Lợi ích
- Tiết kiệm rất nhiều thời gian.
- Bạn biết chính xác những gì cần tìm.
- Bạn có thể dễ dàng tự động hóa quy trình điều chỉnh của mình.
- Ít cơ hội gửi các vấn đề ngoài phạm vi hơn.
- Cũng giống như các phương pháp bảo mật khác, nó cho phép bạn thực hiện Recon tốt hơn.

### Phạm vi nhỏ

Mục tiêu: thường là các subdomains như mail.google.com,...

Recon to do: Directory Enumeration, Technology Fingerprinting, Port Scanning, Broken Link Hijacking, JS Files for Hardcoded APIs & Secrets, Parameter Discovery, Wayback History, Domain-Specific GitHub & Google Dorking, Data Breach Analysis, Misconfigured Cloud Storage.

### Phạm vi trung bình

Mục tiêu: thường là các domain. ví dụ như google.com,...

Recon to do: Subdomain Enumeration, Subdomain Bruteforcing, Subdomain Takeover, Probing, Template Based Scanning, Internet Search Engine Discovery, Potential Pattern Extraction with GF, Heartbleed Scanning, General Security Misconfiguration Scanning,...


