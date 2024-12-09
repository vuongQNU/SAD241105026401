# Payroll System Use-Case Design Solution
## 1. Exercise: Use-Case Desgin
### 1.1 Use-Case Realization-Run Payroll
Mục tiêu : Kịch bản này tập trung vào việc thực hiện bảng lương mà không cần bảo mật bổ sung hoặc xử lý phức tạp, với giả định rằng hệ thống có thể truy cập tất cả dữ liệu cần thiết một cách liền mạch.
---
#### 1.1.1 Run Payroll(with ss interface)
## Mục tiêu : Kịch bản này tập trung vào việc thực hiện bảng lương mà không cần bảo mật bổ sung hoặc xử lý phức tạp, với giả định rằng hệ thống có thể truy cập tất cả dữ liệu cần thiết một cách liền mạch.
## Quy trình cơ bản :
### Bắt đầu tính lương : Được khởi tạo bởi đồng hồ hệ thống hoặc người dùng quản trị.
### Xác minh nhân viên : Hệ thống kiểm tra xem đó có phải ngày trả lương hay không.
### Thu thập dữ liệu : Hệ thống sẽ thu thập thông tin về thẻ chấm công và lệnh mua hàng, sau đó tính toán số tiền lương.
### Tạo phiếu lương : Phiếu lương được tạo dựa trên số tiền đã tính toán.
### Phương thức thanh toán : Hệ thống xác định phương thức thanh toán của nhân viên (chuyển khoản ngân hàng, séc, v.v.).
### In ấn : Nếu cần, phiếu lương sẽ được in.
### Giao dịch ngân hàng : Nếu phương thức thanh toán là qua ngân hàng, thông tin tiền lương sẽ được gửi đến hệ thống ngân hàng để xử lý.
Run Payroll- Basic Flow(with ss interface)
![Package Diagram](https://www.planttext.com/api/plantuml/png/Z9HBJiCm48RtESMegrQ2IAL09HPGKR5WrKfmWQdZ4gkn7JcEKCx6WYDn1Mp7piDffQwY6V_Vl9M_dzzDfL7fcXS94YqLp3wQIbE-BIGvpG0h6DX9QQICi1A53a9mB_0kD5L793HckeSnlCT6oQBOIg7jboh7JRnZw8sNXMnecoCOOyaduvIWofma657gMf4SAmexbOMytkKyaq99JlqiWX595BDDHZFmthv_Fr_l7sgI33KUR4cpLnGdFpwdi7Ph1dwWY3BssZvfCbW5t3wVtGmymJ85TmVpHN9MOSZ9RXncG5KBADj7WqzbXWsxyiWIM6MH39ihYJluejeYW5pMmjRPAOowstIGcnGMqC7Dn576p6Zf7TXcskzQv2LYuhBI5H0iI5sWfllBtOIxyTWg1QAeGURVJEU-fUi6SHy6mQavFKvrBhEBMQCBz24UKYZjopnKPV1OsTCTj0pOTOK-fgxIWxrMF_spM7-q7boRKwGYQqcjK5Jcy9aKNRatVT15Ci17mUAcrxP-5tSOSf5iZCl-_Fu1003__mC0)


Run Payroll- Basic Flow(with ss interface)

![Package Diagram](https://www.planttext.com/api/plantuml/png/Z9HBJiCm48RtFiMegqO2f88G4Wkeg5XqrKZb0fRZjbOTEx8TKCx6WYDn1Vp8vDLKOjNCpF_D_9uw-Vt-MLj7ZQjBIGXbJXjOx1lhU0aRgTbv0TH2IiGODRaHod4Jo-qpbjweEhT8B8SuXOGmhPpH4cV4bji07oZZqrbTeSToslXVkKcnH0FJR0ziexazDv-Y7J3A484plBGtceH3urmvuPfeW9ruknSCkceWjkgWJKcTqAex_Y3NTweDEr7BTwR0OmmpdUv3b9nHKqG91btrlQoaRdWw6WQ43BO8jxSlirk5PrZTGVptbncPLGJqOhcHMu6f5LIfvd5oAGimEagCfuGDK46RPVRwF-OUZjm526YfQnMyTeeWnvMWt0y9WCEqyBkVCgDDTs2QbE_caVarUEm169MibjJnF9phsYxmjhIWnmpt37m9TyAp7QIcBhlIO7HpsowFK8Na4flVmDxvn34ZOtKqaDvJ9FsY4dlLyU0DQA4dA7YbhHWEd5nmFtc0XJQNNVneorK1pb1b_MV3Oy75skV2X-WF003__mC0)


Run Payroll- VOPC (with ss interface)

![Package Diagram](https://www.planttext.com/api/plantuml/png/Z5NDRjGm4BxdAKQzi22sPQyh90ehfFRKLSiBJEqfiTO_aUrGHT0duy0ZyGhOJkBQsHmu9VxcypUVPvp9tzz_hfr7wtibc-OD72Gw1u-crnpjqB2qV1YS9tMGXfrkjIVxX8pWPmDmTGLfy-Pjyp9nZpXO8-N1Q1-VP6UYxJLqOx2aMn4LpsIxY1UyBwXFeusSc3I7nm23jwWTCY-CtlYMWWFM4Zl17kRNzn3mA76hdqmK9Us57-3Yg-ga6OWk01tCYvG1D2gAJvfHmUCoPHH19YwSOG9biC9w6_Lqhnx9nWXoRicv-DgrHbCH8eL2fW0EAXW1HRurV3oLS17cE7mAXq_8T_8H0bIXANw15llBI3PPWi6ZZNGl536qUGD3oNg9FXPkKnO7larCIEN9grIUrlJMmREn9-BJOQ0ZA-Q3EFn1PVOvQsMhxtZ8Mpegii_DIybpKrFoiHQJVKj1O_CiV3lXfSfDi2c7giqrz7eQETm7eUpu9aELhGUKQ0NnId89JYwrxb6cs91bFnTW9NmmIWddmYLUYAy5nWGiHohdnzwo5XtTMKxM5KquLFmgUxLdh7Y9p1zTxEJnRkxXIvmOznJkJf1qhUXSipegjjlpiR27tNRNd4-Bo5tEX3rykBpSmJOzrlSKy-4_sCM8UEM-M-VcajVS30TA_ZB2eTRYHRhp-CTVWR6uauleyderP_SjqTOkIhDwUwAdghtPsAvfhiDWZN-3Vm000F__0m00)
 
 ----
 #### 1.1.2 Run Payroll(with Security)
 Run Payroll - Basic Flow ( with security)

### Mục tiêu : Trong luồng này, quy trình tính lương được bảo mật và đảm bảo chỉ những nhân viên được ủy quyền mới có thể truy cập dữ liệu nhạy cảm (như thông tin chi tiết về nhân viên hoặc phương thức thanh toán).
### Những cân nhắc về bảo mật :
### Quyền truy cập dữ liệu : Quyền truy cập hạn chế vào dữ liệu nhân viên và thông tin bảng lương.
### Mã hóa : Dữ liệu nhạy cảm như thông tin ngân hàng và thông tin thanh toán được truyền đi một cách an toàn.

![Package Diagram](https://www.planttext.com/api/plantuml/png/Z9HBJiCm48RtFiMegqO2f88G4Wkeg5XqrKZb0fRZjbOTEx8TKCx6WYDn1Vp8vDLKOjNCpF_D_9uw-Vt-MLj7ZQjBIGXbJXjOx1lhU0aRgTbv0TH2IiGODRaHod4Jo-qpbjweEhT8B8SuXOGmhPpH4cV4bji07oZZqrbTeSToslXVkKcnH0FJR0ziexazDv-Y7J3A484plBGtceH3urmvuPfeW9ruknSCkceWjkgWJKcTqAex_Y3NTweDEr7BTwR0OmmpdUv3b9nHKqG91btrlQoaRdWw6WQ43BO8jxSlirk5PrZTGVptbncPLGJqOhcHMu6f5LIfvd5oAGimEagCfuGDK46RPVRwF-OUZjm526YfQnMyTeeWnvMWt0y9WCEqyBkVCgDDTs2QbE_caVarUEm169MibjJnF9phsYxmjhIWnmpt37m9TyAp7QIcBhlIO7HpsowFK8Na4flVmDxvn34ZOtKqaDvJ9FsY4dlLyU0DQA4dA7YbhHWEd5nmFtc0XJQNNVneorK1pb1b_MV3Oy75skV2X-WF003__mC0)



  Run Payroll - VOPC ( with security


![Package Diagram](https://www.planttext.com/api/plantuml/png/Z5NDRjGm4BxdAKQzi22sPQyh90ehfFRKLSiBJEqfiTO_aUrGHT0duy0ZyGhOJkBQsHmu9VxcypUVPvp9tzz_hfr7wtibc-OD72Gw1u-crnpjqB2qV1YS9tMGXfrkjIVxX8pWPmDmTGLfy-Pjyp9nZpXO8-N1Q1-VP6UYxJLqOx2aMn4LpsIxY1UyBwXFeusSc3I7nm23jwWTCY-CtlYMWWFM4Zl17kRNzn3mA76hdqmK9Us57-3Yg-ga6OWk01tCYvG1D2gAJvfHmUCoPHH19YwSOG9biC9w6_Lqhnx9nWXoRicv-DgrHbCH8eL2fW0EAXW1HRurV3oLS17cE7mAXq_8T_8H0bIXANw15llBI3PPWi6ZZNGl536qUGD3oNg9FXPkKnO7larCIEN9grIUrlJMmREn9-BJOQ0ZA-Q3EFn1PVOvQsMhxtZ8Mpegii_DIybpKrFoiHQJVKj1O_CiV3lXfSfDi2c7giqrz7eQETm7eUpu9aELhGUKQ0NnId89JYwrxb6cs91bFnTW9NmmIWddmYLUYAy5nWGiHohdnzwo5XtTMKxM5KquLFmgUxLdh7Y9p1zTxEJnRkxXIvmOznJkJf1qhUXSipegjjlpiR27tNRNd4-Bo5tEX3rykBpSmJOzrlSKy-4_sCM8UEM-M-VcajVS30TA_ZB2eTRYHRhp-CTVWR6uauleyderP_SjqTOkIhDwUwAdghtPsAvfhiDWZN-3Vm000F__0m00)

 ---
#### 1.1.3 Run Payroll(with Distribution)
 Run Payroll - Basic Flow ( with Distribution)
 
### Mục tiêu : Trong luồng này, quy trình tính lương được bảo mật và đảm bảo chỉ những nhân viên được ủy quyền mới có thể truy cập dữ liệu nhạy cảm (như thông tin chi tiết về nhân viên hoặc phương thức thanh toán).
### Những cân nhắc về bảo mật :
### Quyền truy cập dữ liệu : Quyền truy cập hạn chế vào dữ liệu nhân viên và thông tin bảng lương.
### Mã hóa : Dữ liệu nhạy cảm như thông tin ngân hàng và thông tin thanh toán được truyền đi một cách an toàn.

![Package Diagram](https://www.planttext.com/api/plantuml/png/Z9HBRi8m48RtESM85KXj9A2qKXSjAke2gIgez0A3Oy0YiIF7KPMpTT4ZzGgr7JiF0nKhcF7_pHj-lt_cXKAfoYoDa2WXOR2f2aMpHIh8SG1OGCUESYrbXEN8bHU2VO4bLrJkaD2GQHxwy3jcZE-jkFxQVrwkiP8YJHU2A_D9fPMUkllOQvQdeg9r4TxeIpvPHWdAn4gyqPUiIqaEM51OoSGbzYxh2THOaGDrm_96897CJ24OalEs0t8BSFwk9afGuTQKD7X1VdJpjGfZrwRdEueWOwjjaqQTNS7jqzdLmIECOx27CXn5PnMQhFTejLhz9iInp8SRfJlONuPEDse3J6BuABaP9nYlpdf6g76_OmUDWHMGQoZ1wbfc0dkgB8IPABdfi55eTNCZNgwJ641vD-Cx4JAzSsd0EjDwLIFF0HEM5K-1O4hA51LT_zEEFpd7JMCWacfc-CNKmVLqvIZk_2Wogiyse-eWaijvW_DrYv_5a9kNeQzh59qeMzebdfcBgR4hIxsFRQrRS-jk0-UvzkOT-Q0lcVAaHfL4NkZV3HEyAVYcZJgAEdWlMBzj4tNiudP3ZgAvTfa_rpy0003__mC0)

 Run Payroll - Basic Flow (with Distribution)
![Package Diagram](https://www.planttext.com/api/plantuml/png/Z9HBQiCm48RtFiMGbGDD82cbq4LR6he8bCQGNa38IY8YIqQMMtosBdgaNg4ZoMCxYGCbYtXc_czUilpx_SEuCnOcswPoee2LClmu0LP1T0GxQJMPbTe96yBjCuLUc3wsI0XxEvf9mersrYYg4LAkFRnZN9pNwW8zziuAgVT161_xKCOQ_5UhQ2lgxTpR0-lGzrROJzdMFl4aaigZj9yX2eSp2UsaQq83_23QbP7HHJsnrZjZ2-QaqTrc1hu-KstvWLLYOtCQO-ZfT1-o49pPF4Z8wAAlHQbC8-9eP2J9OC4mcpsEBXmUO367oZ7hqcaoga0oda3GelhDc6DTfbk7EznVWv2wE96GO0csrb366DPCBcKUfZ4YCr-0h3oKioQTFlsFMS9UE0y1Aqoj_O2TmijfZoJ78Xvmv9PuOEVCoV5qOAoKRSQHyJNWxnOuKxnMp8dCptLj5_IAjI1YLY03Nz8TQBQTCinDhoGuUTtRB7TGUcTAoM-03lHK7Hg8zvv8N5HahtOyk3OjT0-vA4qbXmNFRWLM7c0-pMKMB5q9dOEpJ5Vu6KBCT_6ClhfGVm000F__0m00)
 
Run Payroll - VOPC (with Distribution)

![Package Diagram](https://www.planttext.com/api/plantuml/png/X5RDRjim3BxxAOJkaWv8krsDeMWR36Y0jGsQ3JipCfjeaIL3aeiPQvziXptINc6IR2UIBMSwn8BuyUEFA39_V_-vrWQKgKkUPHNGFMoHtCi2EVcL4Rie1wt9kj46omMNTByK1jKpKEm0RbrU4iyoE_T7R_utK7-0aebje408bt9VLrCAonKqIdA-aCAuBwf8MTM2L2qYOcYL_wkxIgW6-jy4ew3D4mffy77p0wa96Dwbv1rLkoYN0gCJ_5b9PI9eO9KTChfIVfzACI6L4yvis7I7T9-xCFskvnjmBMz1xDjxYsWAhAHcHpVy1uLXfY6VouhB1cEx0ahCoTfOyzimfWwxB79dDP1ihE6bU9OvkUrsgWJ3f0WmMb86V8sqLjRmGrrkK2MCG54er3eXgNOsoPDwM0BZAIreIXlhFPgTB4PoMyPCsxGMqCpESxAHaeUoBHehl2bbRU_1of-v13C670quqDY4HVLvSO2f7BN8HQsKvVlAIgIWF6E_3v4KEAqv65orhXzTYo-uhvdeWi57b8Y7AhIKiqYUAfixMIlU98jdvqLFbYQThxk3FELsnxy63efXaRG0GjIsaXoaITku2H2dajCdTXI0_YxL7eiXko-d5IgMBYKDBs4NQ7tfRVItFrQhgy9cut3Xtlw9t2zaMJAjRULCv8SU0DEtiAeLtO76HrMWqiwlBqoRJz7nrR0o8zwJHHVIn5F3sPQ9N7G4RJyUl90eEjTh7j8D2YXrTJlP8vIiZJr9oD-ojomvyURpAz8Fisb4OdXbMJO-dCzVhpgsAMbYr2IWPnykBZwUUTlTTZH8yhPQ_UEtGdjycgVRXqCa9mLJRXPs4qIJjfMyC9ZWUX_vTAZEB3jipmAtBVhGdew8Jw_p-Q3138J3xf2DseM7fHxAf2F7Nf0b7zZGxwZ2i-mQHU7-KVq3003__mC0)

---
#### 1.1.4 Run Payroll(with OODBMS Persistency)
 Run Payroll - Basic Flow (with OODBMS Persistency)
 
### Mục tiêu : Trong luồng này, quy trình tính lương được bảo mật và đảm bảo chỉ những nhân viên được ủy quyền mới có thể truy cập dữ liệu nhạy cảm (như thông tin chi tiết về nhân viên hoặc phương thức thanh toán).
### Những cân nhắc về bảo mật :
### Quyền truy cập dữ liệu : Quyền truy cập hạn chế vào dữ liệu nhân viên và thông tin bảng lương.
### Mã hóa : Dữ liệu nhạy cảm như thông tin ngân hàng và thông tin thanh toán được truyền đi một cách an toàn.


 ![Package Diagram](https://www.planttext.com/api/plantuml/png/Z9IvRkCm48PxFiKWbGHi5h0NsG0faaMEmiKY1fmopO2YRI8KQP1K5dgsBV98UONmqEYo3QIov_Zc-4VIv_-FFywZzKsj64FkZOMBJUkygE516Vvs0UWWEv9DEMihjHSsXRl_5Bf7_TOXAHpjR3B6ZVRMAEgHIguYl4Kkvhtwm82jiGs_wl7-BshSKV-PyoZz8TjgcZzu1s2LTja8-owxUIOU9ccaa3hibHF7UmhjfM_J07mlEXd9wAEHMEcjiJLwQNIlriWtL6eitwCJpxQYDSQUFkz5reAZhL8A6NtqgJuequgy6XcCZKI7oylRaqU06rZyXFIm52KxcH7H8t4Jjm3RQ3ZaMC3PSLg4QQB4B0CbNOGgR8loxWmpltxk5zYTy5IlS3vSSLV2guwnt-3mNHHqZnzzt_9xSorZxJWOO6qQ7VNeCs8woTwDiip3W2Ut3FUTCvDhzc3kj7u-ZPoMEc2_WAFYZK8lrb4xTavmag0Z0sT5WE2Vz7jQRgiC-dFAJ5wFhieL7A9pfEycoy-csMc0_EqWCYYLsREFoEWrww1hgCJ1E3bkE7kBGkSH5iiSLmcjdT0LU8lQXKzPm8ho2m00__y30000)

 Run Payroll - VOPC (with OODBMS Persistency)

  ![Package Diagram](https://www.planttext.com/api/plantuml/png/X5PBRjim4Dth58HNJW0dxLO8WYHkWHYeKwCkqFMOdDY4ALBW9u3GvcHTz4YzGgc_A54k5zQ0y-RBnw7__lxpO2newpAH93dGCnoHR1L3GNucn2ygm1YoBup5R2qKFM-aHVqA51j0kMvlIULbULLjlIS3qnqKMWcnLjAMNzG3EqAqamsWivsOVdhQWlHvXPO6th2ngTSHxNUU8GNDnlkViroe0Z68KITP_V2kffskv5YHXEIbSfb3GKz8pscPNoK5LVU-DayWptNd0ZSCSsNug5aeBRS5QJCD32Hac9AzzU6FWsrii1kMbb47ceCFl96lAYLFZQGpi5p9OVyKvI3sI9tsWLzSTa0T2GACQJGceibFIkAi7MR0HSmAYipNkaLxKcoYzqJYnhULGR6yIib1AJ7K-QFqoiTCENyENlyg5DWfe0zGWgOXFAhjImcOwr6DN3kjlR-UMYbfvI6IWg1EWCLTdNgVMdZ0BMU20uQgeaWzLADtkGpqCTeyAwT54INFgL9zysxY_NhkzB6q6_zx4A0vicW4aD9v9fMG8XxZSO2ur9osiPC2p0-bpyZ6tYiwxL3pE9L68wBEfOtHdlxKpENCTwCxy2h-XTwlLPPnOpnpPlf3Ey3yAUoSfYSm-5KprARCwmitzYxOlXypC_1xaNH3D-7SBcEhI2-26Jww8K5rvQnvYGyeeBJaxUoCqCfPlnFHloS-_lJbM7nSaDNgllfE7eV_u6DFMCpamyrDQrMBaoSXhNbNNMElzDkN_JJoy3b82UCQgMtV0aFgeV36OSRNTP1JnxCawSJ58EthHJzeUiJThzLgD2f6ol4zJoONluB5A3-RI7-ha-XL6USTS3L97b0o_-_a7m000F__0m00)
