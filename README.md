# 🛡️ Hệ Thống Honeypot Tập Trung: T-Pot Platform, Cowrie, Dionaea & Conpot

Repository này lưu trữ tài liệu, kịch bản triển khai và báo cáo chi tiết của **Nhóm 8** về hệ thống **Honeypot**. Dự án tập trung vào việc xây dựng môi trường bẫy mã độc, giả lập các dịch vụ mạng/IoT/OT, và thu thập log tập trung nhằm phân tích hành vi tấn công mạng.

---

## 👥 Thành viên Nhóm 8
* **Lê Minh Tấn** – MSSV: 23521398[cite: 1]
* **Nguyễn Quang Thắng** – MSSV: 23521425[cite: 1]
* **Trần Viết Thắng** – MSSV: 23521433[cite: 1]

---

## 📂 Cấu trúc Đồ án & Nội dung Slide
1. **Giới thiệu về Honeypot:** Tổng quan về tầm quan trọng của honeypot như một công cụ cảnh báo sớm và phân tích hành vi kẻ tấn công[cite: 1].
2. **Kiến trúc triển khai (Deployment Architecture):**
   * **VM-A (T-Pot Server):** Trung tâm honeypot chứa các dịch vụ giả lập, ghi nhận log và hiển thị qua ELK Stack (Elasticsearch, Logstash, Kibana).
   * **VM-B (Worm Simulator):** Mô phỏng hành vi tấn công hoặc lây lan của mã độc/worm trong mạng nội bộ (Internal/Host-Only Network).
3. **Công nghệ cốt lõi (Technology Stack):**
   * **Hệ điều hành:** Ubuntu Server (T-Pot Community Edition).
   * **Honeypot Services:** Cowrie (SSH/Telnet), Dionaea (SMB/RPC/FTP), Conpot (ICS/SCADA).
   * **Log Pipeline & Dashboard:** Filebeat → Logstash → Elasticsearch → Kibana.
4. **Các kịch bản triển khai & Demo thực tế:**
   * **Kịch bản 1 (Mirai IoT Botnet với Cowrie):** Giả lập môi trường SSH/Telnet, bẫy các cuộc tấn công brute-force và ghi lại transcript, session playback.
   * **Kịch bản 2 (Malware/Ransomware với Dionaea):** Mô phỏng các dịch vụ SMB, RPC, FTP để bẫy dropper, thu thập mẫu mã độc và kiểm tra cơ chế state machine.
   * **Kịch bản 3 (ICS/SCADA với Conpot):** Giả lập thiết bị công nghiệp (PLC, RTU, Smart Meter, IEC104) nhằm phát hiện các cuộc tấn công nhắm vào hạ tầng OT.

---

## 📺 Video Demo Chi Tiết Các Thành Phần
Dưới đây là các video demo quá trình triển khai, tấn công và ghi nhận log của từng dịch vụ honeypot:

* **1. Demo Cowrie (SSH/Telnet & Mirai Botnet Simulation):** [https://youtu.be/oYQ588GB9eQ]
* **2. Demo Dionaea (SMB/RPC/FTP & Malware Capture):** [https://youtu.be/AXXmfpB4YRY]
* **3. Demo Conpot (ICS/SCADA Industrial Protocols):** [https://youtu.be/GKh7SqUPrOA]

---

## 🚀 Hướng dẫn nhanh (Quick Start)
*(Bạn có thể bổ sung các bước cài đặt hoặc câu lệnh cấu hình Docker/T-Pot tại đây nếu muốn chia sẻ mã nguồn hoặc script cấu hình cụ thể).*

```bash
# Clone repository này về máy
git clone [https://github.com/your-username/t-pot-honeypot-deployment-analysis.git](https://github.com/your-username/t-pot-honeypot-deployment-analysis.git)

# Truy cập vào thư mục dự án
cd t-pot-honeypot-deployment-analysis
