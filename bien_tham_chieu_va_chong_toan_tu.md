1. Biến tham chiếu
   - Biến tham chiếu là bí danh (tên khác) của một biến đã tồn tại.
   - Cú pháp:
     Kiểu &tên_biến = biến gốc;
   - Tham chiếu phải được khởi tạo ngay khi khai báo.
   - Khi thay đổi tham chiếu thì giá trị biến gốc cũng thay đổi.
   - Có thể dùng const nếu không muốn thay đổi giá trị thông qua tham chiếu.
     Ví dụ:
         int a = 10;
         int &b = a;
         b=20;
   
     => a = 20, b = 20.
2. Chồng toán tử
   - Chồng toán tử (Operator Overloading) là việc định nghĩa lại cách hoạt động của các toán tư có sẵn khi sử dụng với các dữ liệu do người lập trình định nghĩa như class, struct.
   - Cú pháp:
         Kiểu operator_ký_hiệu_toán_tử(các_tham_số){
         //xử lý
         }
    - Ví dụ: Cho phép cộng hai đối tượng phân số bằng:
          c = a + b;
      thay vì phải gọi một hàm riêng như cong(a,b).
    - Giới hạn của chồng toán tử
      + Không tạo được toán tử mới.
      + Không thay đổi được độ ưu tiên của toán tử.
      + Không thay đổi được số toán hạng.
      + Không thể chỉ dự vào kiểu trả hàng về để chồng toán tử.
      + Không chồng được các toán tử: ::, ., .*, ?:, sizeof.
      + Không thay đổi ý nghĩa của các toán tử đối với các kiểu dữ liệu có sẵn.
     
