# Quản lý gửi xe ký túc xá — SE100 · Nhóm XX

Hệ thống hỗ trợ quản lý việc **gửi xe** của sinh viên tại ký túc xá (KTX).
Người dùng chính là sinh viên, bảo vệ và ban quản lý KTX.
Hệ thống giúp đăng ký xe, cấp thẻ/vé gửi xe, quét thẻ ra/vào cổng,
tra cứu phí gửi xe, thống kê số lượng xe và lập biên bản sự cố.
**Không được phép** xảy ra: xe đang trong bãi mà quét vào thêm lần nữa,
hoặc xe đang ngoài bãi mà quét ra thêm lần nữa.

## Thành viên

| STT | MSSV     | Họ và tên          | GitHub                                                  |
|-----|----------|--------------------|----------------------------------------------------------|
| 1   | 24520697 | Tô Kiến Huy        |                 |
| 2   | 24520269 | Huỳnh Cao Đạt      | [@estellra](https://github.com/estellra)                 |               
| 3   | 24520842 | Trần Lê Anh Khoa   | [@harutopia0](https://github.com/harutopia0)             |
| 4   | 24520248 | Trần Thanh Dân |   [@danttse](https://github.com/danttse)                  |

| Tên | GitHub | Chủ trì mốc |
|---|---|---|
| | | M1: Yêu cầu |
| | | M2: Mô hình hoá |
| | | M3–M4: Thiết kế |
| | | M5: Giao hàng |

## URL

- Bản chạy: https://...
- Pipeline: xem tab Actions

## Cấu trúc repo

```
docs/         yêu cầu, đặc tả use case, phân tích tác động
diagrams/     sơ đồ Mermaid (.mmd) — use case, lớp, tuần tự, trạng thái, C4
adr/          quyết định kiến trúc, mỗi quyết định một tệp
phan-tu/      bản phản tư M0–M5 và bảng phản hồi cáo buộc
ai-log/       bản ghi hội thoại với agent, theo mốc
src/          mã nguồn
.github/      workflow kiểm mốc — đừng sửa
AGENTS.md     ràng buộc kiến trúc cho agent đọc — viết ở M4
```

## Mốc

| Mốc | Hạn | Nộp gì | CI kiểm thêm |
|---|---|---|---|
| M0 | CN tuần 2 | README, đề tài, `docs/cau-hoi-khach-hang.md` (≥ 3 câu) | 4 người có commit |
| V1 | CN tuần 4 | Hệ thống chạy, `docs/hoi-cuu-vong1.md`, ai-log | Giảng viên kiểm tay, không tính điểm |
| M1 | CN tuần 5 | `docs/yeu-cau.md` | ≥ 3 tác nhân, ≥ 6 FR, ≥ 3 NFR có số, ≥ 1 BR |
| M2 | CN tuần 7 | `diagrams/use-case.mmd` (≥ 5 UC), `docs/dac-ta-UC-*.md` ×3, `diagrams/seq-*.mmd` ×2 | Mermaid parse được |
| M3 | CN tuần 9 | `diagrams/class.mmd` (≥ 5 lớp), `diagrams/state.mmd`, `docs/tu-danh-gia-M3.md` | Đối chiếu chéo lớp ↔ sequence; mọi lớp có trong docs/ |
| M4 | CN tuần 10 | `diagrams/c4-context.mmd`, `c4-container.mmd`, `docs/du-lieu.md`, `adr/0001-*.md`, `AGENTS.md` | ADR có ≥ 2 phương án; AGENTS.md hết comment mẫu |
| M5 | CN tuần 13 | Pipeline riêng xanh, URL sống, `docs/tac-dong-vong3.md`, `docs/trung-lap.md` có 2 lần đo | URL trả 200 |

Mốc nào cũng kèm `phan-tu/Mn.md` (M0 ≥ 40 từ, còn lại ≥ 120 từ, có mã commit) và một tệp trong `ai-log/`. Từ M2 thêm `phan-tu/Mn-phan-hoi.md`.

## Cách nộp mốc

1. Tạo nhánh `moc/Mn` rồi làm việc trên đó.
2. Mở Pull Request vào `main`, tiêu đề `Mn — [tên nhóm]`.
3. Đợi workflow **Kiểm mốc** chạy. Đỏ thì đọc log, sửa, push lại.
4. Xanh thì merge. Thời điểm merge là thời điểm nộp.

