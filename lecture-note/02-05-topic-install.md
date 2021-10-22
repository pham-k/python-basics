# Topic: Cài đặt

## Mục tiêu

 - [ ] Thực hiện cài đặt python

## Giới thiệu

2 version chính thường dùng:
  - python 2.7 
  - python >= 3.6 (hiện tại 3.10) $\rightarrow$ **Recommended**

1 hệ thống có thể có nhiều version $\rightarrow$ giải quyết vấn đề dependency bằng **package manager** + **môi trường ảo**

Package manager và môi trường ảo thường dùng

  - pip + venv (+docker)
  - conda $\rightarrow$ **Recommended**

IDE/ text editor có thể dùng

  - IDLE (cài trực tiếp)
  - Spyder (cài trực tiếp hoặc thông qua Anaconda)
  - Jupyter notebook (cài trực tiếp hoặc thông qua Anaconda) $\rightarrow$ **Recommended**
  - PyCharm (cài trực tiếp hoặc thông qua Anaconda)
  - VSCode + extension
  - [Google Colab](https://colab.research.google.com/) $\rightarrow$ **Recommended**

## Cài đặt:

Có 2 cách thường dùng

  - Cài trực tiếp: Sử dụng pip, venv để quản lý dependencies
  - Cài gián tiếp qua conda: Sử dụng conda để quản lý dependencies $\rightarrow$ **Recommended**

### Cài trực tiếp

Window
  - B1: [Download](https://www.python.org/downloads/)
  - B2: Chạy installer
    - Check ô Add Python 3.x to PATH
  - B3: Chạy IDLE
    - Mở start menu, tìm folder Python 3.x
    - Mở folder và chọn IDLE
  - (B4: Cài pip)
    -  [Hướng dẫn](https://www.geeksforgeeks.org/how-to-install-pip-on-windows/)

MacOS
  - B1: [Download](https://www.python.org/downloads/)
  - B2: Chạy installer
  - B3: Mở IDLE:
    - Mở finder, tìm Applications
    - Tìm Python 3.x và double click
    - Double click IDLE

Linux:

  - Thường có sẵn Python 2 và Python 3
  - Check version bằng `python --version` hoặc `python3 --version`
  - Sử dụng package manager để cài

### Cài gián tiếp thông qua conda

  - B1: Cài [Anaconda](https://www.anaconda.com/products/individual)
  - B2: Tạo environment và chọn environment vừa tạo
  - B3: Cài Python và jupyter notebook
 ![enter image description here](https://www.anaconda.com/imager/assetsdo/Products/Product-Screenshots/5736/navigator-screenshot_680db6b6f11f9cc710dd7defae241cd3.png)
  - B4: Mở jupyter notebook
