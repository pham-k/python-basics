# Topic:

## Mục tiêu

- [ ] Thực hiện được thao tác khai báo biến
- [ ] Thực hiện được thao tác sử dụng biến
- [ ] Áp dụng được comment
- [ ] Đọc được thông báo lỗi

## Khái niệm

**python shell**: textual interface
interactive window
`>>>` là **prompt**
Nhập `1 + 1` và enter $\rightarrow$ **Read-Evaluate-Print Loop** (REPL)
Nhập `print('Hello world')`
  - print() là một **function**
  - function nhận input, gọi là **argument**
  - function thực hiện 1 chức năng nào đó và **return** output
  - function có thể có **side effect**

**Syntax highlighting**:  phần lớn text editor có hỗ trợ.
 Hạn chế của Interactive window: chỉ thực hiện mỗi lần 1 dòng và không thể chia sẻ $\rightarrow$ Cần lưu code (**script**) trong file .py, gọi là **script file**
 Ngoài script file, ta có thể sử dụng file notebook:
   - .ipynb
   - Chạy bằng jupyter notebook hoặc colab
   - Cho phép thực hiện từng đoạn code (gọi là cell)
   - Kết hợp với markdown
   - Có thể export ra các định dạng khác

## Chương trình python đầu tiên

```python
# Day la block comment
print('Hello world') # day la in-line comment
# Comment
# nhieu
# dong
```
Sử dụng comment:
  - [PEP8](https://pep8.org/#comments)
  - Toggle bằng Ctrl + /

Khai báo biến:
  - Sử dụng lại giá trị
  - Tạo context cho giá trị $\rightarrow$ đặt tên biến có ý nghĩa ([PEP8](https://pep8.org/#naming-conventions))

Biến sau khi đã khai báo sẽ được lưu trong `namespace`, có thể liệt kê bằng `dir()` 
```python
my_name = 'Khuong'
print('Hello', my_name)
dir()
```
Các loại lỗi
```python
print('Hello world)  # loi syntax
```
Thông báo lỗi (**Traceback**):
  - File ...: cho biết file
  - Line 1: cho biết dòng
  - `print('Hello world)`: dòng gây ra lỗi
  - `in <module>`: cho biết module
  - `^` cho biết vị trí trong dòng
  - `SyntaxError: EOL while scanning string literal` cho biết loại lỗi

Áp dụng tương tự để xác định lỗi cho trường hợp sau  
```python
print('Hello', My_name)  # loi runtime, case-sensitive
```
