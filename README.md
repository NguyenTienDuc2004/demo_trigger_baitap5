# demo_trigger_baitap5
# bài tập 5 k225480106081 Nguyễn Tiến Đức môn hệ quản trị cơ sở dữ liệu
# BÀI TẬP VỀ NHÀ 05, Môn Hệ quản trị csdl.

SUBJECT: Trigger on mssql

# A. Trình bày lại đầu bài của đồ án PT&TKHT:
1. Mô tả bài toán của đồ án PT&TKHT, 
   đưa ra yêu cầu của bài toán đó
2. Cơ sở dữ liệu của Đồ án PT&TKHT :
   Có database với các bảng dữ liệu cần thiết (3nf),
   Các bảng này đã có PK, FK, CK cần thiết
 
# B. Nội dung Bài tập 05:
1. Dựa trên cơ sở là csdl của Đồ án
2. Tìm cách bổ xung thêm 1 (hoặc vài) trường phi chuẩn
   (là trường tính toán đc, nhưng thêm vào thì ok hơn,
    ok hơn theo 1 logic nào đó, vd ok hơn về speed)
   => Nêu rõ logic này!
3. Viết trigger cho 1 bảng nào đó, 
   mà có sử dụng trường phi chuẩn này,
   nhằm đạt được 1 vài mục tiêu nào đó.
   => Nêu rõ các mục tiêu 
4. Nhập dữ liệu có kiểm soát, 
   nhằm để test sự hiệu quả của việc trigger auto run.
5. Kết luận về Trigger đã giúp gì cho đồ án của em.

# HƯỚNG DẪN CÁCH LÀM:

Hướng dẫn làm phần A: 
 - Chỉ cần nêu ra y/c của đồ án.
 - Không cần chụp quá trình làm ra db, tables.
 - Chỉ cần đưa ra db gồm các bảng nào,
   mỗi bảng có các trường nào, kiểu dữ liệu nào,
   và pk, fk, ck của các bảng.

Hướng dẫn làm phần B:
1. Sv tạo repo mới trên github, cho phép truy cập public.
2. Tạo file Readme.md, đầu file để thông tin cá nhân sv.
3. Tiếp theo đưa phần A vào file Reame.md .
3. Các thao tác làm trên csdl bằng phần mềm ssms.
4. Chụp ảnh màn hình quá trình làm.
5. Paste ngay vào Readme.md, 
   rồi gõ mô tả ảnh này làm gì, nhập gì, hay đạt được điều gì...
6. Có thể thêm những nhận xét hoặc kết luận
   cho việc bản thân đã hiểu rõ thêm về 1 vấn đề gì đó.
7. Lặp lại các step 4 5 6 cho đến khi hoàn thành yêu cầu của phần B.
8. Xuất các file sql chứa cấu trúc và data, up lên cùng repo.
9. Link đến repo cần mở được trực tiếp nội dung, 
   Paste link này vào file excel online ghim trên nhóm.
   Thầy sẽ dùng tool để check các link này.

# DEADLINE: 23H59:59 NGÀY 23/04/2025

#----------------------------------------------------------------------
 A. Trình bày lại đầu bài của đồ án PT&TKHT:
1. Mô tả bài toán của đồ án PT&TKHT, 
   đưa ra yêu cầu của bài toán đó
2. Cơ sở dữ liệu của Đồ án PT&TKHT :
   Có database với các bảng dữ liệu cần thiết (3nf),
   Các bảng này đã có PK, FK, CK cần thiết

bài làm:
1: Mục tiêu hệ thống
Xây dựng một hệ thống quản lý kho dành cho siêu thị, cho phép theo dõi nhập – xuất hàng hóa, quản lý tồn kho, quản lý sản phẩm, nhà cung cấp và nhân viên thực hiện giao dịch. Hệ thống cần đảm bảo cập nhật số lượng tồn kho chính xác, tự động sau mỗi giao dịch.
 Quản lý sản phẩm:
Lưu thông tin sản phẩm: tên, đơn vị tính, giá nhập, giá bán, loại sản phẩm.

Theo dõi số lượng tồn kho.

 Quản lý loại sản phẩm:
Phân loại hàng hóa (ví dụ: thực phẩm, đồ gia dụng, nước uống…).

 Quản lý nhà cung cấp:
Lưu thông tin tên, địa chỉ, số điện thoại của nhà cung cấp hàng hóa.

 Quản lý nhân viên:
Nhân viên chịu trách nhiệm thực hiện các nghiệp vụ nhập – xuất kho.

 Nhập kho:
Lập phiếu nhập hàng khi hàng về từ nhà cung cấp.

Ghi nhận chi tiết sản phẩm và số lượng nhập.

Tự động cộng số lượng vào tồn kho.

 Xuất kho:
Lập phiếu xuất hàng khi xuất bán cho khách hoặc chuyển đi nơi khác.

Ghi nhận chi tiết sản phẩm và số lượng xuất.

Tự động trừ số lượng tồn kho.

Không cho phép xuất quá số lượng hiện có trong kho.

2. Cơ sở dữ liệu của Đồ án PT&TKHT :
   Có database với các bảng dữ liệu cần thiết (3nf),
   Các bảng này đã có PK, FK, CK cần thiết

bảng mã nhân viên
![image](https://github.com/user-attachments/assets/951ec7ed-9a3b-4418-bc93-bc44326efab1)

bảng nhà cung cấp 
![image](https://github.com/user-attachments/assets/3f44bbd8-072b-4702-b0c6-86d6ad1192b0)

bảng sản phẩm 
![image](https://github.com/user-attachments/assets/74d7f675-1dc1-4c5f-9891-376643aecbe7)

bảng loại sản phẩm 
![image](https://github.com/user-attachments/assets/5806886b-e4b6-40f2-849b-36229732f522)

bảng phiếu nhập 
![image](https://github.com/user-attachments/assets/0843b753-6912-4c7c-9ef9-6979de707be7)

bảng phiếu xuất 
![image](https://github.com/user-attachments/assets/9f0e068e-256c-4168-8ebb-0248c93959e6)

bảng chi tiết phiếu nhập 
![image](https://github.com/user-attachments/assets/3ab42107-cff7-49c4-88e1-474a116ffc36)

bảng chi tiết phiếu xuất 
![image](https://github.com/user-attachments/assets/3fc19a39-fd86-42d9-a7d1-3f90d399c366)

bảng diagram
![image](https://github.com/user-attachments/assets/c639b266-322e-4fd6-b215-833957082189)

#-----------------------------------------------------------------------------------------
 B. Nội dung Bài tập 05:
1. Dựa trên cơ sở là csdl của Đồ án
2. Tìm cách bổ xung thêm 1 (hoặc vài) trường phi chuẩn
   (là trường tính toán đc, nhưng thêm vào thì ok hơn,
    ok hơn theo 1 logic nào đó, vd ok hơn về speed)
   => Nêu rõ logic này!
3. Viết trigger cho 1 bảng nào đó, 
   mà có sử dụng trường phi chuẩn này,
   nhằm đạt được 1 vài mục tiêu nào đó.
   => Nêu rõ các mục tiêu 
4. Nhập dữ liệu có kiểm soát, 
   nhằm để test sự hiệu quả của việc trigger auto run.
5. Kết luận về Trigger đã giúp gì cho đồ án của em.


bài làm : 

bổ sung thêm trường phi chuẩn 
![image](https://github.com/user-attachments/assets/cb2a66ee-2b09-43c9-a2fb-a6719c1b9a35)

bổ sung thêm số lượng tồn
![image](https://github.com/user-attachments/assets/e7bed541-a9bd-4ff6-bce3-36095fbe4dae)

viết trigger cho bảng 
![image](https://github.com/user-attachments/assets/a8c89075-bb12-4c1d-b23f-410839d9736a)

4 nhập sữ liệu 
![image](https://github.com/user-attachments/assets/58fda6ae-ecc3-4c17-990f-480fe5131047)

kiểm tra bảng log hệ thống 
![image](https://github.com/user-attachments/assets/fbb6e8b8-b79b-41e9-97b0-297b67fa9505)

kết quả đạt được 
![image](https://github.com/user-attachments/assets/0ca0f654-a80a-4906-89c4-a0cd0710602d)
![image](https://github.com/user-attachments/assets/148e7bdd-a3d9-45b5-86b9-dfd2f939c16b)

5 kết luận 
Tự động cập nhật tồn kho khi xuất hàng, không cần thao tác thủ công.
Ghi lại lịch sử xuất kho bằng JSON, thuận tiện cho việc truy vết và báo cáo.
Sử dụng trường phi chuẩn (JSON) giúp dễ dàng tích hợp với các hệ thống khác hoặc giao diện người dùng.

xuất file
![image](https://github.com/user-attachments/assets/6f63ed5c-89bc-4133-92f6-defe39a1c6c4)
![image](https://github.com/user-attachments/assets/4b1e1c37-4e5f-4a02-82c9-b5fea1f80f3f)



















 
