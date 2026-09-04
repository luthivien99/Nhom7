1. Cấp phát và giải phóng bộ nhớ bằng new, delete
1.1. Khái niệm
- Trong C++, new và delete là các toán tử dùng để cấp phát và giải phóng bộ nhớ động.
 + new: cấp phát bộ nhớ trong vùng nhớ động (heap) khi chương trình đang chạy.
 + delete: giải phóng vùng nhớ đã được cấp phát bằng new.
 + So với các hàm cấp phát bộ nhớ của C như malloc(), calloc(), free(), cách sử dụng new, delete trong C++ linh hoạt và phù hợp với kiểu dữ liệu, đối tượng hơn.
1.2. Toán tử new
Cú pháp
- Theo slide, new có các dạng:
new Ten_kieu;
new (Ten_kieu);
new Ten_kieu Gia_tri_khoi_tao;
new (Ten_kieu) Gia_tri_khoi_tao;
- Thông thường có thể sử dụng:
Tên_con_trỏ = new Kiểu_dữ_liệu;
- Hoặc khởi tạo ngay giá trị:
Tên_con_trỏ = new Kiểu_dữ_liệu(giá_trị);
=> Nếu việc cấp phát bộ nhớ không thành công, new sẽ trả về giá trị NULL trong cách trình bày của slide.
Ví dụ 1: Cấp phát một biến động
#include <iostream>
using namespace std;
int main() {
    int *p;
    p = new int;
    *p = 10;
    cout << "Gia tri = " << *p;
    delete p;
    return 0;
}
Ví dụ 2: Cấp phát và khởi tạo giá trị
int *p = new int(20);
cout << *p;
delete p;
Kết quả: 20
1.3. Cấp phát mảng động bằng new
- C++ cho phép sử dụng new để cấp phát mảng có kích thước được xác định trong thời gian chạy.
- Cú pháp: Tên_con_trỏ = new Kiểu_dữ_liệu[kích_thước];
- Ví dụ:
#include <iostream>
using namespace std;
int main() {
    int n;
    cout << "Nhap n: ";
    cin >> n;
    int *a = new int[n];
    for (int i = 0; i < n; i++) {
        cout << "a[" << i << "] = ";
        cin >> a[i];
    }
    cout << "Mang vua nhap: ";
    for (int i = 0; i < n; i++) {
        cout << a[i] << " ";
    }
    delete[] a;
    return 0;

}
2. Toán tử delete
2.1. Khái niệm
- delete dùng để giải phóng vùng nhớ động đã được cấp phát bằng new.
- Đối với một biến:
int *p = new int;
delete p;
- Đối với một mảng:
int *a = new int[10];
delete[] a;
3. Hàm inline
3.1. Khái niệm
- Hàm inline là một mở rộng của C++ nhằm giảm chi phí khi gọi các hàm nhỏ.
- Khi trình biên dịch thực hiện inline, nó có thể chèn trực tiếp đoạn lệnh của hàm vào vị trí gọi hàm, thay vì thực hiện quá trình gọi hàm thông thường.
- Theo slide:
* Hàm inline phải được định nghĩa trước khi sử dụng.
* Trình biên dịch có thể chèn trực tiếp đoạn chương trình vào chỗ hàm được gọi.
* Hàm đệ quy không được là hàm inline.
3.2. Cú pháp
inline Kiểu_dữ_liệu Tên_hàm(các_tham_số)
{
    // thân hàm

}
- Ví dụ:
#include <iostream>
using namespace std;

inline int BinhPhuong(int x)
{
    return x * x;
}
int main()
{
    cout << BinhPhuong(5);

    return 0;
}
