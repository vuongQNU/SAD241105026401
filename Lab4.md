# PayRoll System Use- Case Analysis Solution
## 1. Use-Case Analysis
### 1.1 Use-Case Realization Interaction Diagrams
#### 1.1.1 Login
##### 1.1.1.1 Login-Basic Flow
![Package Diagram](https://www.planttext.com/api/plantuml/png/V94nJaCn38PtdyBgr4fm0GPKbaxT40Tm4xSl8YzviftsS0mSYIlW11LKaCWGAVu___uZVxozRzL8hCqPA5WLV54MMBoKGbge6AxszPJAhigyGbBSxsxLfsOJ5t-JfLgUMSufy22x0j3zyFxH-_017VHNyrAXcP5An8LKBrNYUWEEEDZR73rJJf6CrrVwxXlTm61-s31nUCKW77iIoegfe3VJWPI1ic4wtiZ37D3FrMd44xOc1RM5mAf3_yeqFj7rc8I3eLMtr-bGII9mLluz89N_HnmfvIRyTuHEzO8iufkOFGET6BX4sFhLT_G9003__mC0)
###### LoginForm: Đây là giao diện người dùng (UI) nơi người dùng nhập tên đăng nhập và mật khẩu để thực hiện đăng nhập vào hệ thống.

###### AuthenticationService: Đây là dịch vụ phía sau xử lý việc xác thực thông tin đăng nhập, kiểm tra tính hợp lệ của tên đăng nhập và mật khẩu bằng cách so sánh với thông tin trong cơ sở dữ liệu.

##### 1.1.1.2 Login-Basic Flow
![Package Diagram](https://www.planttext.com/api/plantuml/png/LCyn3i8m30NGtQUmc5e9Bi20ojAf6-809h5eHEjKJbeEny2Hk09E9K2Cjj-txDVZsQHCckTn078vAfuJAqpM2YvC91atNRm6QQEE6wI4NVi_FSwvPx6QSeXoObs2urMM2K3PXxk3vN2F1gsQhIKqCf9ud2YbUrHVrM34O8aPNMW8dZ9N7xtzqXfMyxEkPtT3f-pB9JGa388MfWib1cXOV7dm3G00__y30000)

#### 1.1.2 Maintain Timecard
##### 1.1.2.1 Maintain Timecard - Basic Flow

![Package Diagram](https://www.planttext.com/api/plantuml/png/d5GxKiCm4ErrYYsX81dRWI85ana-7JCKN42H5iUC9MLM4apEHi6Hk09Ib8zDh2HGkB2rx-Etp_x-_9fPnybvrJ8kd25uKClMh13Pt7WjEQtWfL4eECb7Gue9ensPTlVmBjstI0orQzn-d4dk-9nRX6SoRoZS4zUyHXN6xZSdUus34SQsHk3gjcS1fb2CO3m6nHljmWLkStfnoNg37U3U9aoBKH7XDJeGdYY83J5q41sUjVXv13dvG516EA7pf0yO8En047A7eF7ZX9sKHp6gZX1cCzc5EObesTXborUdOVqehtT9B3ZL2C98jDaOiqs8L9DEh7soF6o8Ct6L_-4QViT9FzyEtvdhkSd1ynqlrnKFzWBZmdYoy1gBaS3QgpcIFMj5PKhLBsMir1-ANcvx_WjwxCEirgujVnzKEcQpIbevQCvabVOSOM5wXbh6FzaF0000__y30000)

###### maintain timecard(): là hành động đầu tiên để quản lý và duy trì thông tin Maintain Timecard
###### get current timecard(): là lấy ra thông tin chấm công hiện tại từ hệ thống.
###### return current timecard(): là thông tin mà giao diện người dùng (giao diện TimecardForm) sẽ hiển thị cho nhân viên.
###### display timecard(): là bước mà nhân viên có thể xem và điều chỉnh timecard của mình.
###### get charge codes(): là bước kết nối giữa hệ thống chấm công và cơ sở dữ liệu quản lý dự án.
###### return charge codes(): là dữ liệu mà nhân viên sẽ sử dụng để phân bổ thời gian làm việc của mình.
###### enter hour for charge numbers(): là bước nhập liệu quan trọng trong quá trình duy trì thời gian làm việc của nhân viên.
###### update timecard(): là hành động làm mới thông tin chấm công với các thay đổi từ người dùng.
###### save timecard(): lưu lại thông tin chấm công sau khi người dùng hoàn thành việc nhập liệu.
###### save(): là bước cuối cùng trong quá trình lưu trữ thông tin chấm công vào hệ thống.

##### 1.1.2.2 Maintain Timecard - Basic Flow

### 1.1.3 Run Payroll
#### 1.1.3.1 Run Payroll - Basic Flow

![Package Diagram](https://www.planttext.com/api/plantuml/png/Z9HBRiCW48Rtd09bPKlj1RfeeaPTT9L8xGKccDGe62myLkMpTT4ZzGe56sp0YPgLDJFVpppbt--VNOTWi6ya8S1G6xfv7phapLvgTjbGw6XaazQoWeaM50QGZX7wff2RCp2UQ-P0AZx2OBIKUwtGVRaPTIjlAdfjMga7FkK8HefyY8OpCDM812DBtHjMGyVfmLGXhtUDdbMXhEP-5i7842DSazaCl7Vfty_N-sE6L81mSYLjNa1T_FX6mjcJ6VGHaMLSs2KfYLP17v-lReO-qV4AYf9S3LlPQZ7KYaolQ3i5h7IDM5rOagL5v-0AXcBxF_p9qT4K6jqhLzWSirnOg-Smc4ATTOOcY_NyyJ2HsnIDiZEGh9U0t9PvgxDm2WuttBB5by3Q5tntWmst1zHmh7LrCr5sHrRSEbSHAh2w75baCtrVIITtN7wEL_dbnjpLS5LD4ZIWEdkWGgkvheVbjP94kkILv0ZTS_5B9I4xwtD_fpy0003__mC0)

---
![Package Diagram](https://www.planttext.com/api/plantuml/png/Z9HBJiCm48RtFiMegqO2f88G4Wkeg5XqrKZb0fRZjbOTEx8TKCx6WYDn1Vp8vDLKOjNCpF_D_9uw-Vt-MLj7ZQjBIGXbJXjOx1lhU0aRgTbv0TH2IiGODRaHod4Jo-qpbjweEhT8B8SuXOGmhPpH4cV4bji07oZZqrbTeSToslXVkKcnH0FJR0ziexazDv-Y7J3A484plBGtceH3urmvuPfeW9ruknSCkceWjkgWJKcTqAex_Y3NTweDEr7BTwR0OmmpdUv3b9nHKqG91btrlQoaRdWw6WQ43BO8jxSlirk5PrZTGVptbncPLGJqOhcHMu6f5LIfvd5oAGimEagCfuGDK46RPVRwF-OUZjm526YfQnMyTeeWnvMWt0y9WCEqyBkVCgDDTs2QbE_caVarUEm169MibjJnF9phsYxmjhIWnmpt37m9TyAp7QIcBhlIO7HpsowFK8Na4flVmDxvn34ZOtKqaDvJ9FsY4dlLyU0DQA4dA7YbhHWEd5nmFtc0XJQNNVneorK1pb1b_MV3Oy75skV2X-WF003__mC0)
code từ plantext
@startuml

actor "System Clock" as SystemClock
actor "Printer" as Printer
actor "Bank System" as BankSystem

control "SystemClockInterface" as SystemClockInterface
control "PayrollController" as PayrollController
control "IPrintService" as IPrintService
interface "IBankSystem" as IBankSystem

entity "Paycheck" as Paycheck
entity "BankInformation" as BankInformation
entity "PurchaseOrder" as PurchaseOrder
entity "Timecard" as Timecard
entity "Employee" as Employee

SystemClock --> SystemClockInterface : 1. start()
SystemClockInterface --> PayrollController : 1.1 run payroll()

PayrollController --> Employee : 1.1.1 is payday()?
PayrollController --> Employee : 1.1.2 get pay amount()
Employee --> Timecard : 1.1.2.1 get timecard info()
Employee --> PurchaseOrder : 1.1.2.2 get PO info()
Employee --> PayrollController : 1.1.2.3 calculatePay()

PayrollController --> Paycheck : 1.1.3 create with amount(float)
PayrollController --> IPrintService : 1.1.5 print(Paycheck, String)
IPrintService --> Printer : 1.1.5.1 print()

PayrollController --> IBankSystem : 1.1.7 deposit(Paycheck, BankInformation)
IBankSystem --> BankSystem : 1.1.7.1 send transaction()

@enduml

#### 1.1.3.2 Run Payroll - Basic Flow

## 1.2 Use-Case Realization view of Participating Classes (VOPCs)
### 1.2.1 Login
#### 1.2.1.1 Login-VOPC
![Package Diagram](https://www.planttext.com/api/plantuml/png/DCun3i8m40J0tg_OCaX8-KAgL7pYi4zWOP_HdGC5ucKKF8alv0Ias6vsjP_NUx9EsfTQGeY5p71efonpq_e8m3Y2fRDYCLQXoY19kBgxDqt3xaTkL7AYpiEczfluWtZcU45KJhwMgHYom1jq9EFlojCJ9fRaJrO0003__mC0)


### 1.2.2 Maintain Timecard
#### 1.2.2.1 Maintain Timecard-VOPC
![Package Diagram](https://www.planttext.com/api/plantuml/png/j5HBRjim4Dtp58DiqXQm4s-xQO0stGN8eXSOanER2Jy2XseX63bP5prIhr1-H9LsR7HL0H8u__VUqFxzyzSTHmnnj4Q8QxXtKSS9f45cObX1t7kczCK8WOP0J2ucaq1XH42dGFf0i1rPEs86oWqqiQ3QwUhU3iPFH5U03Cqu24YFGqlbGBCRj2hs5jqBQFVaYyLUQZJ09CUGMxhHRYbmYQ5I2LCz3tllw2XA5hMfCPniHcuf4Sf3Rcv0StOhd3wzUryzEuhP1MZzwEA9jwll8mlMtfcGXYAKjYGnB0KIvMWmqYDEnILU_ulct-QnHNDeLXLzxyV0yCE75r9D6XWew2OButVgkJGEFSbnI52ef_SgX2WCbd5VVR27saPf7amQSog77yYrSy9EOKRtv0F8FORTiiwMbHRgOdhVjCgeJ_0Sm_diNGpUc3JayEz5bLX58BrQz7ZB-z9mKVS9Zy4_aumFw717-GfzIJlSOjhlNnJSZ-9Qtwi8gnMSum4VORFQY3EHLD1-QYdfThtkytBqJCsSbp_fLip2jBoZukFM7ov2kCoz5gQhVhlUY3joAl_z_0400F__0m00)

### Timecard : kiểu entity
### TimecardForm : kiểu boundary
### TimecardController : kiểu control
### ProjectManagementDatabase : kiểu boundary
### Employee : kiểu entity

### 1.2.3 Run Payroll
#### 1.2.3.1 Run Payroll-VOPC
![Package Diagram](https://www.planttext.com/api/plantuml/png/Z5NDRjGm4BxdAKQzi22sPQyh90ehfFRKLSiBJEqfiTO_aUrGHT0duy0ZyGhOJkBQsHmu9VxcypUVPvp9tzz_hfr7wtibc-OD72Gw1u-crnpjqB2qV1YS9tMGXfrkjIVxX8pWPmDmTGLfy-Pjyp9nZpXO8-N1Q1-VP6UYxJLqOx2aMn4LpsIxY1UyBwXFeusSc3I7nm23jwWTCY-CtlYMWWFM4Zl17kRNzn3mA76hdqmK9Us57-3Yg-ga6OWk01tCYvG1D2gAJvfHmUCoPHH19YwSOG9biC9w6_Lqhnx9nWXoRicv-DgrHbCH8eL2fW0EAXW1HRurV3oLS17cE7mAXq_8T_8H0bIXANw15llBI3PPWi6ZZNGl536qUGD3oNg9FXPkKnO7larCIEN9grIUrlJMmREn9-BJOQ0ZA-Q3EFn1PVOvQsMhxtZ8Mpegii_DIybpKrFoiHQJVKj1O_CiV3lXfSfDi2c7giqrz7eQETm7eUpu9aELhGUKQ0NnId89JYwrxb6cs91bFnTW9NmmIWddmYLUYAy5nWGiHohdnzwo5XtTMKxM5KquLFmgUxLdh7Y9p1zTxEJnRkxXIvmOznJkJf1qhUXSipegjjlpiR27tNRNd4-Bo5tEX3rykBpSmJOzrlSKy-4_sCM8UEM-M-VcajVS30TA_ZB2eTRYHRhp-CTVWR6uauleyderP_SjqTOkIhDwUwAdghtPsAvfhiDWZN-3Vm000F__0m00)

### SystemClockInterface : kiểu boundary
### PrinterInterface : kiểu boundary
### BankSystem : kiểu boundary
### PayrollController : kiểu control

## 1.3 Analysis-Class-To-Analysis-Mechanism Map

| Analysis Class                | Analysis Mechanism(s)       |
|-------------------------------|-----------------------------|
| BankSystem                    | Legacy Interface            |
| CommissionedEmployee          | Persistency, Security       |
| Employee                      | Persistency, Security       |
| HourlyEmployee                | Persistency, Security       |
| LoginForm                     | None                        |
| Paycheck                      | Persistency                 |
| PayrollController             | Distribution                |
| PrinterInterface              | None                        |
| ProjectManagementDatabase     | Legacy Interface            |
| PurchaseOrder                 | Persistency                 |
| SalariedEmployee              | Persistency, Security       |
| Timecard                      | Persistency                 |
| TimecardController            | Distribution                |
| TimecardForm                  | None                        |
| SystemClockInterface          | None                        |


