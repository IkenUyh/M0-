# AI Log — M0 · Dựng môi trường

*Buổi: Thực hành 1 · Ngày: 26/09/2026 · Agent: Antigravity*

---

## Yêu cầu đặt ra cho agent

Đọc file `TH1-dung-moi-truong.md`, lên plan toàn bộ yêu cầu và tự động tạo các file cần thiết trong repo mẫu local cho đề tài **Quản lý gửi xe ký túc xá**, sau đó hướng dẫn push lên GitHub.

## Agent đã làm gì

1. **Đọc và phân tích** `TH1-dung-moi-truong.md` (137 dòng) và toàn bộ cấu trúc `repo-mau/` bao gồm `scripts/kiem_moc.py` để hiểu CI kiểm gì.
2. **Kiểm tra M0** bằng cách chạy `scripts/kiem_moc.py M0` — xác định 7/8 mục đạt (chỉ thiếu 4 thành viên commit).
3. **Nhận đề tài** từ người dùng: Hệ thống quản lý gửi xe KTX với 5 user story (đăng ký xe, quét thẻ, tra cứu phí, thống kê, biên bản sự cố) và 3 tác nhân (Sinh viên, Bảo vệ, Ban quản lý).
4. **Cập nhật toàn bộ** file M0 theo đề tài mới:
   - `README.md` — mô tả hệ thống gửi xe KTX, ràng buộc nghiệp vụ (xe không quét vào/ra trùng)
   - `diagrams/class.mmd` — sơ đồ 9 lớp + 3 enum (User, Student, SecurityGuard, Manager, Vehicle, ParkingCard, ParkingRecord, PaymentTransaction, IncidentReport)
   - `diagrams/xem.md` — wrapper Mermaid cho GitHub render
   - `src/index.html` — trang tĩnh deploy được, chủ đề gửi xe KTX
   - `docs/cau-hoi-khach-hang.md` — 3 câu hỏi bối cảnh về gửi xe
   - `phan-tu/M0.md` — bản phản tư (≥ 40 từ, placeholder hash)
   - `ai-log/M0-setup.md` — file này

## Quyết định thiết kế

- Sơ đồ lớp dùng **kế thừa** (User là abstract class, Student/SecurityGuard/Manager kế thừa) — phù hợp OOP và dễ mở rộng thêm role sau.
- Tách Vehicle và ParkingCard thành 2 lớp riêng vì 1 xe có đúng 1 thẻ nhưng thẻ có thể hết hạn/cấp lại.
- ParkingRecord ghi lại mọi lần quét (kể cả thất bại) — phục vụ audit trail.
- Ràng buộc nghiệp vụ chính: kiểm tra VehicleStatus trước khi cho quét vào/ra, tránh quét trùng.
- `src/index.html` dùng pure HTML/CSS, không framework — đúng với lời khuyên trong TH1.

## Việc người dùng cần làm tay

1. Tạo repo GitHub (`Use this template`), thêm collaborator, mọi người commit
2. Kết nối Cloudflare Pages, điền URL vào README
3. Tạo nhánh `moc/M0`, mở PR
4. Sau khi push: lấy hash commit thật điền vào `phan-tu/M0.md`

## Lệnh agent đề xuất (đã xem qua)

```bash
# Không có lệnh rm -rf, sudo, hay dán API key nào
git checkout -b moc/M0
git push -u origin moc/M0
```
