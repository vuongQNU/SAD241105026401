# MÔ HÌNH BIỂU ĐỒ DIAGRAM

## CLASS DIAGRAM
![DIAGRAM](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3XUNkeBFmzsp2nI2C_CouiCoK_EuadCIYuiHV8LgBWKGy0qEKx1I22ufoinBLx2n2V2simDBw8OSNfK7bu48EOEDG1NpIp-y82y38LYBiDlZuUxUvFY0Z8UxbiEiHnQ2ko3H8m2x4uBpVKhpWM9M2iaPYKKGCTz4NmzarMuWrKYM-kRdnNla9qFjW_8GLg5gHlKjaXpK_eUx9yQ775wR5--SyN1t9r0sCwy4ObbWQMAU0b2mNI4zy-7kzOaAoOSN9YlaW9p0XGXZNLqx1LG_MoaScN2a6MXvzk6zN2Wo4CKm1rifX6IKFjmzCvcBoo4rBmKKfm00003__mC0)

#### PK Là khóa chính của thuộc tính
#### FK là khóa ngoại của thuộc tính

## USE CASE DIAGRAM
![DIAGRAM](https://www.planttext.com/api/plantuml/png/T94z3e9048NxFSM4IWikO650Oa6XCKPZFO69473HtI4c6azcuP6yWiklMT3oxVlclSdi-_doDAFYyfGBZBXG49IQYnEfLYvGPa8eYXZbCIVmToku2-WnSDqvJ4AfIJ44gEAfCItT44l91jw4wzh_giOD4eeoqvMZZEWdSKWvYHLUJQPE_cIO3Qch6Aqugh3jKVvmUX0-6AYfwbOm0ySlEIbKUaDE2-bKi5rkmLkwbAIvCrkyRxFO_Jb6hjyTyH0UoRZwjmy0003__mC0)

#### Customer (Khách hàng) thực hiện các hành động chính:
###### Insert Card: Đưa thẻ vào máy ATM.
###### Enter PIN: Nhập mã PIN để xác thực.
###### Check Balance: Kiểm tra số dư tài khoản.
###### Withdraw Cash: Rút tiền từ tài khoản.
###### Change PIN: Đổi mã PIN của thẻ.
#### Bank (Ngân hàng) sẽ xử lý các yêu cầu từ ATM:
###### Authorization: Xác thực cho giao dịch rút tiền.
###### Request Balance: Truy vấn số dư của tài khoản.
###### Update PIN: Cập nhật mã PIN khi khách hàng thay đổi.

## PACKAGE DIAGRAM
![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3fULSsbnINvkQf6LWgwkdOA6Vr5AQf52G55-IcboYIQ6T4XHOdAs0bWHKD8n9JSp3ohZcvYNc9wAf1DPChGW9R4aLS4phomrhoI_g5AJYqi3PhAE0bYb9aHbM6PgESHy1PVKaiJCd69DBeVKl1IGMm40003__mC0)

## SEQUENCE DIAGRAM
![DIAGRAM](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3XUNkeBFmzsp2nI2C_CouiCoK_EuadCIYuiHV8LgBWKGy0qEKx1I22ufoinBLx2n2V2simDBw8OSNfK7bu48EOEDG1NpIp-y82y38LYBiDlZuUxUvFY0Z8UxbiEiHnQ2ko3H8m2x4uBpVKhpWM9M2iaPYKKGCTz4NmzarMuWrKYM-kRdnNla9qFjW_8GLg5gHlKjaXpK_eUx9yQ775wR5--SyN1t9r0sCwy4ObbWQMAU0b2mNI4zy-7kzOaAoOSN9YlaW9p0XGXZNLqx1LG_MoaScN2a6MXvzk6zN2Wo4CKm1rifX6IKFjmzCvcBoo4rBmKKfm00003__mC0)

#### User (Người dùng) tương tác với LibrarySystem (Hệ thống thư viện) để thực hiện việc thuê sách.
###### searchBook(bookTitle): Người dùng tìm kiếm sách dựa trên tiêu đề.
###### checkAvailability(bookTitle): Hệ thống kiểm tra tình trạng của sách từ kho sách (Inventory).
###### bookStatus: Kho sách trả về trạng thái sách (có sẵn hoặc không có sẵn) cho hệ thống.
###### requestRental(bookID): Nếu sách có sẵn, người dùng yêu cầu thuê sách.
###### updateInventory(bookID, "rent"): Hệ thống cập nhật trạng thái sách trong kho sách để đánh dấu sách đã được thuê.
###### confirmation: Kho sách trả về xác nhận cập nhật trạng thái.
###### rentalConfirmation: Hệ thống thông báo cho người dùng rằng sách đã được thuê thành công.
