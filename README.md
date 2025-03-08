# Linux2025-2
Lưu ý: 
- file (.c) nẳm trong `src` ;
- file (.o) nẳm trong `obj` ;
- file (.so) nẳm trong `lib/shared` ;
- file (.a) nẳm trong `lib/static` ;
- khi tạo file `obj` thì lấy file `src` ;
- khi tạo file `lib` thì lấy file `obj` ;
- Có cả `obj` và `lib` thì tạo đc file `bin` ;
 
```
# cài một số service để có thể chạy đc lệnh.
sudo apt install net-tools -y
sudo apt install openssh-server -y
sudo apt install make -y
sudo apt install gcc -y
```
## 1. Linking
Mặc định:

![image](https://github.com/user-attachments/assets/c378845e-ae1b-4a11-b7fc-76c8c62cf15c)

(Lưu ý: Trường`Dependences` trong makefile `obj` phải đc đặt trước `lib`).

![image](https://github.com/user-attachments/assets/cdfe77bb-b099-460f-a7b0-f144f73b0336)

Có 2 kiểu `make all`:

### Về Static: #library static (.a) and obj static (.o) >> make all2 là `bin`/use-static-library.
- Tạo Static obj → Tạo Static Library → all: obj-Static lib-Static
  
![image](https://github.com/user-attachments/assets/c2b59728-a07a-408d-81ba-4515e0e69384)
- Tạo một `clean`để xóa file nằm trong:: `rm -rf obj lib bin`
### Về Shared: # library shared (.so) and obj shard (.o) >> make all là `bin`/use-shared-library.
- Tạo Shared obj → Tạo Shared Library → all: obj-Shared lib-Shared

![image](https://github.com/user-attachments/assets/2bfc7c0b-39d3-4c83-91f2-f7f2811743ad)
- Tạo một `clean` để xóa file nằm trong: `rm -rf obj lib bin`
