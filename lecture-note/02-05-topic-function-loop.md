# Topic: Function và loop

## Mục tiêu

- [ ] Thực hiện khai báo và gọi function
- [ ] Áp dụng được for và while loop
- [ ] Trình bày được khái niệm scope 

## Function (hàm)

Function là first-class citizens, nghĩa là:
  - Là giá trị có thể gán cho biến
  - Có thể sử dụng như argument
  - Là return value từ function khác

2 loại function: built-in và user-defined
  - Có thể ghi đè lên built-in function (**không nên**)

Quá trình thực thi function:
  - **Define** function: Khai báo/ định nghĩa hàm
  - **Call** function, **arguments** are **passed**: Gọi hàm, sử dụng argument như input
  - Function is **executed** and function can have **side effect**: Thực thi
  - Function **returns** value: Trả về giá trị output

Khai báo function, gồm 2 phần
  - Function signature: tên function, arguments (nếu có)
  - Function body: code sẽ chạy khi function được gọi, có thể chứa **statement**, **expression**, comment, **function** khác, ... Nên sử dụng **docstring** để giải thích chức năng function.

[Đọc thêm về docstring](https://stackoverflow.com/questions/3898572/what-is-the-standard-python-docstring-format)

```python
def add(a, b):  # Function signature
    # Function body
    sum = a + b
    print(sum)  # Side effect
    return sum  # Output
    print("Nooo, this won't be run")
```

Function signature bao gồm:
  - Keyword `def`
  - Tên function là `add`
  - Các argumenta `(a, b)`
  - Dấu `:` báo hiệu kết thúc phần signature

Function body bao gồm:
  - Phải sử dụng **identation** (thường dùng 4 khoảng trắng)
  - Chứa code, comment
  - `return` statement, code sau `return` sẽ không được chạy

Gọi hàm

```python
def add(a, b):  # Function signature
    # Function body
    sum = a + b
    print(sum)  # Side effect, optional
    return sum  # Output, optional
    print("Nooo, this won't be run")

add(2, 3)
my_sum = add(5, 6)
```

Nếu gọi hàm trước khi khai báo: báo lỗi `NameError`

```python

add(2, 3)
my_sum = add(5, 6)

def add(a, b):  # Function signature
    # Function body
    sum = a + b
    print(sum)  # Side effect
    return sum  # Output
    print("Nooo, this won't be run")
```

## While loop

```python
n = 1
while n < 5:
    print(n)
    n = n + 1
```

Cấu trúc của while loop:
  - Keyword `while`
  - **test condition** `n < 5`: Điều kiện được xét trước mỗi vòng lặp . `<` thuộc nhóm **logical operators**, thường được sử dụng trong vòng lặp và cấu trúc điều kiện.
  - Dấu `:`
  - **Loop body**: Code được thực hiện trong mỗi vòng lặp. Nếu không có `n = n + 1` thì đây sẽ là **infinite loop**. Infinte loop có thể bị dừng bởi Ctrl + C trong terminal hoặc nút $\blacksquare$ (interrupt the kernel) trong notebook

## For loop

```python
for letter in 'python':
    print(letter)

for i in range(4):
    print(i)
```

Cấu trúc của for loop:
  - Keyword `for`
  - **Membership expression** `letter in 'python'`
  - Dấu `:`
  - **Loop body**: Code được thực hiện trong mỗi vòng lặp. Có thể sử dụng for loop trong for loop, gọi là **nested loop**, làm tăng thời gian tính toán.

Membership expression thường gặp:

```python
for i in range(4):
    print(i)

for i in range(5, 10):
    print(2 * i)
```

## Scope

Là tập hợp tên của của các đối tượng. Mỗi lần gọi tên đối tượng, Python sẽ tìm tên đối tượng lần lượt từng scope (**scope resolution**) theo quy tắc LEGB:
  - Local
  - Enclose
  - Global
  - Built-in

```python
x = 5  # This x is in global scope
print('Global scope: x =', x)

def func():
    x = 3  # This x is in local scope
    print('Lobal scope: x =', x)

func()
# function print is in built-in scope
```

```python
x = 5  # x is in global scope
def outerfunc():
    y = 3  # y is in enclosing scope
    def innerfunc():
        z = x + y  # z is in local scope of innerfunc()
        return z
    return innerfunc()

outerfunc()
```

[Đọc thêm: Global variable và Global constant](https://stackoverflow.com/questions/19158339/why-are-global-variables-evil)


