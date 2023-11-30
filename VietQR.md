EMVCo là một tổ chức toàn cầu được thành lập bởi sáu công ty thẻ tín dụng hàng đầu thế giới: American Express, Discover, JCB, Mastercard, UnionPay và Visa. Mục tiêu của EMVCo là tạo ra các tiêu chuẩn và quy trình để đảm bảo tính tương thích và an toàn của các giao dịch thanh toán bằng thẻ thông minh (smart card) hoặc thiết bị di động (mobile device).

EMVCo là viết tắt của Europay, Mastercard và Visa, ba công ty thẻ tín dụng đầu tiên tham gia vào việc phát triển các tiêu chuẩn EMV. EMV là một tập hợp các thông số kỹ thuật cho các thẻ thông minh và các thiết bị đọc thẻ, bao gồm cả các yếu tố về phần cứng, phần mềm, giao tiếp và bảo mật. EMV cũng bao gồm các quy định về xác thực giao dịch, quản lý rủi ro và xử lý sự cố.

EMVCo cũng chịu trách nhiệm cho việc phát triển và duy trì các tiêu chuẩn khác liên quan đến thanh toán di động, như EMV Contactless, EMV QR Code, EMV Secure Remote Commerce và EMV 3-D Secure. Ngoài ra, EMVCo cũng cung cấp các dịch vụ kiểm tra và chứng nhận cho các sản phẩm và giải pháp thanh toán tuân thủ các tiêu chuẩn EMV.

EMVCo là một tổ chức độc lập và không phải là một cơ quan quy định hay chính phủ. EMVCo hợp tác với các bên liên quan khác trong ngành thanh toán, như các ngân hàng, các nhà cung cấp dịch vụ, các nhà sản xuất thiết bị, các cơ quan tiêu chuẩn và các tổ chức quốc tế để nâng cao chất lượng và an ninh của các giao dịch thanh toán trên toàn cầu.

======================================

VietQR là một tiêu chuẩn mã QR dành cho thanh toán điện tử tại Việt Nam, được phát triển bởi Ngân hàng Nhà nước Việt Nam (NHNN) và EMVCo. VietQR được thiết kế để tương thích với các tiêu chuẩn quốc tế về mã QR, như EMV QR Code và ISO 20022. VietQR cho phép người dùng thanh toán cho các sản phẩm và dịch vụ bằng cách quét mã QR bằng điện thoại thông minh, thay vì sử dụng tiền mặt hay thẻ.

======================================

Lợi ích của VietQR trong giao dịch hiện đại:
- Dễ dàng tạo ra các mã QR Code để thanh toán nhanh và được chấp nhận bởi hơn 60 ngân hàng và dịch vụ trong lãnh thổ Việt Nam.
- Giảm thiểu khản năng chuyển tiền nhầm (do nhập sai thông tin người hưởng thụ).
- Giảm thiểu lừa đảo (do sử dụng mã QR Tĩnh, bị dán đè).

======================================

Cấu trúc của một chuỗi VietQR
00020101021238570010A00000072701270006970403011300110123456780208QRIBFTTA530370454061800005802VN62340107NPS68690819thanh toan don hang63042E2E

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
    - Thông tin người thụ hưởng:
        - 0010A000000727: Mã cố định của VietQR
            - 00: ID của dữ liệu.
            - 10: Chiều dài của dữ liệu.
            - A000000727: Chuỗi cố định của VietQR
        - 01270006970403011300110123456780208QRIBFTTA: Thông tin người thụ hưởng
            - 01: ID của dữ liệu.
            - 27: Chiều dài của dữ liệu.
            - 0006970403011300110123456780208QRIBFTTA: Chuỗi định danh người hưởng thụ.
                - 0006970403: Chuỗi định danh ngân hàng hưởng thụ.
                    - 00: ID của dữ liệu.
                    - 06: Chiều dài của dữ liệu.
                    - 970403: Mã ngân hàng (refer giá trị BIN trong API: https://api.vietqr.io/v2/banks)
                - 01130011012345678: Chuỗi định danh người hưởng thụ.
                    - 01: ID của dữ liệu.
                    - 13: Chiều dài của dữ liệu.
                    - 0011012345678: Số thẻ hoặc số tài khoản thụ hưởng.
                - 0208QRIBFTTA: Chuỗi định danh loại hưởng thụ.
                    - 02: ID của dữ liệu.
                    - 08: Chiều dài của dữ liệu.
                    - QRIBFTTA: Loại tài khoản hưởng thụ (QRIBFTTA: Tài khoản | QRIBFTTC: Thẻ)

    
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
    - Thông tin bổ sung:
        - 0107NPS6869: Mã hóa đơn
            - 01: ID của dữ liệu
            - 07: Chiều dài của dữ liệu.
            - NPS6869: Mã hóa đơn.
        - 0819thanh toan don hang: Nội dung lời nhắn
            - 08: ID của dữ liệu
            - 19: Chiều dài của dữ liệu.
            - thanh toan don hang: Nội dung lời nhắn
            
    => Additional Data Field Template.

- 63042E2E: Chuỗi CRC (dùng để xác thực nội dung, là chuỗi mã hóa CRC-CCITT (0xFFFF) của các chuỗi phía trước)
    - 63: ID của dữ liệu.
    - 04: Chiều dài của dữ liệu.
    - 2E2E: CRC-CCITT (0xFFFF).
    
    => Country Code.

CRC: https://www.lammertbies.nl/comm/info/crc-calculation
Bank: https://api.vietqr.io/v2/banks

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
