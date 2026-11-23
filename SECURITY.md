# Cấu hình Bảo mật Cloudflare cho Bleach vs Naruto (bvn.portgame.cloud)

Zone ID: `676adfbcda5c810ad23a02a00522dd54` (portgame.cloud)

Cấu hình bảo mật hiện tại đồng bộ 100% với Gunny:

## 1. Geo-blocking WAF (Chỉ cho phép Việt Nam)
* **Rule ID**: `ea82e43d72f742899600c378e276b808`
* **Tên**: `Only allow Vietnam visitors for bvn.portgame.cloud`
* **Biểu thức**:
  ```text
  (http.host eq "bvn.portgame.cloud" and ip.geoip.country ne "VN")
  ```
* **Hành động**: **Block** (Chặn tất cả IP ngoài lãnh thổ Việt Nam ngay tại máy chủ rìa Cloudflare Edge).

## 2. Rate Limiting (Chống Spam / Flood / DDoS)
* **Rule ID**: `5855a3ddaf6d4776afd2264f5e2dfb90`
* **Tên**: `Rate limit gunny and bvn portgame.cloud (100 req/10s per IP, exclude static assets)`
* **Biểu thức**:
  ```text
  ((http.host eq "gunny.portgame.cloud" and not http.request.uri.path contains "/image/" and not http.request.uri.path contains "/flash/" and not http.request.uri.path contains "/sound/") or (http.host eq "bvn.portgame.cloud" and not http.request.uri.path contains "/assets/" and not http.request.uri.path contains "/bvn_web/" and not http.request.uri.path contains ".swf"))
  ```
* **Ngưỡng**: **100 requests / 10 giây** cho mỗi IP.
* **Thời gian phạt**: Chặn **10 giây** nếu vượt ngưỡng.
* **Ngoại lệ an toàn (Whitelist Assets)**: Đã loại trừ toàn bộ asset game tĩnh (`/assets/`, `/bvn_web/`, `.swf`) để người chơi khi vào trận tải map, âm thanh và nhân vật không bao giờ bị chặn nhầm.

## 3. Cấu hình SSL / TLS
* **Always Use HTTPS**: Bật (Tự động chuyển HTTP sang HTTPS).
* **Minimum TLS Version**: TLS 1.2+.
* **Security Level**: Medium.
* **Bot Fight Mode & Browser Check**: Bật bảo vệ chống crawler/bot xấu.
