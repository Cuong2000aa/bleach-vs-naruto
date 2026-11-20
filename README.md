# ⚔️ Bleach vs Naruto 3.3 - Web Edition (with Modular SWF Expansion)

Trò chơi đối kháng huyền thoại **Bleach vs Naruto (死神VS火影 - BVN)** phiên bản chạy trực tiếp trên nền tảng Web thông qua trình giả lập **Ruffle (WebAssembly)**, tích hợp sẵn hệ thống **Modular SWF (Fighter Packs)** giúp dễ dàng tùy biến, mở rộng và thêm nhân vật mới.

![Bleach vs Naruto Banner](assets/map/random.png)

---

## 🌟 Tính Năng Nổi Bật

1. **Chơi Trực Tiếp Trên Trình Duyệt (Web Browser):**
   * Không cần Flash Player, chạy mượt mà trên Chrome, Firefox, Safari, Edge và cả thiết bị di động.
   * Tự động điều chỉnh kích thước và hỗ trợ chế độ **Toàn Màn Hình (Fullscreen)**.
2. **Hai Chế Độ Chơi Song Song:**
   * **🎮 Bản Full Game 3.3 (`game.swf`):** Đầy đủ các chế độ chơi Arcade, VS COM, Team Play, Training với 40+ tướng kinh điển.
   * **⚡ Chế Độ Mở Rộng Modular (`FighterTester.swf`):** Sử dụng kiến trúc module độc lập nạp file từ `assets/fighter/`, cho phép kiểm tra chiêu thức và test tướng tùy biến ngay lập tức.
3. **Kho Tài Nguyên Nhân Vật Rời (`assets/fighter/`):**
   * 38+ file `.swf` độc lập của từng tướng chính (Ichigo, Naruto, Sasuke, Madara, Pain, Itachi, Aizen, Byakuya, Kenshin,...).
   * 37+ file `.swf` trợ thủ (Minato, Hinata, Yamamoto, Yoruichi,...).
   * 14 map sàn đấu kèm hình ảnh xem trước.

---

## 🎮 Hướng Dẫn Phím Điều Khiển

| Thao Tác | Người Chơi 1 (P1) | Người Chơi 2 (P2) |
|---|---|---|
| **Di chuyển** | `A` / `D` | `←` / `→` |
| **Nhảy / Ngồi** | `W` / `S` | `↑` / `↓` |
| **Tấn công thường** | `J` | `1` (Numpad) |
| **Nhảy cao** | `K` | `2` (Numpad) |
| **Lướt nhanh (Dash)** | `L` | `3` (Numpad) |
| **Chiêu phụ** | `U` | `4` (Numpad) |
| **Tuyệt chiêu (Ultimate)** | `I` | `5` (Numpad) |
| **Gọi trợ thủ** | `O` | `6` (Numpad) |

---

## 🛠️ Cách Thêm / Tùy Biến Tướng Mới (Import Custom SWF)

Game được tổ chức theo kiến trúc Plug & Play:

1. **Thêm file SWF:**
   * Đặt file `.swf` nhân vật mới (ví dụ: `goku.swf` hoặc `luffy.swf`) vào thư mục:
     ```text
     assets/fighter/
     ```
2. **Khai báo trong cấu hình:**
   * Mở file `assets/config/fighter.xml` và thêm thẻ nhân vật:
     ```xml
     <fighter id="goku" name="Son Goku" comic_type="0">
       <file url="assets/fighter/goku.swf" startFrame="1"/>
     </fighter>
     ```
3. **Chạy thử:**
   * Chọn chế độ **Chế Độ Mở Rộng** trên giao diện Web để chiến ngay nhân vật vừa thêm!

---

## 📜 Bản Quyền & Tác Giả
* Game gốc được phát triển bởi **剑jian** và nhóm **5DPLAY Game Studio**.
* Trình giả lập WebAssembly được phát triển bởi dự án mã nguồn mở **Ruffle**.
