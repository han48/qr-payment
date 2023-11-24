Cấu trúc của một chuỗi VietQR
00020101021238570010A00000072701270006970403011300110123456780208QRIBFTTA530370454061800005802VN62340107NPS68690819thanh toan don hang630463042E2E

- 000201010212: Chuỗi xác nhận QR có định dạng theo tiêu chuẩn EMVCo.
    - 00: ID của dữ liệu.
    - 02: Chiều dài của dữ liệu.
    - 01: Giá trị của dữ liệu.
    => Payload Format.
    - 01: ID của dữ liệu.
    - 02: Chiều dài của dữ liệu.
    - 12: Giá trị của dữ liệu (11: QR tĩnh | 12: QR động).
    => Point of Initiation Method.

- 38570010A00000072701270006970403011300110123456780208QRIBFTTA: Chuỗi xác nhận thông tin người thụ hưởng.
    - 38: ID của dữ liệu.
    - 57: Chiều dài của dữ liệu.
    - 0010A00000072701270006970403011300110123456780208QRIBFTTA: Thông tin người thụ hưởng.
    => Consumer Account Information.

- 5303704: Chuỗi xác nhận loại tiền tệ
    - 53: ID của dữ liệu.
    - 03: Chiều dài của dữ liệu.
    - 704: Mã tiền tệ (VND).
    => Transaction Currency.

- 5406180000: Chuỗi xác nhận số tiền thanh toán.
    - 54: ID của dữ liệu.
    - 06: Chiều dài của dữ liệu.
    - 180000: Số tiền giao dịch.
    => Transaction Amount.

- 5802VN: Chuỗi xác nhận thông tin quốc gia.
    - 58: ID của dữ liệu.
    - 02: Chiều dài của dữ liệu.
    - VN: Mã quốc gia (Việt Nam).
    => Country Code.

- 62340107NPS68690819thanh toan don hang6304: Chuỗi xác nhận thông tin bổ sung.
    - 62: ID của dữ liệu.
    - 34: Chiều dài của dữ liệu.
    - 0107NPS68690819thanh toan don hang: Thông tin bổ sung.
    => Additional Data Field Template.

- 63042E2E: Chuỗi CRC (dùng để xác thực nội dung, là chuỗi mã hóa CRC-CCITT (0xFFFF) của các chuỗi phía trước)
    - 63: ID của dữ liệu.
    - 04: Chiều dài của dữ liệu.
    - 2E2E: CRC-CCITT (0xFFFF).
    => Country Code.

CRC: https://www.lammertbies.nl/comm/info/crc-calculation

Bảng mã tiền tệ:
| Mã tiền tệ | Ký hiệu tiền tệ | Ý nghĩa           |
| ---------- |:---------------:| -----------------:|
| 392        | JPY             | Yên Japan         |
| 410        | KRW             | Won Korea         |
| 458        | MYR             | Ringgit Malaysia  |
| 156        | CNY             | Nhân dân tệ       |
| 360        | IDR             | Rupiah Indonesia  |
| 608        | PHP             | Peso Philippines  |
| 702        | SGD             | Dollar Singapore  |
| 764        | THB             | Baht Thailand     |
| 704        | VND             | Viet Nam          |

Bảng mã quốc gia:
| Mã   | Quốc Gia      |
| ---- | -------------:|
| JP   | Japan         |
| KR   | Korea         |
| MY   | Malaysia      |
| RC   | China         |
| RI   | Indonesia     |
| RP   | Philippines   |
| SG   | Singapore     |
| TH   | Thailand      |
| VN   | Viet Nam      |
