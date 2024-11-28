# Identify design elements
## 1: Subsystem context diagrams
### BankSystem Subsystem
#### Mô tả: Hệ thống con BankSystem chịu trách nhiệm xử lý thanh toán qua ngân hàng, bao gồm việc kết nối với hệ thống ngân hàng để thực hiện giao dịch (chuyển lương) và nhận trạng thái giao dịch.
![Package Diagram](https://www.planttext.com/api/plantuml/png/X9DBSiCW38Rtd48No0MowCJs1MZS2yYOJ9dmI45qXhDrqIFr2iMls8wTTWdw9Nty4ZzVtwT0w2aQpL2Gyy0nUQTrdG990nY0rsEaH7ljBihnN0ZXeYMqrDqM5MEyXiDBhnlIZr37nYY26oOZiyxBZoW3iLdI9sITj2qqNGFoQ4Dke9nb9HmUwhtDKSZW5CEgLbRp-WYLinVbpTHs3-mya2pRmRiA-LrfI_SQfK_xqWtXMLBqzj-w8odtxbErSbVEYkePjN3cXZO13YFOis81FgaQr6Y5V0wz4Qw1Yse6VfJkM5nr0GqNL5gswxbknZ-iYUWpDFOst7TbGpkDTsdQClKlerSjHjjEUVcw3_0B003__mC0)
#### Giải thích:

#### PayrollSystem: Là hệ thống chính gửi yêu cầu thanh toán cho BankSystem.
#### BankSystem: Là hệ thống con thực hiện giao tiếp với Bank, gửi yêu cầu và nhận trạng thái giao dịch.
#### Bank: Là hệ thống ngân hàng chịu trách nhiệm thực hiện giao dịch.

### PrintService Subsystem
#### Mô tả: Hệ thống con PrintService hỗ trợ tạo và in báo cáo lương, danh sách nhân viên nhận lương.
![Package Diagram](https://www.planttext.com/api/plantuml/png/Z95DQiCm48NtEiLSm1VmeXYoyQeOwGIAF0A1v557uu3FbaMEb2jKmau83RJTQjxtVj3zUXkAM9OrHMMT4CDaDwOOpLO44zW2apakepPYlMzlerPgCj1zmCHX4ODy2GvxCEiv1O6yUq1kHs3yMh68UfK-KUHAuJB3RCM2hp4Fc34J7nGoT6zX9rfyu7IaE4eveWHQVWGrplJmIHByTeZBwXoMejIetqVelIzWDQGDiJKgCUIT_MF6Gzlc_AVxg_Ml6qRTLm-wXFbPI0qriVtSDm000F__0m00)
#### Giải thích:

#### PayrollSystem: Gửi yêu cầu in báo cáo đến PrintService.
#### PrintService: Kết nối với máy in và cung cấp trạng thái in báo cáo.
#### Printer: Thực hiện in báo cáo.

### ProjectManagementDatabase Subsystem
#### Mô tả: Hệ thống con này lưu trữ thông tin dự án, dữ liệu nhân viên, và dữ liệu lương để sử dụng cho các báo cáo và xử lý nghiệp vụ.
![Package Diagram](https://www.planttext.com/api/plantuml/png/Z97B3O9048RlMyKqOBnpC1gzaX2eO7H7isOVE3jBGcqUBCaM18aOZGRE_-ERn_rwMqT1bkIimeC4XW9R3jPMRHHoW16AwgLmEDD1SlHu8dvAkL953elLf-R8omu5znWfWutMorHh589wS84cGMEZ-fk2HT-PPx0D_cZOZScXgADM4zIIX0qr1EHg6rfwmp56S_AzUtA0AkiHZT6_qj1DWZFsB-cIAChOqDrRqfpTlz5349ZgmABMv7N_jGS0003__mC0)
#### Giải thích:

#### PayrollSystem: Thực hiện truy vấn thông tin từ cơ sở dữ liệu.
#### ProjectManagementDatabase: Lưu trữ dữ liệu liên quan đến dự án, nhân viên, và lương.

## 2.Analysis Class to Design Element Map
| Analysis Class         | Design Element            |
|------------------------|---------------------------|
| Employee               | Employee Entity           |
| Payroll                | Payroll Processor Service |
| Bank Transaction       | Bank Transaction Adapter  |
| PrintRequest           | PrintRequest Queue        |
| Project                | Project Entity            |
| SalaryReportGenerator  | ReportGenerator Component |

## 3.Design Element to Owning Package Map
| Design Element           | Owning Package            |
|--------------------------|---------------------------|
| Employee Entity          | EmployeeManagement Package|
| Payroll Processor Service| PayrollProcessor Package  |
| Bank Transaction Adapter | BankIntegration Package   |
| PrintRequest Queue       | PrintService Package      |
| Project Entity           | ProjectManagement Package |
| ReportGenerator Component| Reporting Package         |


## 4.Architectural Layers and Their Dependencies
![Package Diagram](https://www.planttext.com/api/plantuml/png/V9512i8m44NtFSNGVQyWhIWYL2Y21nZYKA9f4f9qKSIJkV18Ni6qO9kcwlRF_oz_9g_7CxSEZMiRaMXaLwm9qigG9UdGSIMXn8vC2hS4W0cq5YhiZ1BYjFTASa-cMA6ruEn_gZAAaRNAZ8CZQMNSZYGPT5uFYUlMSkdjKAgQioLqssYXEg83Ik-VcFwL2p7taKFa1Xr2mTX0_SNhErdkstGnCfXuwdWAoBBLSiLO65nnvw-cQ84eC-C4ZUQf41IOSfBd_hVV0000__y30000)
#### Giải thích:

#### Presentation Layer: Giao diện người dùng, ví dụ: PayrollUI.
#### Application Layer: Chứa logic ứng dụng như PayrollProcessor, ReportGenerator.
#### Business Logic Layer: Xử lý nghiệp vụ, quản lý nhân viên và dự án.
#### Data Access Layer: Giao tiếp với cơ sở dữ liệu thông qua các repository.

