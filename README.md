
# 🛡️ Zeek (Bro) – Intrusion Detection & Prevention System  

Đây là đồ án cuối kỳ môn **Hệ thống tìm kiếm, phát hiện và ngăn ngừa xâm nhập** tại Trường Đại học Công nghệ Thông tin – ĐHQG HCM.  
Mục tiêu của đồ án là triển khai **Zeek (trước đây là Bro)** trong vai trò một **IDS/IDPS**, thực nghiệm các kịch bản tấn công, xây dựng script phát hiện và đánh giá hiệu quả của hệ thống.  

---

## 👨‍💻 Nhóm thực hiện
- **Trương Đức Hào** – 22520407  
- **Nguyễn Khang Hưng** – 22520515  
- **Đỗ Mạnh Hùng** – 22520500  
- **Nguyễn Xuân Huy** – 22520568  

Giảng viên hướng dẫn: **ThS. Đỗ Hoàng Hiển**  

---

## ⚙️ Công nghệ và môi trường triển khai
- **Công cụ chính:** Zeek (Bro IDS)  
- **Môi trường:** Ubuntu, VMware (mô phỏng mạng doanh nghiệp nhỏ)  
- **Dịch vụ triển khai:** HTTP, DNS, FTP, SMB  
- **Cấu hình phần cứng lab:** Intel i7 (16 cores), 16GB RAM, 1TB SSD  

---

## 🔎 Các kỹ thuật phát hiện trong Zeek
- **Signature-based:** phát hiện dựa trên mẫu tấn công đã biết.  
- **Anomaly-based:** phát hiện hành vi bất thường trong lưu lượng mạng.  
- **Specification-based:** phát hiện vi phạm các quy tắc/chuẩn giao thức.  

Zeek hỗ trợ kết hợp cả 3 kỹ thuật, giúp tăng khả năng phát hiện kể cả với tấn công zero-day.  

---

## 📌 Các kịch bản tấn công & phát hiện
1. **Phát hiện chứng chỉ SSL/TLS giả mạo (MITM, phishing)**  
   → Zeek cảnh báo khi gặp chứng chỉ hết hạn, tự ký hoặc không tin cậy.  

2. **HTTP Beaconing (C2 traffic)**  
   → Phát hiện malware giao tiếp định kỳ bất thường với server điều khiển.  

3. **DNS Tunneling (Data Exfiltration)**  
   → Phân tích độ dài, tần suất, loại bản ghi DNS để phát hiện tunnel bí mật.  

4. **Phát tán malware qua file tải về**  
   → Tính toán hash (SHA-1) và so sánh với Malware Hash Registry (Team Cymru).  

5. **Đánh cắp dữ liệu qua SMB**  
   → Theo dõi truy cập file nhạy cảm (secret, password, .exe) qua SMB.  

---

## 🛡️ Tuning & Evading
- **Tuning:** giảm cảnh báo giả bằng cách điều chỉnh ngưỡng (threshold), whitelist domain/IP nội bộ, tối ưu script với `redef`.  
- **Evading:** nghiên cứu cách kẻ tấn công có thể vượt qua Zeek (jitter delay với beaconing, DoH với DNS tunneling, file obfuscation khi phát tán malware, đổi tên dữ liệu nhạy cảm trong SMB).  

---

## 📊 Kết quả đạt được
- Xây dựng thành công mô hình IDPS với Zeek.  
- Viết script tùy chỉnh phát hiện nhiều kịch bản tấn công phổ biến.  
- Đánh giá hiệu quả phát hiện, tỷ lệ false positive và khả năng ứng phó.  
- Minh chứng: Zeek có thể phát hiện tốt nhiều loại tấn công, nhưng cần kết hợp Suricata/tường lửa để ngăn chặn chủ động.  

---

## 🚀 Hướng phát triển
- Tích hợp Zeek với **SIEM/ELK Stack** để phân tích tập trung.  
- Kết hợp với **Suricata** để tạo hệ thống IDPS chủ động.  
- Ứng dụng **AI/ML** để cải thiện phát hiện anomaly-based.  
- Triển khai Zeek trong môi trường **Cloud & Container**.  

---

## 📚 Tài liệu tham khảo
- [Zeek Documentation](https://docs.zeek.org/)  
- [Zeek GitHub](https://github.com/zeek/zeek)  
- [Abuse.ch Malware Bazaar](https://bazaar.abuse.ch/)  
- Hold My Beer Security – Detecting SSH Brute Forcing with Zeek  

---

✍️ **Nhóm Zeek – UIT**
