# CLAUDE.md

Hướng dẫn cho Claude Code khi làm việc trong repo này.

## Repo này là gì

Kho **nội dung tài liệu GitBook** của AutoShopee — bộ hướng dẫn sử dụng cho khách hàng, viết bằng **tiếng Việt**. Remote: `git@github.com:autoshopee/document.git`, xuất bản qua GitBook.

**Không có code, không build, không test, không dependency** — 92 file `.md` + 640 ảnh trong `.gitbook/assets/`. Đừng tìm `package.json`, đừng đề xuất thêm lint/CI/test.

## Cấu trúc

| Đường dẫn | Nội dung |
|---|---|
| `SUMMARY.md` | **Mục lục = sidebar GitBook.** Nguồn chuẩn của điều hướng |
| `README.md` | Trang chủ |
| `lien-he.md` | Thông tin liên hệ, hotline, số tài khoản |
| `shopmanager/` | App Shop Manager (Windows/macOS): quản lý, sản phẩm, đơn hàng, tự động, nâng cao, shop-admin |
| `extension/` | Extension trình duyệt: cài đặt, các chức năng trên Shopee |
| `autoshopee/` | Web AutoShopee: Shopee, sao chép đa sàn (TikTok/Lazada), thông báo đơn hàng |
| `xu-ly-loi/` | Khắc phục lỗi: Shopee, Windows, macOS |
| `.gitbook/assets/` | Toàn bộ ảnh và file đính kèm (phẳng, không thư mục con) |

Thư mục có trang cha thì dùng `README.md`; trang con nằm cùng cấp bên trong.

## 🔴 Luật bắt buộc

1. **Thêm/xoá/đổi tên trang → PHẢI sửa `SUMMARY.md` cùng lượt.** Trang không có trong `SUMMARY.md` là trang mồ côi, GitBook không hiện.
2. **Sync hai chiều với GitBook.** Commit trên `main` hầu hết do GitBook tự đẩy (`GITBOOK-<số>: <mô tả>`). Sửa tay ở local mà GitBook cũng đang sửa là dễ xung đột → `git pull` trước khi sửa, và báo user biết thay đổi cần được đồng bộ ngược lên GitBook.
3. **Không đụng frontmatter `layout:`** trừ khi user yêu cầu — đó là cấu hình hiển thị do GitBook sinh ra.
4. **Ảnh: chỉ tham chiếu file đã có trong `.gitbook/assets/`.** Không tự đổi tên/xoá/dọn ảnh "không dùng" — GitBook đánh số tên ảnh (`image (380).png`), xoá là gãy trang khác.
5. Nội dung viết cho **người dùng cuối không rành kỹ thuật**: câu ngắn, từng bước, kèm ảnh minh hoạ. Giữ nguyên giọng văn và emoji của các trang sẵn có.

## Cú pháp GitBook đang dùng

Frontmatter YAML (`description`, `cover`, `coverY`, `layout`), tiêu đề H1 thường kèm emoji.

```markdown
{% hint style="info" %}   <!-- info | warning | success | danger -->
Nội dung ghi chú
{% endhint %}

{% content-ref url="them-shop.md" %}
[them-shop.md](them-shop.md)
{% endcontent-ref %}

{% embed url="https://www.youtube.com/watch?v=..." %}
Video hướng dẫn
{% endembed %}

{% file src="../../.gitbook/assets/Mau 1.txt" %}
Mẫu in đơn 1
{% endfile %}

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
```

**Đường dẫn ảnh có dấu cách hoặc ngoặc phải bọc `<>`**:
`![Chú thích](<../../.gitbook/assets/image (13) (1) (1).png>)` — thiếu `<>` là ảnh vỡ.

## Kiểm chứng thay đổi

Không có lệnh build. Nghiệm thu bằng:

```bash
# 1. Trang mới đã vào mục lục chưa
grep -c "duong-dan-trang-moi.md" SUMMARY.md

# 2. Ảnh/file đính kèm nào bị tham chiếu mà không tồn tại (không ra dòng nào = OK)
grep -rhoP --include='*.md' --exclude=CLAUDE.md '\.gitbook/assets/.*?\.(png|jpg|jpeg|webp|gif|txt)' .   | sed 's#^\.gitbook/assets/##' | sort -u > /tmp/refs.txt
ls .gitbook/assets | sort -u > /tmp/have.txt
comm -23 /tmp/refs.txt /tmp/have.txt
```

Tại thời điểm viết file này: 356 tham chiếu asset, **0 tham chiếu gãy** — giữ nguyên con số 0 sau khi sửa.

## MCP GitBook

Server `gitbook` (`https://mcp.gitbook.com/mcp`) đã đăng ký ở **scope `local`** — chỉ hiệu lực trong project này, cấu hình nằm ở `~/.claude.json`, **không commit vào repo**. Dùng nó để đọc/tra nội dung space thay vì đoán.

| Định danh | Giá trị |
|---|---|
| Organization ID | `5RFnrey6nGpQ5BRGtnux` |
| Site ID | `site_NVN0Y` |
| Content Space ID | `-MgV0FZZTwTQwlMCjc86` |
| Variant | `AutoShopee.com` tại `/huong-dan` (mặc định) |
| **URL public** | https://support.autoshopee.com/ |
| Trang quản trị | https://app.gitbook.com/o/5RFnrey6nGpQ5BRGtnux/sites/site_NVN0Y/s/-MgV0FZZTwTQwlMCjc86/ |

Token API lưu ở KeePassXC entry **`Services/GitBook - API token`** (tài khoản đăng nhập ở `Services/GitBook`). **Không hardcode token vào bất kỳ file nào trong repo.**

11 tool: `list_sites` `get_site_structure` `list_site_topics` `get_page` `create_change_request` `submit_or_merge_change_request` `search` `describe_operation` `invoke_operation` `get_usage_guide` `report_tool_feedback`.

⚠️ **Nội dung đã publish chỉ sửa qua change request**, không ghi thẳng: `create_change_request` → `invoke_operation(updateChangeRequestContent)` → `submit_or_merge_change_request`. `list_sites` bắt buộc truyền `organizationId`.

Gỡ server: `claude mcp remove gitbook -s local`
