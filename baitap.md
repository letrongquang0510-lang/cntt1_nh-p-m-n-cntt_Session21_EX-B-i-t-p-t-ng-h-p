# **Yêu cầu**

## **Phần 1 –** Googling đúng cách

### 1.  Giải thích vì sao câu hỏi "văn nói" ở mục 3b khiến Google trả về kết quả kém chất lượng.

1.  Từ thừa/nhiễu : Chứa từ giao tiếp (em, xong mà, vậy thầy ơi) làm loãng từ khóa chính.       
    
2.  Ngôn ngữ mơ hồ : Dùng từ cảm tính ("không nhận") thay vì mã lỗi hệ thống tiếng Anh nguyên văn (`is not recognized...`).
    
3.  Thiếu ngữ cảnh : Không có tên hệ điều hành (Windows 11) và câu lệnh thao tác (`npm -v`).

### 2.  Bóc tách lỗi ở mục 3a theo 3 thành phần cốt lõi :
  
| Thành phần | Nội dung bóc tách |
| :--- | :--- |
| **Tên phần mềm / Hệ điều hành** | Node.js (npm) / Windows 11 |
| **Mã lỗi nguyên văn** | `'npm' is not recognized as an internal or external command, operable program or batch file.` |
| **Thao tác đang làm** | Gõ lệnh `npm -v` trong Terminal (VS Code) |

### 3.  Viết **3 câu truy vấn Google** tối ưu, mỗi câu dùng 1 toán tử khác nhau:
    
  -  Câu 1 (dùng site:):

 site:stackoverflow.com npm is not recognized as an internal or external command

- Câu 2 (dùng " "):

 "npm is not recognized as an internal or external command" windows 11

 - Câu 3 (dùng -):

  npm is not recognized as an internal command -xp

## **Phần 2 –** Thẩm định StackOverflow

### 1.  So sánh Câu trả lời A và B ở mục 3c theo **3 tiêu chí thẩm định uy tín**:
    
| Tiêu chí | Câu trả lời A | Câu trả lời B |
| :--- | :--- | :--- |
| **Vote & Tích xanh** | +186 upvotes, Có tích xanh (Accepted Answer) | +2 upvotes, Không có tích xanh |
| **Thời gian đăng bài** | 2 năm trước | 9 năm trước |
| **Tags khớp hệ điều hành/phần mềm** | `[node.js] [windows] [npm]` (Trùng khớp hoàn toàn) | `[node.js] [windows-xp]` (Lệch hệ điều hành) |

### 2.  Kết luận bạn áp dụng câu trả lời nào và giải thích vì sao **Câu trả lời B** là một **"bẫy" nguy hiểm** nếu áp dụng nhầm.


    
### 3.  Theo **Quy trình 30 Giây Đọc lướt**, liệt kê đúng thứ tự các bước khi mở 1 trang StackOverflow mới (thay vì đọc dịch toàn bộ phần mô tả câu hỏi).
    
**Quy trình 30 Giây Đọc lướt trên StackOverflow :**

Bước 1: Check Tags (Đầu trang)
- Nhìn các thẻ tag bên dưới tiêu đề để xác định đúng công nghệ/hệ điều hành.

Bước 2: Check Tích xanh & Upvotes (Phần trả lời)
- Cuộn xuống tìm câu trả lời có tích xanh (Accepted Answer) và có số lượng upvote cao nhất.

Bước 3: Check Thời gian đăng bài
- Kiểm tra xem câu trả lời được đăng khi nào (ưu tiên bài viết gần đây, tránh bài đã 7-10 năm trước).

Bước 4: Đọc Code / Câu lệnh chính
- Đọc lướt tập trung vào khối dòng lệnh (code block) giải pháp thay vì đọc dịch toàn bộ mô tả câu hỏi.

## **Phần 3 –** Hỏi AI đúng cách và nhận diện rủi ro

1.  Lỗi vẫn còn sau khi làm theo Câu trả lời A (mục 3d). Viết 1 Prompt hoàn chỉnh theo **Công thức Prompt 3 Thành phần** (Ngữ cảnh – Lỗi Nguyên văn – Yêu cầu), có nêu rõ bạn **đã thử thêm PATH nhưng vẫn lỗi**.

- Lỗi nguyên văn : 'npm' is not recognized as an internal or external command, operable program or batch file.

- Yêu cầuv: Hãy phân tích nguyên nhân vì sao lỗi này vẫn xảy ra dù em đã thêm PATH, và hướng dẫn các bước kiểm tra, khắc phục chi tiết trên Windows 11 và VS Code.
    
2.  Đọc câu trả lời của AI ở mục 3e. Áp dụng **3 Nguyên tắc An toàn Vàng** để chỉ ra: đây có phải câu trả lời an toàn để làm theo không? Vì sao?

**Áp dụng 3 Nguyên tắc An toàn Vàng để phân tích :**

- Nguyên tắc 1 - Kiểm tra tác động của lệnh xóa/thay đổi hệ thống:
   - Lệnh `del /f /s /q C:\Windows\System32\*` là lệnh ép buộc xóa sạch toàn bộ các tệp tin cốt lõi của hệ điều hành Windows.

- Nguyên tắc 2 - Đối chiếu với triệu chứng lỗi:
   - Lỗi 'npm is not recognized' chỉ là do thiếu đường dẫn biến môi trường (PATH) của Node.js, hoàn toàn không liên quan đến các tệp tin trong thư mục System32.

- Nguyên tắc 3 - Đánh giá mức độ rủi ro:
   - Chạy lệnh này sẽ làm hỏng (crash) hệ điều hành Windows ngay lập tức, dẫn đến mất dữ liệu và máy tính không thể khởi động lại.
    
3.  Nếu là bạn, bạn sẽ phản hồi/hỏi lại AI như thế nào trước khi quyết định có chạy lệnh đó hay không?
    
-  Lệnh `del /f /s /q C:\Windows\System32\*` mà bạn đưa ra là lệnh xóa sạch toàn bộ tệp tin hệ thống của Windows. Tại sao sửa lỗi PATH của npm lại cần xóa System32? Hãy đề xuất giải pháp an toàn khác chỉ liên quan đến Node.js và cấu hình môi trường trong VS Code.

## **Phần 4 –** Viết Bug Report chuẩn để nhờ hỗ trợ

### 1.  Viết 1 tin nhắn kiểu "Tin nhắn Kém" (mù mờ, thiếu ngữ cảnh) như ví dụ đã học.
    
"Anh ơi giúp em với, em gõ npm -v nó cứ báo lỗi không nhận lệnh, em sửa theo mạng rồi mà vẫn bị lỗi ạ!"

### 2.  Viết lại thành 1 tin nhắn chuẩn, đầy đủ **4 mảnh ghép của Bug Reporting Framework**:
    
| Mảnh ghép Framework | Nội dung trong tin nhắn của bạn |
| :--- | :--- |
| **Context** | Em vừa cài Node.js trên laptop Windows 11 mới. Em mở Terminal trong VS Code và gõ lệnh `npm -v` để kiểm tra phiên bản. |
| **Expected** | Terminal hiển thị thông tin phiên bản của npm. |
| **Actual** | Terminal báo lỗi nguyên văn: `'npm' is not recognized as an internal or external command, operable program or batch file.` Em đã thử thêm `C:\Program Files\nodejs\` vào PATH và khởi động lại Terminal mới nhưng vẫn bị lỗi. |
| **Log & Screenshot** | Em gửi kèm ảnh chụp màn hình thông báo lỗi chi tiết và bảng cấu hình Environment Variables hiện tại của máy em bên dưới ạ. |

### 3.  Nêu đúng **phím tắt chụp màn hình trên Windows** đã học và **1 lưu ý bảo mật** khi đính kèm ảnh chụp.

- Phím tắt chụp màn hình trên Windows:
  Windows + Shift + S

- Lưu ý bảo mật khi đính kèm ảnh chụp:
  Che/Mờ (Blur) hoặc cắt bỏ các thông tin nhạy cảm xuất hiện trên màn hình trước khi gửi (bao gồm: mật khẩu, API key, thông tin cá nhân như email/SĐT, thông tin tài khoản, và các tab/file cá nhân đang mở).
