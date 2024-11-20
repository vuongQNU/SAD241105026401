# **Phân Tích Kiến Trúc, Cơ Chế, Ca Sử Dụng – Payroll System**

## **1. Phân Tích Kiến Trúc**
Hệ thống được thiết kế theo kiến trúc **3-layer**, bao gồm các lớp sau:  
- **Domain Layer**: Chứa các đối tượng mô hình nghiệp vụ.  
- **Application Layer**: Chứa logic nghiệp vụ chính của hệ thống.  
- **Infrastructure Layer**: Quản lý cơ sở dữ liệu và các kết nối hệ thống.

### **Biểu đồ Package**
![Package Diagram](https://www.planttext.com/api/plantuml/png/h9DDQiCm48NtESMGbGlf1KmfAQIBGWg1v09JUPg8wiT8uu0fELaNFLAlK3cHLDjnTZNOe9ddDq-VvP-lxwLdTDneDQjHVE2UO8EjiqfjMy-auNC6a3hpZIDFXf6bDR36bjpyB00G2hs7PrqhsnB58i0zoAe4QJYl3MegOSjEcdqkObK5PtzLhx7LOTuhyS46dqr_6KLXD2hHA6GAxUAkX7TbyJBlr8isUBUNJvyBkxQUI2M4RGolY56gSRX0nLaHGaVZ0dKdZkD3ZAELLKxHtNsGJtMjfBZ9CNfkoHsb-AC9u4cHuC5U2ehGNowa5t5B8rpzH6DgtUSknf5JbftK9D1Lrs72LqlDwn1Li2vX5PuBEDZ6-GaotRKdJYP-x1AqQ-dv8GaUR_8CSt0AP5T_Gpz0Y4TAvpGFBFFHdSYNrJB7IgM1wsqO73jbflbV64wp9Pcg-tr_0G00__y30000)

---

## **2. Phân Tích Cơ Chế**

### **Các cơ chế cần giải quyết**
1. **Quản lý thông tin nhân viên**  
   - Lưu trữ và cập nhật các thông tin như tên, địa chỉ, phương thức thanh toán.
2. **Tính toán lương**  
   - Xử lý logic tính lương dựa trên thời gian làm việc và phương thức thanh toán.
3. **Quản lý thẻ chấm công (timecard)**  
   - Cập nhật và lưu trữ giờ làm việc hàng ngày.
4. **Xử lý thanh toán**  
   - Thực hiện giao dịch qua các phương thức như chuyển khoản ngân hàng hoặc tiền mặt.

### **Giải thích lý do**
Những cơ chế này đảm bảo hệ thống hoạt động chính xác, quản lý dữ liệu hiệu quả và xử lý giao dịch an toàn.

---

## **3. Phân Tích Use Case: Select Payment**

### **Mô tả**
- **Employee**: Chứa thông tin nhân viên (id, name, paymentMethod).  
- **PaymentMethod**: Lưu phương thức thanh toán (bankTransfer, cash, ...).

### **Quan hệ giữa các lớp**
- **Employee** có quan hệ 1-1 với **PaymentMethod**.

### **Biểu đồ Sequence**
![Select Payment Sequence Diagram](https://www.planttext.com/api/plantuml/png/R90z2i9048NxESLS81Uma1HQM0XYy02RpHC3cnsPJ08vcuL7yWfc5HS9QUTzxuTvFPvbRqvjw08vRw9ywQ64QArDV7AJIWWxPwvsFQYM8JPEFq8tCnLqR3t8IxGPv7rt3p81H2c5Y-q2v0rN2F3skzD2_ph-EsVB6QOjHkHuFiIhq18irkgo9M4hRLbFo_8iFi9kqb29sAJFq1i00F__0m00)

---

## **4. Phân Tích Use Case: Maintain Timecard**

### **Mô tả**
- **Employee**: Lưu thông tin nhân viên.  
- **Timecard**: Thẻ chấm công ghi lại ngày và số giờ làm việc.  
- **TimecardService**: Xử lý logic lưu trữ thông tin chấm công.  
- **PayrollDatabase**: Lưu trữ thẻ chấm công.

### **Quan hệ giữa các lớp**
- **Employee** có quan hệ 1-n với **Timecard**.

### **Biểu đồ Sequence**
![Maintain Timecard Sequence Diagram](https://www.planttext.com/api/plantuml/png/RD2z3S8m40NWtbFS0bc00WK1FI8mm66_mf9_qEM8bDae68aLS0eBPD8-V-TtklVprO_AeeyO35lDGjSHOf3KwqmddYM7S63b6uymDYSj0LryX6Ln0sJo5fNNs9Zb4-gsBQGDxPpxklQvJ3ILPU8C5Oy9T8pta6V0jAPRRQgS5hTMLQDYzm9M_2-slj70qu_jaTnolWy0003__mC0)

---

## **5. Hợp Nhất Kết Quả Phân Tích**

### **Biểu đồ lớp tổng hợp**
- Quan hệ giữa các lớp được mô tả như sau:  
  - **Employee** có quan hệ 1-1 với **PaymentMethod**.  
  - **Employee** có quan hệ 1-n với **Timecard**.

![Class Diagram](https://www.planttext.com/api/plantuml/png/P91B2i8m48RtESNGbHMwSDjL5xeK1Bt0s0vj80z9Kg689tFXaRo2QPh65ZV9FFvycNy-htTb7HhNIy5gWTR2GTw47eZWmG0Au4q9NBaGAvHKmjaPhjfGkE4WIRaZkKvxtMcPiYUBn5KvOcLy4c59U-6IQZIph47dVzpxCwITxesTvbdIZHR2Q_2ATXeRmEATPYSRZvZZF7HRSgaP3UO_pSXEMyXs6MoB8jnhV_yIbQNvMKMg6PVw1G00__y30000)

---

