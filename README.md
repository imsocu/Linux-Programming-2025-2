# Linux2025-2

  ## 1. Linking.
  
<details>
 <summary>Click vào đây để xem thêm.</summary>
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
  
</details>

## 2. Linux File System.

<details>
 <summary>Click vào đây để xem thêm.</summary>
  
### 2.1 Introduction

- Tất cả mọi thứ trong Linux đều là file.
  
![image](https://github.com/user-attachments/assets/a4943352-cbd9-4b3b-9650-a18c81ed83cc)

### 2.2 Operations on File

- Các System Call: gọi hàm  open(), read(), write(), close() để chuyển đổi từ user mode > kernel space

![image](https://github.com/user-attachments/assets/e162ba63-632a-4e9f-b36d-b108b3e76b9b)


![image](https://github.com/user-attachments/assets/fc3545bc-d42a-45f3-9849-cf40f082a74d)



### 2.3 File Management.

### 2.4 File Locking.

</details>
  
## 3. Linux Process.

<details>
 <summary>Click vào đây để xem thêm.</summary>
  
### 3.1 Program  & Process.

![image](https://github.com/user-attachments/assets/684d4954-2703-4d59-b638-c675806f3860)

#liệt kê các process đang chạy. `# ps -aux`

![image](https://github.com/user-attachments/assets/57287ef8-bd6d-42e9-99de-fa2d0b670a93)

### 3.2 Command-line Argument.

- `argc` (Argument Count): Số lượng tham số truyền vào chương trình `%d`, bao gồm cả tên chương trình.
- `argv` (Argument Vector): Mảng chứa các chuỗi (string) `%s` đại diện cho từng tham số truyền vào.

### 3.3 Memory Layout.

![image](https://github.com/user-attachments/assets/6600df5a-83f6-4dbf-a86c-b46d621466b0)

- Stack
- Heap
- Uninitializad data
- Initialized data
- Text

- Công cụ debug : `Valgrind` để check lỗi.

</details>

### 3.4. Operations on Process.

<details>
 <summary>Click vào đây để xem thêm.</summary>
  
System Call fork()

![image](https://github.com/user-attachments/assets/03f52db4-8584-4a37-abd4-d4ce096a209a)

Exec Family

![image](https://github.com/user-attachments/assets/7c690a80-1f7c-419c-bdee-24faba94479d)

Process Termination

![image](https://github.com/user-attachments/assets/518e6a98-c00b-4e1d-a8b9-a71cb201d63f)

### 3.5. Process Management.

![image](https://github.com/user-attachments/assets/9a3559a5-59d1-41e2-8960-0f83d695c7ce)

- fork() wait() exit()

### 3.6. Orphane Process and Zombie Process.

#### 3.6.1 Orphane Process.


#### 3.6.2 Zombie Process.

</details>



