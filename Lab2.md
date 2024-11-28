# Lab 2

## 1. Phân tích ca sử dụng:

### Maintain Timecard
- **Mô tả:** Nhân viên hoặc quản lý nhập thông tin chấm công (timecard) vào hệ thống.
- **Actor:** Nhân viên, Quản lý
- **Các bước thực hiện:**
  1. Nhân viên đăng nhập vào hệ thống.
  2. Chọn tùy chọn "Maintain Timecard".
  3. Nhập thông tin chấm công bao gồm: ngày làm việc, số giờ làm việc, và mã nhân viên.
  4. Lưu thông tin chấm công vào cơ sở dữ liệu.
  5. Hệ thống hiển thị thông báo cập nhật thành công.
- **Ngoại lệ:**
  - Thông tin nhập không hợp lệ (ví dụ: số giờ làm vượt quá giới hạn).
  - Nhân viên không có quyền truy cập vào chức năng này.

### Calculate Payroll
- **Mô tả:** Hệ thống tính toán bảng lương cho nhân viên dựa trên thông tin chấm công và bảng lương cơ bản.
- **Actor:** Hệ thống, Quản lý
- **Các bước thực hiện:**
  1. Hệ thống truy xuất thông tin chấm công của nhân viên.
  2. Tính toán tổng thu nhập dựa trên giờ làm việc và lương cơ bản.
  3. Trừ các khoản khấu trừ (bảo hiểm, thuế).
  4. Cập nhật thông tin vào bảng lương và hiển thị cho quản lý.

### Select Payment Method
- **Mô tả:** Nhân viên chọn phương thức thanh toán lương (chuyển khoản ngân hàng, tiền mặt).
- **Actor:** Nhân viên
- **Các bước thực hiện:**
  1. Nhân viên đăng nhập vào hệ thống.
  2. Chọn tùy chọn "Select Payment Method".
  3. Chọn phương thức thanh toán mong muốn.
  4. Hệ thống lưu lại thông tin lựa chọn.

### View Pay Statement
- **Mô tả:** Nhân viên có thể xem bảng lương của mình.
- **Actor:** Nhân viên
- **Các bước thực hiện:**
  1. Nhân viên đăng nhập vào hệ thống.
  2. Chọn tùy chọn "View Pay Statement".
  3. Hệ thống hiển thị bảng lương cho nhân viên.

## 3. Java mô phỏng ca sử dụng: Maintain Timecard

Dưới đây là mã nguồn Java mô phỏng chức năng **Maintain Timecard**:

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

// Timecard class to represent a single timecard
class Timecard {
    private int id;
    private String employeeName;
    private String date;
    private double hoursWorked;

    public Timecard(int id, String employeeName, String date, double hoursWorked) {
        this.id = id;
        this.employeeName = employeeName;
        this.date = date;
        this.hoursWorked = hoursWorked;
    }

    // Getters and Setters
    public int getId() {
        return id;
    }

    public String getEmployeeName() {
        return employeeName;
    }

    public void setEmployeeName(String employeeName) {
        this.employeeName = employeeName;
    }

    public String getDate() {
        return date;
    }

    public void setDate(String date) {
        this.date = date;
    }

    public double getHoursWorked() {
        return hoursWorked;
    }

    public void setHoursWorked(double hoursWorked) {
        this.hoursWorked = hoursWorked;
    }

    @Override
    public String toString() {
        return "Timecard { " +
                "ID=" + id +
                ", Employee='" + employeeName + '\'' +
                ", Date='" + date + '\'' +
                ", Hours Worked=" + hoursWorked +
                " }";
    }
}

// TimecardService class to manage timecards
class TimecardService {
    private List<Timecard> timecards = new ArrayList<>();
    private int nextId = 1;

    public void addTimecard(String employeeName, String date, double hoursWorked) {
        Timecard timecard = new Timecard(nextId++, employeeName, date, hoursWorked);
        timecards.add(timecard);
        System.out.println("Timecard added: " + timecard);
    }

    public void editTimecard(int id, String employeeName, String date, double hoursWorked) {
        Timecard timecard = findTimecardById(id);
        if (timecard != null) {
            timecard.setEmployeeName(employeeName);
            timecard.setDate(date);
            timecard.setHoursWorked(hoursWorked);
            System.out.println("Timecard updated: " + timecard);
        } else {
            System.out.println("Timecard with ID " + id + " not found.");
        }
    }

    public void deleteTimecard(int id) {
        Timecard timecard = findTimecardById(id);
        if (timecard != null) {
            timecards.remove(timecard);
            System.out.println("Timecard deleted: " + timecard);
        } else {
            System.out.println("Timecard with ID " + id + " not found.");
        }
    }

    public void viewTimecards() {
        if (timecards.isEmpty()) {
            System.out.println("No timecards available.");
        } else {
            for (Timecard timecard : timecards) {
                System.out.println(timecard);
            }
        }
    }

    private Timecard findTimecardById(int id) {
        for (Timecard timecard : timecards) {
            if (timecard.getId() == id) {
                return timecard;
            }
        }
        return null;
    }
}

// Main class to interact with the system
public class MaintainTimecard {
    public static void main(String[] args) {
        TimecardService timecardService = new TimecardService();
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("\n--- Maintain Timecard Menu ---");
            System.out.println("1. Add Timecard");
            System.out.println("2. Edit Timecard");
            System.out.println("3. Delete Timecard");
            System.out.println("4. View Timecards");
            System.out.println("5. Exit");
            System.out.print("Choose an option: ");
            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            switch (choice) {
                case 1 -> {
                    System.out.print("Enter employee name: ");
                    String name = scanner.nextLine();
                    System.out.print("Enter date (YYYY-MM-DD): ");
                    String date = scanner.nextLine();
                    System.out.print("Enter hours worked: ");
                    double hours = scanner.nextDouble();
                    timecardService.addTimecard(name, date, hours);
                }
                case 2 -> {
                    System.out.print("Enter timecard ID to edit: ");
                    int id = scanner.nextInt();
                    scanner.nextLine(); // Consume newline
                    System.out.print("Enter new employee name: ");
                    String name = scanner.nextLine();
                    System.out.print("Enter new date (YYYY-MM-DD): ");
                    String date = scanner.nextLine();
                    System.out.print("Enter new hours worked: ");
                    double hours = scanner.nextDouble();
                    timecardService.editTimecard(id, name, date, hours);
                }
                case 3 -> {
                    System.out.print("Enter timecard ID to delete: ");
                    int id = scanner.nextInt();
                    timecardService.deleteTimecard(id);
                }
                case 4 -> timecardService.viewTimecards();
                case 5 -> {
                    System.out.println("Exiting Maintain Timecard System. Goodbye!");
                    scanner.close();
                    return;
                }
                default -> System.out.println("Invalid choice. Please try again.");
            }
        }
    }
}

```
