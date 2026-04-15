---
description: >-
  Hướng dẫn đồng bộ SKU, tồn kho và cân nặng thưc tế. Dữ liệu sẽ áp dụng khi sao
  chép sản phẩm từ  cho Shopee => Tiktok, Lazada
---

# 🎩 Đồng bộ dữ liệu sản phẩm

{% hint style="warning" %}
**Từ ngày 01/11/2025**, Shopee **ngừng cho phép truy cập dữ liệu tồn kho sản phẩm qua API**.



**Nếu bạn sao chép sản phẩm từ chính shop của mình** (bạn là **chủ shop đó**):\
👉 Bạn vẫn có thể **xuất file Excel từ Shopee** và **tải lên hệ thống** để đồng bộ các thông tin **tồn kho, SKU, kích thước và cân nặng**.



**Nếu bạn sao chép sản phẩm từ shop khác** (không thuộc quyền sở hữu của bạn):\
⚠️ Hiện tại **không thể đồng bộ tồn kho** hoặc **cập nhật cân nặng, kích thước thực tế** cho những sản phẩm này.
{% endhint %}

## 1) Tải Excel dữ liệu sản phẩm

Đăng nhập vào Shop gốc > Chọn cập nhật hàng loạt

<figure><img src="../../.gitbook/assets/image (1) (4).png" alt=""><figcaption></figcaption></figure>

* **Thông tin bán hàng** đồng bộ SKU phân loại và tồn kho thực tế
* **Thông tin vận chuyển** đồng bộ cân nặng, dài rộng và cao

<figure><img src="../../.gitbook/assets/image (19) (2).png" alt=""><figcaption><p>Xuất Excel</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/shopee_download_excel_product_sku.gif" alt=""><figcaption></figcaption></figure>

## 2) Cập nhật lên hệ thống

Truy cập vào link sau => [https://autoshopee.com/public/shopee/productSync](https://autoshopee.com/public/shopee/productSync)

Dán link Shop gốc vào của bạn vào

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Tải lên 2 file "Thông tin vận chuyển" và "Thông tin báng hàng" bạn vừa tải ở bước 1

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Kết quả hiển thị như thế này là thành công

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

## 3) Nhập sản phẩm vào Kho

Bạn nhập sản phẩm vào Kho như bình thường phần mềm sẽ tự động theo đúng dữ liệu bạn đã cập nhật

<figure><img src="../../.gitbook/assets/Screenshot_1.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Nếu bạn có sản phẩm mới đăng lên Shop bạn cần cập nhật lại SKU và cân nặng mới nhé
{% endhint %}
