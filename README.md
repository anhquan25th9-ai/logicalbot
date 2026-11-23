# Task 2 Logic Sparring — Build file .IPA qua GitHub Actions

## Cấu trúc dự án
- `www/index.html`: Toàn bộ giao diện và logic app (thuần CSS/JS, không phụ thuộc CDN nên chạy mượt trong iOS WebView).
- `.github/workflows/build-ipa.yml`: Script tự động build file `.ipa` trên máy ảo macOS của GitHub.
- `package.json` & `capacitor.config.json`: Cấu hình Capacitor 6 cho iOS.

## Cách build file `.ipa` (không cần máy Mac)
1. Tạo một repository mới trên GitHub (Public hoặc Private đều được).
2. Giải nén file `.zip` này và đẩy toàn bộ các file/thư mục bên trong (nhớ giữ nguyên thư mục ẩn `.github`) lên nhánh `main`.
3. Vào tab **Actions** trên GitHub → chọn workflow **Build Unsigned IPA** (nếu chưa tự chạy thì bấm **Run workflow**).
4. Chờ khoảng 4–5 phút để build xong, cuộn xuống mục **Artifacts** và tải file **`Task2Sparring-IPA`** về (giải nén sẽ ra `Task2Sparring-unsigned.ipa`).

## Cài lên iPhone không cần cáp
- Dùng **ESign** hoặc **Feather** trên iPhone, nhập file `Task2Sparring-unsigned.ipa` cùng chứng chỉ (`.p12` + `.mobileprovision`), bấm **Ký (Sign)** rồi **Cài đặt**.
- Mở app → bấm biểu tượng ⚙️ góc trên bên phải → dán **Gemini API Key** và chọn model `gemini-2.5-pro` để dùng ngay.
