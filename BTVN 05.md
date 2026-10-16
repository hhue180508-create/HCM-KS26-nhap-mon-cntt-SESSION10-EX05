Bài thực hành tổng hợp Markdown: Smart-Farm 🌱

Bài làm dưới đây gồm 3 phần: phân tích hệ thống, file README.md hoàn chỉnh để đưa vào StackEdit và kiểm thử tình huống RAM đầy do dữ liệu nhật ký.

Phần 1. Phân tích hệ thống

1.1. Xác định Input và Output theo mô hình IPO
IPO là mô hình mô tả Input (đầu vào) → Process (xử lý) → Output (đầu ra).
Thành phần	Nội dung trong Smart-Farm
Input	Nhiệt độ, độ ẩm đất, độ ẩm không khí từ cảm biến IoT
Process	Vi điều khiển đọc dữ liệu, so sánh với ngưỡng cài đặt và quyết định tưới
Output	Bật/tắt máy bơm, đóng/mở van tưới, hiển thị trạng thái và ghi nhật ký

1.2. Sơ đồ phối hợp phần cứng
Cảm biến IoT
Nhiệt độ · Độ ẩm đất · Độ ẩm không khí

Vi điều khiển (ESP32)
Đọc dữ liệu · Xử lý ngưỡng · Ra quyết định

Mạch điều khiển và máy bơm
Điều khiển rơ-le · Van tưới · Hệ thống cấp nước

Người quản lý trang trại
Theo dõi trạng thái · Xem nhật ký · Điều chỉnh ngưỡng

Hình 1. Sơ đồ luồng hoạt động khái quát của Smart-Farm. Đây là sơ đồ minh họa bằng các khối giao diện.
Phối hợp phần cứng: cảm biến thu thập dữ liệu, ESP32 xử lý, mạch rơ-le điều khiển máy bơm và giao diện cung cấp thông tin cho người quản lý. Cần có cơ chế giới hạn thời gian tưới và ngắt bơm khi xảy ra lỗi để tránh cấp nước ngoài ý muốn.
1.3. Tích hợp SoC và DIKW
- SoC (System on a Chip): ESP32 tích hợp bộ xử lý và các ngoại vi cần thiết trên một chip, hỗ trợ giao tiếp với cảm biến và thiết bị điều khiển.
- DIKW: chuyển đổi dữ liệu thô thành thông tin, tri thức và hành động phù hợp.
- Fetch–Decode–Execute: CPU lần lượt lấy lệnh, giải mã lệnh và thực thi lệnh. Đây là chu trình xử lý lệnh của CPU, không phải toàn bộ quy trình điều khiển tưới.
It looks like image creation is temporarily unavailable. Do you want to try something else?
Image creation is temporarily unavailable because the Instant image-generation limit has been reached, and the Mini model is text-only.