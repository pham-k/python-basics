# Topic: Làm việc với số

## Mục tiêu

## Integer

```python
# Sử dụng function type() để xác định data type
type(1)
type(1.0) # khong phai integer
```

Khai báo:
  - `1` (integer literal)
  - `int(1)`
  - `1_000_000`



## FLoat
 
```python
type(1.0) # khong phai integer
```

Khai báo
  - `1.0` (floating-point literal)
  - `1_000_000.0`
  - `1e6`, `2e-10` (e-notation)
  - `float(1)`
  - Giới hạn trên là `inf` (vd: `2e400`)
  - Giới hạn dưới là `-inf` (vd: `-2e400`)

## Complex number

Khai báo:
  - `1 + 2i`, `2 + 3j`
  - `i`, `j`: phần ảo

Truy xuất phần thực bằng `(1 + 2i).real`, phần ảo bằng `(1 + 2i).imag`

## Operators

Phép tính số học:
  - `+`, `-`,`*`,`/`,`**`, `%`, `//`
  - `x % y` trả về kết quả là r = x - (y * (x // y))
  - `//` làm tròn **xuống**, cẩn thận với số âm; không thực hiện được trên số phức
  - Nếu thực hiện trên float, kết quả sẽ là float
  - Phép chia luôn ra float


Lỗi thường gặp:
  - `ZeroDivisionError: division by zero`

## FLoating-point representation error

## Format number

Syntax:
  - Sử dụng f-string
  - `:`: báo hiệu phía sau nó là quy tắc format
  - `.2f`: làm tròn đến 2 chữ số thập phân
  - `,`: Thêm dấu `,` ngăn cách phần nghìn
  - `.2%`: Biểu diễn dạng phần trăm, 2 chữ số thập phân 
```
n = 1234.5678
f'n is {n:.2f}'
ratio = 0.25
f'ratio is {ratio:.2%}'
```

[Đọc thêm](https://docs.python.org/3/library/string.html#format-string-syntax)

## Thao tác trên số

Về hình thức:
  - Sử dụng operator
  - Sử dụng function
  - Sử dụng method

### Làm tròn

Sử dụng function round()
  - Làm tròn đến số nguyên gần nhất
  - Đối với trường hợp ties (2.5, 3.5, 1.2345): rounding ties to even, nghĩa là làm tròn theo chữ số bên trái số 5, nếu chẵn thì làm tròn xuống, lẻ thì làm tròn lên (**IEEE 754**)
  - `round(3.1415, 2)` làm tròn đến 2 chữ số thập phân
  - round() có thể sai do FLoating-point representation error, vd `round(2.675, 2)`

Lỗi thường gặp
  - `round(3.1415, 2.5)`: `TypeError: 'float' object cannot be interpreted as an integer`

### Tính trị tuyệt đối

Sử dụng function `abs()`

### Tính lũy thừa

Sử dụng function pow()
  - `pow(x, y)`: tương đương x ** y
  - `pow(x, y, z)`: tương đương (x ** y) % z

### Kiểm tra số nguyên

Sử dụng method `is_integer()`
  - Trả về boolean
