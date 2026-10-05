# dayservice

Trang tĩnh một tệp (`index.html`) cho sổ ngày. Dữ liệu người dùng nằm trên từng máy, trong `localStorage` (các khóa `kaigo_v1`, `kaigo_ord`, `kaigo_plan`). Cập nhật trang không xóa các khóa này.

## Đồng bộ iPhone và máy tính

Đồng bộ tự động qua **bin riêng** trên [JSONBin](https://jsonbin.io). Không có máy chủ riêng. Không có nút đẩy / kéo.

1. Tạo tài khoản JSONBin miễn phí.
2. Tạo **một bin Private** (riêng tư).
3. Chép **Bin ID** và **Master Key** (hoặc Access Key có quyền đọc và ghi).
4. Mở **cùng một địa chỉ https** trên iPhone và trên máy tính.
5. Vào **設定・バックアップ / Cài đặt và sao lưu**, dán Bin ID và khóa **một lần trên điện thoại** và **một lần trên máy tính**.

Sau đó ứng dụng tự gửi sau mỗi lần lưu, và khi mở trang sẽ nhận bản trên mây nếu bản đó mới hơn lần đồng bộ gần nhất của máy này. Bin ID và khóa chỉ lưu trên máy (`kaigo_sync_bin`, `kaigo_sync_key`), không ghi vào GitHub và không nằm trong tệp sao lưu.

Đừng chia sẻ Bin ID hoặc khóa. Ai có cả hai sẽ đọc và sửa được toàn bộ thông tin sức khỏe. Gói miễn phí của JSONBin khoảng 100KB; nhiều ảnh đính kèm có thể không gửi được.

Nếu chưa dán đủ Bin ID và khóa, đồng bộ tắt, không báo lỗi liên tục.

Lần đầu dán khóa: nếu máy đang có dữ liệu mà bin trống, bin mới, hoặc bản mây cũ hơn, máy này chỉ **gửi lên**, không bị ghi đè. Máy trống mới nhận dữ liệu từ mây. Nếu hai bên đều có dữ liệu và không rõ bản nào mới hơn, ứng dụng hỏi trước khi thay.

## Sao lưu tệp (khi không có mạng)

Trong Cài đặt vẫn có nút tạo bản sao lưu và lưu `kaigo-backup.json`. Có thể chuyển tệp đó bằng AirDrop hoặc USB, rồi khôi phục trên máy kia.

## Kiểm tra sau khi cập nhật

1. Mở trang trên điện thoại và xác nhận danh sách người vẫn còn.
2. Dán Bin ID và khóa trong Cài đặt, chỉ một lần.
3. Đợi dòng trạng thái, hoặc đóng rồi mở lại trang. Trạng thái phải hiện đã gửi (送信 / Đã gửi).
4. Trên máy tính, mở cùng địa chỉ, dán cùng Bin ID và cùng khóa. Danh sách hiện ra, và điện thoại không bị xóa.
