# 🎓 IET Оюутны Портал

**IET Политехник Коллежийн** оюутны удирдлагын вэб систем — дүн, хуваарь, төлбөр, AI туслахтай.

---

## ✨ Боломжууд

| Боломж | Тайлбар |
|--------|---------|
| 🔐 Нэвтрэх | Gmail OTP, утасны SMS, банкны баталгаажуулалт |
| 📊 Дүн | Улирлын дүн, GPA, кредит харах, CSV/Excel экспорт |
| 📅 Хуваарь | 5 хоногийн цагийн хуваарь |
| 💰 Төлбөр | QPay QR код, Хаан банк, Төрийн банк |
| 🤖 AI Туслах | Claude AI — дүн тайлбар, GPA зөвлөгөө |
| 👤 Профайл | Оюутны дэлгэрэнгүй мэдээлэл |

---

## 📁 Файлын бүтэц

```
iet-portal/
├── server.js                  ← Node.js + Express backend
├── package.json
├── .env                       ← API key-нүүд (git-д оруулахгүй!)
├── .gitignore
└── public/
    └── iet-portal-ai.html     ← Frontend (AI туслахтай)
```

---

## ⚙️ Тохиргоо

### 1. Хамааралт суулгах

```bash
npm install
```

### 2. `.env` файл үүсгэх

```env
ANTHROPIC_API_KEY=sk-ant-xxxxxxxxxxxxxxxx
EMAILJS_PUBLIC_KEY=your_emailjs_public_key
EMAILJS_SERVICE_ID=service_xxxxxxx
EMAILJS_TEMPLATE_ID=template_xxxxxxx
FIREBASE_API_KEY=your_firebase_api_key
FIREBASE_PROJECT_ID=your_project_id
PORT=3000
```

### 3. Локал ажиллуулах

```bash
node server.js
# ✅ http://localhost:3000
```

---

## 🔑 API тохиргоо

### Anthropic (AI туслах)
1. [console.anthropic.com](https://console.anthropic.com) → API Keys → Create Key
2. `.env` дотор `ANTHROPIC_API_KEY=...` гэж бичнэ

### Firebase (OTP хадгалах)
1. [console.firebase.google.com](https://console.firebase.google.com) → Шинэ project
2. Firestore Database үүсгэнэ
3. Rules тохируулна:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{db}/documents {
    match /otp_codes/{doc} {
      allow read, write: if true;
    }
  }
}
```

### EmailJS (OTP майл)
1. [emailjs.com](https://emailjs.com) → Sign up (сард 200 майл үнэгүй)
2. Gmail сервис нэмнэ
3. Template үүсгэнэ — `{{otp_code}}`, `{{to_email}}` хувьсагч ашиглана

---

## 🚀 Vercel-д деплой хийх

```bash
npm install -g vercel
vercel login
vercel --prod
```

Vercel dashboard → Settings → Environment Variables → `.env`-ийн утгуудыг нэмнэ.

---

## 👤 Demo бүртгэлүүд

| Оюутны ID | Нууц үг | Нэр |
|-----------|---------|-----|
| IET2021001 | 1234 | Батжаргал Дорж |
| IET2022015 | 5678 | Оюунцэцэг Тогтох |
| IET2022108 | 8888 | Тэмүүлэн Мөнхөө |

---

## 🛠️ Технологи

- **Frontend:** HTML5, CSS3, Vanilla JavaScript
- **Backend:** Node.js, Express
- **Database:** Firebase Firestore (OTP)
- **AI:** Anthropic Claude Sonnet
- **Мэйл:** EmailJS
- **Төлбөр:** QPay, Khan Bank, State Bank

---

## 📄 Лиценз

IET Политехник Коллеж © 2024. Бүх эрх хуулиар хамгаалагдсан.
