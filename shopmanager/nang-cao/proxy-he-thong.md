---
description: ShopManager có hỗ trợ hệ thống Proxy miễn phí cập nhật liên tục
---

# Proxy hệ thống

{% hint style="warning" %}
Lưu ý sử dụng Proxy sẽ chậm hơn bình thường 30-40% nhé.\
Nếu bạn không đặt đơn ảo (tách biệt Shop chính với Shop đặt đơn) thì không nhất thiết dùng Proxy nhé
{% endhint %}

## 1) Cài đặt

{% embed url="https://youtu.be/R5x2WXi5Le0" %}

### a) Windows

{% hint style="info" %}
**Tải phần mềm Putty và cài đặt**

\*\*\*\*[https://drive.google.com/drive/folders/1yrxSB0EhigD8xILeOS6FataHiJ60U4WG?usp=sharing](https://drive.google.com/drive/folders/1yrxSB0EhigD8xILeOS6FataHiJ60U4WG?usp=sharing)
{% endhint %}

![Chọn 64 bit](<../../.gitbook/assets/image (129).png>)

![Bấm Next > Next vài đặt bình thường](<../../.gitbook/assets/image (130).png>)

### b) MacOs

{% hint style="warning" %}
Nếu bạn không rành kĩ thuật có thể nhờ hỗ trợ nhé
{% endhint %}

![Mở Teriminal](<../../.gitbook/assets/image (131).png>)

Dán dòng lệnh sau

```
xcode-select --install
```

Sau đó chạy

```bash
curl -O -L http://downloads.sourceforge.net/project/sshpass/sshpass/1.09/sshpass-1.09.tar.gz && tar xvzf sshpass-1.09.tar.gz && cd sshpass-1.09 && ./configure && make && sudo make install
```

![Dán dòng lênh trên](<../../.gitbook/assets/image (133).png>)

Tới bước này bạn gõ **pass của máy tính** => rồi nhấn enter (lúc gõ pass sẽ không hiện pass bạn cứ gõ rồi nhấn enter)

![Gõ pass và nhấn Enter](<../../.gitbook/assets/image (239).png>)

## 2) Sử dụng

1. Mở phần mềm
2. Mở Proxy (gốc phải màn hình)
3. Tạo Proxy cổng mới (bạn có bao nhiêu Shop tạo bấy nhiêu cổng)
4. Đợi các Proxy kết nối đầy đủ (kết nối xanh lá)

![Tạo Proxy](<../../.gitbook/assets/image (134).png>)

![Bấm tự chọn Proxy](<../../.gitbook/assets/image (135).png>)

Đăng nhập vào phần mềm

![Địa chỉ IP của Proxy](<../../.gitbook/assets/image (136).png>)
