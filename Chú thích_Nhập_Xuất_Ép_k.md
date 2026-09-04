1. Chú thích
- Chú thích không được coi là mà nguồn và sẽ được loại bỏ bởi trình biên dịch khi biên dịch mã nguồn . 
```cpp
Ví dụ:
// Đây là chú thích một dòng
int a = 10; // Khai báo biến a
```cpp

Ví dụ 2:
/*
  int a = 10; 
   Đây là chú thích
   gồm nhiều dòng
*/



2. Nhập và xuất
- cin là đối tượng giúp nhập dữ liệu từ bàn phím thay vì khởi tạo thủ công, cin nằm trong thư viện "iostream" và namespace std.
- cin đi kèm với toán tử nhập >>
Ví dụ:
```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main(){
    int n, a, b, c;
    cout << "Nhap gia tri cho n : ";
    cin >> n;
    cout << "Gia tri n vua nhap la : " << n << endl;
    cout << "Nhap gia tri cho a, b, c : ";
    cin >> a >> b >> c;
    cout << "Gia tri a, b, c : " << a << " " << b << " " << c << endl;
    return 0;
}


- cout là một đối tượng giúp thể hiện thị nội dung như : số nguyên, số thực, giá trị của biến, đoạn text ra màn hình. 
- Để sử dụng đối tượng này cần khai báo thư viện "iostream" và sử dụng namespace std
Ví dụ:
```cpp  
#include <iostream>
using namespace std;

int main(){
    int n = 282828;
    cout << "Gia tri cua bien n : " << n << endl;
    
    return 0;
}
```cpp

3. Ép kiểu
- Toán tử ép kiểu trong C++ là 1 toán tử đặc biệt mà làm một kiểu dữ liệu này biến đổi thành kiểu dữ liệu khác.
  Toán tử ép kiểu là một toán tử 1 ngôi và có cùng độ ưu tiên như bất kỳ toán tử một ngôi nào khác trong C++.
  Ví dụ:
```cpp
  #include <iostream>
  using namespace std;
   
  int main(){
     float a = 5.5;
     float b = 9.02;
     int c ;
   
     c = (int) a;
     cout << "Gia tri cua (int)a la: " << c << endl ;
     
     c = (int) b;
     cout << "Gia tri cua (int)b la: " << c << endl ;
     
     return 0;
  }
```cpp
