1. Tham số giá trị mặc định (Default Arguments)
1.1. Khái niệm
Tham số giá trị mặc định (Default Arguments) là tham số được gán sẵn một giá trị khi khai báo hàm. Nếu khi gọi hàm người lập trình không truyền giá trị cho tham số đó thì chương trình sẽ tự động sử dụng giá trị mặc định.
Việc sử dụng tham số mặc định giúp giảm số lượng hàm cần xây dựng, tăng tính linh hoạt và làm cho chương trình ngắn gọn, dễ sử dụng hơn.
Cú pháp
kiểu_trả_về tên_hàm(kiểu tham_số = giá_trị_mặc_định);
Ví dụ:
void Display(string name = "Guest");
Nếu gọi:
Display();
thì chương trình sẽ hiểu là:
Display("Guest");
1.2. Quy tắc sử dụng
Giá trị mặc định chỉ được khai báo trong prototype (khai báo hàm).
Các tham số có giá trị mặc định phải được đặt ở cuối danh sách tham số.
Khi gọi hàm chỉ được phép bỏ bớt các tham số từ phải sang trái.
Ví dụ:
void Sum(int a, int b = 5, int c = 10);
Sum(2,3,4);   // Đúng
Sum(2,3);     // Đúng
Sum(2);       // Đúng
// Sum(2,,4); // Sai
1.3. Lưu ý
Không khai báo giá trị mặc định nhiều lần cho cùng một tham số.
Sau một tham số có giá trị mặc định thì tất cả các tham số phía sau cũng phải có giá trị mặc định.
Giá trị mặc định chỉ được sử dụng khi đối số tương ứng không được truyền vào.
Nên dùng tham số mặc định khi các hàm chỉ khác nhau ở một vài giá trị mặc định của tham số.
1.4. Ví dụ minh họa
#include <iostream>
using namespace std;
void Student(string name = "Unknown", int age = 18)
{
    cout << "Name: " << name << endl;
    cout << "Age : " << age << endl;
}
int main()
{
    Student();
    Student("Trang");
    Student("An",20);
    return 0;
}
Kết quả
Name: Unknown
Age : 18
Name: Trang
Age : 18
Name: An
Age : 20
2. Chồng hàm (Function Overloading)
2.1. Khái niệm
Chồng hàm (Function Overloading) là cơ chế cho phép định nghĩa nhiều hàm có cùng tên nhưng khác nhau về danh sách tham số (số lượng tham số, kiểu dữ liệu hoặc thứ tự tham số).
Khi gọi hàm, trình biên dịch sẽ tự động lựa chọn phiên bản phù hợp dựa trên các đối số được truyền vào.
Chồng hàm giúp tăng khả năng tái sử dụng mã, làm chương trình dễ đọc và tránh phải đặt nhiều tên hàm khác nhau cho các chức năng tương tự.
2.2. Điều kiện chồng hàm
Các hàm được phép chồng nếu khác nhau về:
Số lượng tham số.
Kiểu dữ liệu của tham số.
Thứ tự các kiểu dữ liệu của tham số.
Ví dụ:
void Print(int x);
void Print(double x);
void Print(int x, int y);
2.3. Lưu ý và giới hạn
Khi sử dụng chồng hàm cần lưu ý:
Hai hàm phải có danh sách tham số khác nhau.
Không được chồng hàm chỉ khác kiểu trả về.
int Sum(int a, int b);
float Sum(int a, int b);   // Sai
typedef chỉ tạo bí danh cho kiểu dữ liệu, không tạo kiểu mới nên không dùng để phân biệt chồng hàm.
Đối với chồng hàm, mảng (int a[]) và con trỏ (int *a) được xem là tương đương.
Có thể dùng const với con trỏ hoặc tham chiếu để phân biệt các phiên bản hàm.
2.4. Ví dụ minh họa
Ví dụ 1: Khác số lượng tham số
#include <iostream>
using namespace std;
int Sum(int a, int b)
{
    return a + b;
}
int Sum(int a, int b, int c)
{
    return a + b + c;
}
int main()
{
    cout << Sum(3,4) << endl;
    cout << Sum(3,4,5);
}
Kết quả
7
12
Ví dụ 2: Khác kiểu dữ liệu
#include <iostream>
using namespace std;
void Print(int x)
{
    cout << "Integer: " << x << endl;
}
void Print(double x)
{
    cout << "Double: " << x << endl;
}
int main()
{
    Print(10);
    Print(3.14);
}
Kết quả
Integer: 10
Double: 3.14
