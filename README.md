# CƠM TẤM PRO - Layout Design Studio

Ứng dụng thiết kế layout quán cơm tấm với công cụ phân tích điểm số, so sánh, và export.

## 📋 Cấu trúc Thư Mục

```
project-root/
├── index.html          ← Trang chính (Vercel sẽ serve file này)
├── vercel.json         ← Cấu hình Vercel deployment
├── .gitignore
└── README.md
```

## 🚀 Cách Deploy lên Vercel

### Bước 1: Chuẩn bị Files
- ✅ `index.html` - file HTML chính
- ✅ `vercel.json` - cấu hình Vercel (đã có)

### Bước 2: Push lên Git
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/comtam-pro.git
git push -u origin main
```

### Bước 3: Deploy trên Vercel
1. Vào https://vercel.com
2. Click "Add New..." → "Project"
3. Import GitHub repository
4. Vercel sẽ tự detect `vercel.json` và build
5. Done! ✅

## ⚙️ Cấu hình vercel.json

```json
{
  "buildCommand": "exit 0",           // Không cần build, chỉ là static files
  "outputDirectory": ".",             // Output folder = root
  "cleanUrls": true,                  // Bỏ .html extension
  "trailingSlash": false
}
```

**Tại sao `exit 0`?**
- File HTML là static, không cần build process
- Vercel sẽ serve `index.html` trực tiếp

## 🔧 Nếu Vercel vẫn báo 404

1. **Kiểm tra Settings trong Vercel Dashboard:**
   - Project Settings → Build & Development
   - Output Directory: `.` (hoặc để trống)
   - Build Command: `exit 0`

2. **Hoặc dùng Vercel CLI:**
```bash
npm i -g vercel
vercel --prod
```

3. **Xóa `.vercel/` cache và redeploy:**
```bash
rm -rf .vercel/
git push origin main
```

## 📱 Sử dụng

1. Mở trang web
2. Chọn layout từ gallery
3. Xem điểm số & phân tích
4. So sánh layouts với nút "Compare"
5. Export hình PNG

---

**Ngôn ngữ:** Tiếng Việt  
**Công nghệ:** HTML + CSS + JavaScript (vanilla)  
**Responsive:** Yes (desktop + tablet)
