# Topic: Làm việc với số

## Mục tiêu

## Integer

```python
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

## Operators

Phép tính số học:
  - `+`, `-`,`*`,`/`,`**`, `%`, `//`
  - `x % y` trả về kết quả là r = x - (y * (x // y))
  - `//` làm tròn **xuống**, cẩn thận với số âm
  - Nếu thực hiện trên float, kết quả sẽ là float
  - Phép chia luôn ra float

Lỗi thường gặp:
  - `ZeroDivisionError: division by zero`

## FLoating-point representation error

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
