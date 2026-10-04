# Bài 1: Khởi tạo Droplet trên DigitalOcean

### 1. Tạo SSH Keypair trên máy cá nhân
Chạy lệnh sau trên máy cá nhân để tạo SSH key (Sử dụng thuật toán ed25519 bảo mật cao):
```bash
ssh-keygen -t ed25519 -C "daotrongtri21092006@gmail.com" -f ~/.ssh/id_ed25519_do_ss2
```
Output:
```
Generating public/private ed25519 key pair.
Your identification has been saved in /Users/trongtri/.ssh/id_ed25519_do_ss2
Your public key has been saved in /Users/trongtri/.ssh/id_ed25519_do_ss2.pub
The key fingerprint is:
SHA256:DrKhNcpH9FuiDj+sRpeVYdGySq3H9B/bjat7EUcRh2M daotrongtri21092006@gmail.com
```

### 2. Các bước tạo Droplet
1. Đăng nhập vào DigitalOcean, nhấn **Create** -> **Droplets**.
2. Chọn Region: **Singapore**.
3. Chọn OS: **Ubuntu 22.04 LTS**.
4. Chọn Size: **Basic plan, Regular SSD, CPU Shared** ($4 hoặc $6/tháng).
5. Tại Authentication: Chọn **SSH Keys**. Bấm **New SSH Key** và paste nội dung file `~/.ssh/id_ed25519_do_ss2.pub` (đã tạo ở bước 1) vào.
6. Đặt tên Droplet và bấm **Create Droplet**.


### 3. Kết nối vào Droplet
Mở Terminal trên máy cá nhân và chạy lệnh (thay `<IP_ADDRESS_DROPLET>` bằng IP thật của Droplet):
```bash
ssh -i ~/.ssh/id_ed25519_do_ss2 root@<IP_ADDRESS_DROPLET>
```

Vì thẻ visa của em bị khoá nên ko thể tạo droplet