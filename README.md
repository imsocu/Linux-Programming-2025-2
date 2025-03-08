# Linux2025-2
Lưu ý: 
- file (.c) nẳm trong `src` ;
- file (.o) nẳm trong `obj` ;
- file (.so) nẳm trong `lib/shared` ;
- file (.a) nẳm trong `lib/static` ;
- khi tạo file `obj` thì lấy file `src` ;
- khi tạo file `lib` thì lấy file `obj` ;
- Có cả `obj` và `lib` thì tạo đc file `bin` ;
 

## 1. Linking
Mặc định:

 ![image](https://github.com/user-attachments/assets/c378845e-ae1b-4a11-b7fc-76c8c62cf15c)
Có 2 kiểu `make`:

### Về Static: #library static (.a) and obj static (.o) >> make all2 (luu y obj phai dc tao truoc lib neu ko se bao loi)
- Tạo Static obj → Tạo Static Library → all: obj-Static lib-Static
- Tạo một `clean`(để xóa file): `rm -rf obj lib bin`
![image](https://github.com/user-attachments/assets/c2b59728-a07a-408d-81ba-4515e0e69384)

### Về Shared: # library shared (.so) and obj shard (.0) >> make all
- Tạo Shared obj → Tạo Shared Library → all: obj-Shared lib-Shared
- Tạo một `clean`: `rm -rf obj lib bin`
  ![image](https://github.com/user-attachments/assets/2bfc7c0b-39d3-4c83-91f2-f7f2811743ad)

