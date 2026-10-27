# Cổng Quà Tặng VIP — Landing Page (aerialskylab.com)

Landing page **1 bước** bằng **HTML thuần** (toàn bộ CSS + JS nằm trong `index.html`), giao diện **sáng**, dành cho link đăng ký:

`https://aerialskylab.com/wap/#/register`

![Mobile](preview/mobile.png)

## Nội dung trang

| Thành phần | Ghi chú |
|---|---|
| Badge "Ưu đãi hội viên mới" | Dải vàng nổi bật |
| Icon quà tặng + tiêu đề | "Chào mừng đến với Cổng Quà Tặng VIP" |
| Bảng "Người chơi vừa nhận thưởng" | 3 dòng thưởng: **Đăng Ký 88k / Nạp 188k / Nạp 288K**, tự chạy, dừng khi rê chuột |
| Checkbox 18+ | Bắt buộc tích thì nút mới bấm được |
| Nút "ĐĂNG KÝ NGAY" | Sáng màu cam–đỏ, bấm là chuyển thẳng tới link đài |
| Footer | © 2026 Gift Center. Bảo mật tuyệt đối. |

**Bước 2 (xác nhận nhận thưởng) của mẫu cũ đã được bỏ** — chỉ còn bước 1 như yêu cầu.

## Đổi link đài / thêm mã

Mở `index.html`, sửa khối `CONFIG` ở cuối file:

```js
var CONFIG = {
  destination: 'https://aerialskylab.com/wap/#/register', // link đài
  promoCode: '',        // điền 'ads2b004' nếu muốn tự gắn ?code=ads2b004
  newTab: false         // true = mở tab mới
};
```

## Chạy thử

- Mở trực tiếp `index.html` bằng trình duyệt, hoặc
- `python -m http.server 8080` rồi vào `http://localhost:8080`

## Deploy

- **Netlify Drop**: kéo thả file `index.html` vào https://app.netlify.com/drop
- **Vercel**: `vercel --prod`
- **Cloudflare Pages** / **GitHub Pages**: trỏ tới thư mục này

## Cấu trúc

```
index.html            # toàn bộ trang (HTML + CSS + JS)
README.md
preview/mobile.png    # ảnh xem trước bản mobile
preview/desktop.png   # ảnh xem trước bản desktop
```

## Ghi chú kỹ thuật

- Mobile-first (thẻ 430px, tự co giãn), an toàn với tai thỏ / safe-area.
- Font Be Vietnam Pro (Google Fonts), fallback Segoe UI.
- Không dùng thư viện, ảnh hay video bên ngoài → tải nhanh, không lỗi ảnh.
- Ticker tự chạy vô hạn; tôn trọng `prefers-reduced-motion`.
- Trong app TikTok / Facebook / Zalo trên Android: tự mở bằng Chrome để tránh webview chặn đăng ký.

© 2026 Gift Center. Bảo mật tuyệt đối.
