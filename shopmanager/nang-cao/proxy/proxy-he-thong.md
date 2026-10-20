---
description: >-
  Hướng dẫn cài đặt proxy nuôi nick Shopee trên ShopManager. Cô lập môi trường trình duyệt, chống quét khóa shop liên đới, tặng proxy hệ thống miễn phí cho seller.
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
---

# Proxy Shopee Là Gì? Cách Dùng Proxy Nuôi Nhiều Nick Shopee Không Bị Quét Shop

> **Trả lời nhanh (Direct Answer):** Proxy Shopee là địa chỉ IP trung gian giúp mỗi gian hàng Shopee hoạt động trên một đường truyền mạng riêng biệt. Khi nuôi hoặc vận hành nhiều shop trên cùng một máy tính, việc gán proxy riêng cho từng trình duyệt giúp che giấu dấu vân tay thiết bị, ngăn chặn Shopee phát hiện hành vi trùng lặp IP và bảo vệ các shop không bị khóa liên đới.

{% hint style="warning" %}
**Lưu ý khi sử dụng:** Tốc độ kết nối qua Proxy công cộng sẽ chậm hơn mạng gia đình thông thường (khoảng 30-40%). 

Hệ thống Proxy tích hợp sẵn trên ShopManager được chia sẻ miễn phí nhằm hỗ trợ seller cách ly mạng cơ bản. Nếu bạn cần nuôi các shop doanh thu lớn hoặc chạy tác vụ nặng, chúng tôi khuyến nghị nên mua thêm Proxy IPv4/Dân cư tĩnh (Static Residential Proxy) chất lượng cao để đảm bảo độ mượt mà tối đa.
{% endhint %}

## 1) Hướng Dẫn Cài Đặt Kết Nối Proxy

{% embed url="https://youtu.be/R5x2WXi5Le0" %}

### a) Dành Cho Hệ Điều Hành Windows

{% hint style="info" %}
**Tải phần mềm Putty và cài đặt:**

\*\*\*\*[https://drive.google.com/drive/folders/1yrxSB0EhigD8xILeOS6FataHiJ60U4WG?usp=sharing](https://drive.google.com/drive/folders/1yrxSB0EhigD8xILeOS6FataHiJ60U4WG?usp=sharing)
{% endhint %}

![Chọn phiên bản 64 bit](<../../../.gitbook/assets/image (129).png>)

![Bấm Next > Next và cài đặt bình thường](<../../../.gitbook/assets/image (130).png>)

### b) Dành Cho Hệ Điều Hành macOS

{% hint style="warning" %}
Nếu bạn không rành thao tác kỹ thuật dòng lệnh trên macOS, hãy liên hệ Zalo CSKH AutoShopee để kỹ thuật viên hỗ trợ Ultraview/Anydesk nhé.
{% endhint %}

![Mở ứng dụng Terminal](<../../../.gitbook/assets/image (131).png>)

Dán dòng lệnh sau và nhấn Enter:

```bash
xcode-select --install
```

Sau đó chạy tiếp lệnh cài đặt:

```bash
curl -O -L http://downloads.sourceforge.net/project/sshpass/sshpass/1.06/sshpass-1.06.tar.gz && tar xvzf sshpass-1.06.tar.gz && cd sshpass-1.06 && ./configure && make && sudo make install
```

![Dán dòng lệnh trên vào Terminal](<../../../.gitbook/assets/image (133).png>)

Tại bước này, bạn gõ **mật khẩu (password) của máy tính** => rồi nhấn Enter (lưu ý: lúc gõ mật khẩu trên Terminal sẽ không hiển thị ký tự, bạn cứ gõ đúng mật khẩu rồi nhấn Enter bình thường).

![Gõ mật khẩu và nhấn Enter](<../../../.gitbook/assets/image (239).png>)

## 2) Cách Kích Hoạt & Gán Proxy Cho Từng Gian Hàng Shopee

1. Mở phần mềm **ShopManager** trên máy tính.
2. Bấm vào mục **Proxy** (nằm ở góc phải màn hình).
3. Bấm **Tạo Proxy cổng mới** (bạn vận hành bao nhiêu gian hàng Shopee thì tạo bấy nhiêu cổng proxy riêng biệt).
4. Đợi các cổng Proxy chuyển sang trạng thái kết nối thành công (biểu tượng kết nối màu xanh lá).
5. Gán từng cổng Proxy này vào từng gian hàng trong danh sách quản trị shop để cô lập hoàn toàn môi trường mạng.

![Tạo cổng Proxy mới trên ShopManager](<../../../.gitbook/assets/image (134).png>)

![Bấm chọn Proxy cho gian hàng](<../../../.gitbook/assets/image (135).png>)

Đăng nhập vào Kênh Người Bán trên giao diện ShopManager:

![Kiểm tra địa chỉ IP an toàn của Proxy](<../../../.gitbook/assets/image (136).png>)
