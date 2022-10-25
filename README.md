### Các lệnh cơ bản
+ `cd` : Di chuyển đển thư mục khác

+ `ls` : Liệt kê nội dung thư mục
   + `ls -l` : Gồm 7 trường:  `- rw- rw- r--.` `1` `Owner` `Group` `1024`  `Feb 26 07:08` `file1`
  
 ```
 1. Quyền của user, group other
 2. số liên kết
 3. Owner của file
 4. Group của file
 5. Size
 6. Last modified date
 7. Name
 ```
   

### Quyền truy cập `- rw- rw- r--`

+ `-` : file
+ `d` : thư mục

+ `rw-`: đầu tiên là quyền riêng của Owner
+ `rw-`: thứ 2 là quyền dành cho người dùng Group 
+ `rw-`: thứ 3 là quyền dành cho người dùng khác

### Liên kết
+ `hard-link`: 


+ `soft-link`:


## Chỉ số inode: 
+ Cách xem chỉ ố inode: `ls -i` là chỉ số 

Trong inode chứa các thông tin sau:
+ Dung lượng file tính bằng bytes
+ Device ID: id của device lưu file (sda, sda1)
+ User ID: id của owner
+ Group ID: id của nhóm 
+ File mode

   
### File chứa thông tin người dùng `/etc/passwd` - 7 trường

Dòng đầu là thông tin của user root, tiếp theo là thông tin các user khác trong hệ thống, cuối cùng là tài khoản người dùng

`root` : `x` : `0` : `0` : `root` : `/root` : `/bin/bash`
```
1. Tên của User : root
2. Mật khẩu đã được mã hóa, lưu ở trong /etc/shadow
3. User ID: 0
4. Group ID: 0
5. Mô tả về người dùng (commnet): root
6. Đường dẫn thư mục cua user: /root
7. Loại Shell sẽ hoạt động khi user login: /bin/bash
```
### File chứa thông tin mật khẩu của tất cả người dùng `/etc/shadow`, chỉ có root mới quyền đọc - 8 trường

bean:$1$m/VeowYl$11qShSek/Kh7GQ1:18888:0:99999:7:::



### Base Permission (quyền cơ sở) & Umask

+ `Usmask` (user file-creation mode mask) là quyền mặc định của một file hay một thư mục khi mới được tạo.
+ Quyền chính thức của file = Umask + BS
+ BS của một file bất kỳ là: 666

```
+ 7 = read write execute  `rwx`
+ 6 = read write          `rw-
+ 5 = read execute        `r-x`
+ 4 = read                `rw-`
+ 3 = write execute       `-wx`
+ 2 = write               `-w-`
+ 1 = execute             `--x`
+ 0 = None
```

### chmod options permissions file name
user -> group -> other

[options]
`+` = add
chmod u+x a.txt : cấp quyền exec cho a.txt

`-` = remove
chmod g-x a.txt


`=` = apply

Kết hợp với nhau: chmod u+w,g=r,o=x a.txt

[flags]

-f, --silent, --quiet :  Suppress most error messages.
-R, --recursive : directory recursively 

`Process giao tiếp với kernal bằng system call`








