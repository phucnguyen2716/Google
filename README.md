# ASP.NET Core Google Authentication Project

Dự án này sử dụng ASP.NET Core Identity và Google OAuth 2.0 để xác thực người dùng.

## 🛠 Yêu cầu hệ thống
* .NET SDK (phiên bản bạn đang dùng, ví dụ 6.0/7.0/8.0)
* SQL Server (LocalDB)
* Tài khoản Google Cloud Console

## 🚀 Hướng dẫn cài đặt

### 1. Cấu hình Google Cloud Console
1. Truy cập [Google Cloud Console](https://console.cloud.google.com/).
2. Tạo một Project mới (Lưu ý: Không đặt tên chứa từ "Google" để tránh lỗi "Abusive").
3. Thiết lập **OAuth Consent Screen**.
4. Tại mục **Credentials**, tạo **OAuth 2.0 Client ID** loại **Web Application**.
5. Thêm URI điều hướng sau vào mục **Authorized redirect URIs**:
   - `https://localhost:44363/signin-google`
6. Lưu lại **Client ID** và **Client Secret**.

### 2. Cấu hình ứng dụng
Mở file `appsettings.json` và cập nhật thông tin bảo mật của bạn:

```json
"Authentication": {
  "Google": {
    "ClientId": "YOUR_CLIENT_ID_HERE",
    "ClientSecret": "YOUR_CLIENT_SECRET_HERE"
  }
}
