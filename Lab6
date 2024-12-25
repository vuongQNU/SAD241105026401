1. Xác định các lớp
Dựa vào tài liệu và ca sử dụng:

Các lớp chính:
User: Quản lý thông tin người dùng (Học sinh, Giáo viên, Phụ huynh).
AuthenticationService: Xác thực người dùng.
LearningMaterialService: Quản lý tài liệu học tập.
OnlineClassService: Quản lý lớp học trực tuyến.
ParentDashboardService: Cung cấp thông tin tiến độ học tập.
Các lớp hỗ trợ:
Material: Biểu diễn tài liệu học tập.
ClassSession: Đại diện lớp học trực tuyến.
ProgressReport: Biểu diễn báo cáo tiến độ học tập.
2. Xác định operations và methods
User
Thuộc tính:
id: int
name: String
role: String (Student, Teacher, Parent)
email: String
password: String
Phương thức:
login(email: String, password: String): Boolean
logout(): void
AuthenticationService
Phương thức:
authenticate(email: String, password: String): User
resetPassword(email: String): void
LearningMaterialService
Phương thức:
getMaterials(studentId: int): List<Material>
downloadMaterial(materialId: int): File
OnlineClassService
Phương thức:
createClassSession(teacherId: int, topic: String, startTime: DateTime): ClassSession
joinClass(studentId: int, sessionId: int): Boolean
endClass(sessionId: int): void
ParentDashboardService
Phương thức:
getProgressReport(studentId: int): ProgressReport
Material
Thuộc tính:
id: int
title: String
contentUrl: String
uploadDate: DateTime
ClassSession
Thuộc tính:
id: int
teacherId: int
topic: String
startTime: DateTime
duration: int (minutes)
ProgressReport
Thuộc tính:
studentId: int
completedTasks: int
grades: Map<String, Float>
lastUpdated: DateTime
3. Xác định trạng thái và mô tả sự thay đổi
User
Trạng thái:
Active: Đã đăng nhập.
Inactive: Chưa đăng nhập.
Thay đổi:
login → từ Inactive sang Active.
logout → từ Active sang Inactive.
ClassSession
Trạng thái:
Scheduled: Lớp học chưa bắt đầu.
Ongoing: Lớp học đang diễn ra.
Ended: Lớp học đã kết thúc.
Thay đổi:
createClassSession → tạo mới trạng thái Scheduled.
joinClass → giữ nguyên trạng thái hiện tại.
endClass → chuyển trạng thái thành Ended.
4. Xác định phụ thuộc và quan hệ kết hợp
User và AuthenticationService: Quan hệ 1-nhiều, User gọi các phương thức của AuthenticationService.
User và LearningMaterialService: Quan hệ 1-nhiều, User (Học sinh) truy cập tài liệu học tập.
User và OnlineClassService: Quan hệ 1-nhiều, Giáo viên tạo lớp học và Học sinh tham gia.
ParentDashboardService và ProgressReport: Quan hệ 1-nhiều, Phụ huynh truy cập nhiều báo cáo.
