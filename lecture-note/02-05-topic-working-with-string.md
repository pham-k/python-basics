# Topic: Làm việc với string

## Mục tiêu

- [ ] Thực hiện được thao tác khai báo string
- [ ] Thực hiện được thao tác nối string
- [ ] Thực hiện được thao tác indexing và slicing
- [ ] Áp dụng được các function, method và operator trên string

## String

**string**: fundamental data type (không thể tách ra thành những thành phần con, phân biệt với **data structures**)

`type('Hello')  # class <str> hoac str` : để xác định "loại dữ liệu"

Đặc điểm:
  - Chứa ký tự: **character**
  - Có chiều dài (số ký tự): **length**
  - Ký tự được sắp xếp theo chuỗi: **sequence**
  - Không thể thay đổi: **immutable**

Khai báo string: 
  - Sử dụng `'` hoặc `"`
  - `'` và `"` được gọi la delimiter
  - string được khai báo theo cách này gọi là **string literal**
  - Sử dụng `\` để khai báo **multiline string**: output trên 1 dòng
  - Sử dụng `"""` để khai báo **multiline string**: format của output được bảo toàn
  - `\` được gọi là **escape character**
  - `"""` còn được sử dụng để mô tả một đoạn code, trong trường hợp này, nó được gọi là **docstring**

## Thao tác trên string

Về hình thức:
  - Sử dụng function
  - Sử dụng method
  - Sử dụng operator
  - Sử dụng `[ ]`

Về chức năng:
  - Đếm số ký tự
  - Lấy 1 phần string: indexing, slicing, ...
  - Tìm substring trong string: thường trả về vị trí hoặc boolean
  - Tách và nối string
  - Biến đổi string: chuyển thành chữ in hoa, chuyển thành chữ thường, xóa khoảng trắng, thay thế, ...
  
### Đếm số ký tự

Sử dụng function `len()`

```python
hello = 'Hello world'
len(hello)
```

### Nối string (concatenating)

Sử dụng operator `+`

```python
string1 = 'abc'
string2 = 'def'
string3 = string1 + string2
string3  # 'abcdef'
```

Sử dụng method `join()`:
  - Nhận argument là list các string
  - `['123', 'duong so 1', 'phuong 4', 'quan 5']` gọi là list. Chúng ta sẽ bàn chi tiết về list trong topic khác.

```
', ',join(['123', 'duong so 1', 'phuong 4', 'quan 5'])
```

### Tách string

Sử dụng method `split()`
  - Tách string theo (các) ký tự trong argument
  - Mặc định là khoảng trắng `' '`

```
'123, duong so 1, phuong 4, quan 5'.split(',')
```

### Lấy một ký tự (indexing)

Sử dụng `[x]`
  - x gọi là **index**
  - Index bắt đầu từ 0
  - Index có thể nhận số nguyên âm. Ký tự cuối cùng có index -1, ký tự kế cuối là -2,...

```python
msg = 'Python is awesome'
msg[1]  # 'y'
msg[-2]  # 'm'
```

Lỗi thường gặp khi sử dụng index:
  - `IndexError: string index out of range`

Do tính chất immutable của string nên chúng ta không thể thay đổi ký tự bằng indexing. Nếu vi phạm, Python sẽ báo lỗi `TypeError: 'str' object does not support item assignment`

```
txt = 'Python2'
txt[-1] = '3'  # TypeError
txt = 'Python3'  # OK
```

### Lấy nhiều ký tự (slicing)

Sử dụng `[x:y]`:
  - String được lấy ra gọi là **substring**
  - `[x:y]` gọi là slice:
  - `[x:y]` xuất ra substring bắt đầu từ index x và kết thúc trước index y (không bao gồm ký tự tại index y)
  - `[:y]` là cách viết tắt của `[0:y]`, lấy các ký tự từ đầu đến y
  - `[x:]` là cách viết tăt của `[x:len(msg)]`lấy ký tự từ x đến hết
  - `[:]` trả về string ban đầu
  - Có thể sử dụng index âm

```python
msg = 'Python is awesome'
msg[0:6]  # 'Python'
msg[-3;-1]  # 'om'
```

Lưu ý: Khi thực hiện slicing, nếu index không hợp lệ, Python sẽ trả về **empty string** "" và sẽ không báo lỗi IndexError.

### Thay đổi case

Sử dụng string method `lower()`, `upper()`:
  - Phân biệt cách gọi method `txt.lower()` với cách gọi function `len(txt)`
  - Có thể sử dụng trên string literal

```python
txt = 'Python'
txt.lower()
'Python'.upper()
```

### Xóa khoảng trắng bắt đầu và kết thúc

Sử dụng string method `lstrip()`, `rstrip()`, `strip()`:
  - `lstrip()` xóa khoảng trắng đầu string
  - `rstrip()` xóa khoảng trắng cuối string
  - `strip()` xóa khoảng trắng đầu và cuối string

```python
txt = '   Python is awesom   '
txt.strip()
```

### Xác định string có chứa một string cho trước hay không

Sử dụng string method `startswith()`, `endswith()`, `contains()`
  - Trả về giá trị boolean
  - case-sensitive: phân biệt ký tự hoa, ký tự thường

```python
txt = 'Python'
txt.startswith('P')  # True
txt.endswith('N')  # False
txt.contains('on')  # True
```

### Tìm vị trí của substring trong string

Sử dụng method `find()`
  - Nếu tìm thấy, trả về index bắt đầu của kết quả đầu tiên
  - Nếu không tìm thấy, trả về -1
  - case-sensitive

```python
txt = 'Python'
txt.find('P')  # 0
txt.find('th')  # 2
txt.find('py')  # -1
```

### Thay thế (các) ký tự

Sử dụng method `replace()`
  - Thay thế tất cả
  - Có thể nối nhiều method replace(). Lưu ý, các `replace()` này sẽ được thực hiện **lần lượt**
  - case-sensitive
  - String có tính chất immutable nên nếu muốn thay đổi biến cũ thì ta phải khai báo lại

```python
gene1 = 'ATTGC'
gene1.replace('A', 'T')  # 'TTTGC'
gene1  # 'ATTGC'
gene1 = gene1.replace('A', 'T')
gene1  # 'TTTGC'

gene2 = 'ATAT'
gene2.replace('A', 'T').replace('T', 'A')  # `AAAA`
```

### String và operator

Có thể áp dụng operator cho string:
  - `+` 2 vế phải cùng data type
  - `*` Khi sử dụng với string thì vế còn lại phải là số nguyên

```python
num = '1'
num + num  # '11'
num + 1  # TypeError
num * 4  # '1111'
num * '2'  # TypeError
```

### Đọc input từ người dùng

Sử dụng function input():
  - Thường dùng với console
  - Luôn trả về data type string

### Chuyển string thành số và ngược lại

Sử dụng function `int()`, `float()` để chuyển string thành số
  - `int()` chuyển string thành số nguyên
  - `float()` chuyển string thành số thực
  - Lỗi `ValueError` nếu string không hợp lệ
  - Thường dùng để giải quyết các lỗi TypeError

```python
int('4')  # 4
float('4')  # 4.0
int('4.0')  # ValueError
float('4.0')  # 4.0
```

Sử dụng function `str()` đề chuyển số thành string:
  - Không giới hạn

```python
str(2.5)
str(2 + 3.0)
```

### Function `print()` và string

```
no_cát = 2
no_dog = 3
```

Giả sử chúng ta có 2 biến như trên và ta muốn in ra màn hình string sau: 'I have 2 cats and 3 dogs'. Chúng ta có 3 cách để đạt được điều này:

```
print('I have ', no_cat, ' cats and ', no_dog, ' dogs')
```

```
print('I have ' + str(no_cat) + ' cats and ' + str(no_dog) + ' dogs')
```

Sử dụng formatter string literals, còn gọi là f-string
  - { } chứa biến
  - 

```
print(f'I have {no_cat} cats and {no_dog} dogs')
print('I have {} cats and {} dogs'.format(2, 3))
```
