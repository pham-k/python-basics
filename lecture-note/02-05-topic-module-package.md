# Topic: Module and package

## Module

Modular programming: simplicity, reusability, maintainability, scoping (separate namespace)

3 loai module:
  - Module viết bằng python
  - Module viết bằng C (re)
  - Built-in module: có sẵn trong interpreter

Ví dụ: Import module sys `import sys`

Module search path: 
  - Thư mục hiện tại
  - Đường dẫn trong environment variable PYTHONPATH
  - Đường dẫn được cấu hình lúc cài đặt

Liệt kê module search path: `sys.path`

2 cách để đảm bảo import được module:
  - Chuyển module đến thư mục có trong `sys.path`
  - Thêm đường dẫn của module vào sys.path: `sys.path.append('path/to/module')`

`dir()`: Liệt kê đối tượng trong namespace

Module có thể được chạy như script: `python module_name.py`

## Tạo module

## Import module

reload module

## Package

## Tạo package

## Import package
  
