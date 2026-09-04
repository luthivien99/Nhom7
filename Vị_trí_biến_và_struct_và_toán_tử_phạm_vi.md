4. Vị trí khai báo biến
5. 
4.1. Nội dung
Trong C truyền thống, biến thường được khai báo ở đầu một khối lệnh, trước các câu lệnh thực hiện.
```cpp
int main() {
    int a;
    int b;

    a = 5;
    b = 10;
}
```
Trong C++, biến có thể được khai báo ở bất kỳ vị trí thích hợp nào trong khối lệnh, miễn là khai báo trước khi sử dụng.
```cpp
int main() {
    int a = 5;

    cout << a << endl;

    int b = 10;
    cout << b;
}
```

4.2. Ý nghĩa
Việc này giúp:
   - Khai báo biến gần nơi sử dụng.
   - Code dễ đọc và dễ quản lý hơn.
   - Hạn chế phạm vi tồn tại của biến.
   - Giảm việc khai báo nhiều biến không cần thiết ở đầu chương trình.

 5. Kiểu cấu trúc -struct

struct hay kiểu cấu trúc cho phép chúng ta gom nhiều dữ liệu có liên quan với nhau thành một kiểu dữ liệu mới.
Ví dụ cần lưu thông tin sinh viên gồm: Tên, Tuổi, Điểm
Ta có:
```cpp
#include <iostream>
#include <string>
using namespace std;

// Khai báo cấu trúc SinhVien
struct SinhVien {
    string ten;
    int tuoi;
    float diem;
};

int main() {
    // Khai báo biến sinh viên
    SinhVien sv;

    // Gán dữ liệu
    sv.ten = "Nguyen Van An";
    sv.tuoi = 20;
    sv.diem = 8.5;

    // Xuất thông tin
    cout << "Ten: " << sv.ten << endl;
    cout << "Tuoi: " << sv.tuoi << endl;
    cout << "Diem: " << sv.diem << endl;

    return 0;
}
```

 6. Toán tử phạm vi

:: được gọi là toán tử phạm vi hay scope resolution operator.
Nó được dùng để xác định một tên thuộc phạm vi nào.
Ví dụ về biến toàn cục và biến cục bộ:
```cpp
#include <iostream>
using namespace std;

int x = 10;       // biến toàn cục

int main() {
    int x = 20;   // biến cục bộ

    cout << x << endl;
    cout << ::x << endl;

    return 0;
}
```
