# Topic: Setup môi trường làm việc

## Mục tiêu

  - [ ] Thực hiện được thao tác cài package
  - [ ] Thực hiện được thao tác import package

## Giới thiệu

Workflow 1: Sử dụng venv + git

  - Tạo môi trường ảo
  - Activate môi trường ảo
  - Cài đặt package
  - Tạo requirements.txt
  - Tạo folder structure
  - git init
  - Tạo .gitignore
  - git add
  - git commit

Workflow 2: Sử dụng venv + docker

Workflow 3: Sử dụng anaconda $\rightarrow$ **recommended**

  - Tạo Environment
  - Cài đặt package
  - Tạo folder structure


## Cài đặt package

Sử dụng pip:
  - Cài: `pip install package_name`
  - Xóa:`pip uninstall package_name`
  - Liệt kê: `pip list` hoặc `pip list | grep package_name`
  - `pip help`

Sử dụng Anaconda

## Module

Modular programming: simplicity, reusability, maintainability, scoping (separate namespace)

Module search path: 
  - Thư mục hiện tại
  - Đường dẫn trong environment variable PYTHONPATH
  - Đường dẫn được cấu hình lúc cài đặt

Liệt kê module search path: `sys.path`

2 cách để đảm bảo import được module:
  - Chuyển module đến thư mục có trong `sys.path`
  - Thêm đường dẫn của module vào sys.path: `sys.path.append('path/to/module')`
  
## Package

Package bao gồm nhiều module

## Import

Import module
```python
import module1, module2
import long_module_name as short_name
from module_name import *
from module_name import something, something_else
```

Ví dụ trong module mydog có function bark, module mycat có function meow

```python
import mydog as dog
bark() # Bao loi
dog.bark() # OK
```

```python
from mycat import meow
meow() # OK
```

Import module từ  package

```python
from package import module
from package import module as mod
from package.module import something

```

## Folder structure

Gợi ý:
  - data:
    - external
    - raw
    - interim
    - processed 
  - src
    - data
    - visualization
    - model
  - reference
  - notebook
    - exploratory
    - report
