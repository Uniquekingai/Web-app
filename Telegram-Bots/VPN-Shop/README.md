<div dir="rtl" align="right">

<p align="center">
  <img src="https://img.shields.io/badge/UniqueKingAI-VPN%20Shop%20Bot-6366f1?style=for-the-badge&logo=telegram&logoColor=white" alt="UniqueKingAI VPN Shop Bot">
</p>

<p align="center">
  <a href="#فارسی">🇮🇷 فارسی</a> &nbsp;|&nbsp; <a href="#english">🇬🇧 English</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-18+-339933?style=flat-square&logo=node.js&logoColor=white">
  <img src="https://img.shields.io/badge/Telegram-Web%20App-26A5E4?style=flat-square&logo=telegram&logoColor=white">
  <img src="https://img.shields.io/badge/SQLite-Database-003B57?style=flat-square&logo=sqlite&logoColor=white">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square">
  <img src="https://img.shields.io/badge/Made%20by-UniqueKingAI-6366f1?style=flat-square">
</p>

---

<h1 id="فارسی">🇮🇷 مستندات فارسی</h1>

## 🔐 ربات فروشگاه VPN — تلگرام وب اپ

ربات تلگرام وب اپ برای فروش کانفیگ‌های V2Ray و اکانت VPN با پنل مدیریت کامل، کیف پول کاربری و سیستم سفارش‌گیری خودکار.

---

## ✨ ویژگی‌ها

### 🛒 فروشگاه
| ویژگی | توضیح |
|-------|-------|
| 🌐 کانفیگ مولتی | کانفیگ چندپروتکلی V2Ray با انتخاب حجم |
| 🔒 کانفیگ آی‌پی استاتیک | کانفیگ با آدرس IP اختصاصی |
| 🛸 کانفیگ استارلینک | کانفیگ فوق سریع از طریق شبکه استارلینک |
| ⚡ اکانت اکسپرس VPN | پلن‌های ۱، ۳، ۶ و ۱۲ ماهه |

### 💰 کیف پول
- موجودی اختصاصی برای هر کاربر
- درخواست شارژ از طریق ربات
- نوتیفیکیشن خودکار به کاربر پس از شارژ

### ⚙️ پنل مدیریت
- مشاهده تمام کاربران و موجودی
- شارژ دستی کیف پول هر کاربر
- مدیریت سفارشات و ارسال کانفیگ
- ویرایش قیمت هر نوع کانفیگ به صورت مستقل

---

## 📂 ساختار پروژه

```
vpn-shop-bot/
├── backend/
│   ├── bot.js              # هسته اصلی ربات + API
│   └── database.js         # مدیریت دیتابیس SQLite
├── frontend/
│   └── index.html          # Telegram Web App UI
├── docs/
│   └── nginx.conf          # تنظیمات Nginx
├── data/                   # دیتابیس (ساخته می‌شود)
├── .env.example            # نمونه متغیرهای محیطی
├── ecosystem.config.js     # تنظیمات PM2
└── package.json
```

---

## 🚀 نصب و راه‌اندازی

### پیش‌نیازها
- Node.js نسخه ۱۸ یا بالاتر
- سرور لینوکس با IP ثابت
- دامنه با SSL (برای Web App تلگرام ضروری است)

### مراحل نصب

**۱. کلون پروژه**
```bash
git clone https://github.com/UniqueKingAI/vpn-shop-bot.git
cd vpn-shop-bot
npm install
```

**۲. ایجاد ربات در تلگرام**
- به `@BotFather` پیام دهید
- دستور `/newbot` را بزنید
- نام و یوزرنیم ربات را تعیین کنید
- توکن دریافتی را کپی کنید

**۳. تنظیم Web App**
- در `@BotFather` دستور `/newapp` یا `/mybots` را بزنید
- آدرس دامنه‌تان را به عنوان Web App URL تنظیم کنید

**۴. تنظیم فایل محیطی**
```bash
cp .env.example .env
nano .env
```

```env
BOT_TOKEN=توکن_ربات_شما
ADMIN_IDS=آیدی_تلگرام_ادمین
WEB_APP_URL=https://your-domain.com
BOT_USERNAME=YourBotUsername
```

**۵. آپلود فرانت‌اند**
```bash
# کپی فایل index.html به پوشه وب سرور
cp frontend/index.html /var/www/vpn-shop-bot/frontend/
```

**۶. اجرا**
```bash
# با PM2 (توصیه‌شده برای production)
npm install -g pm2
pm2 start ecosystem.config.js
pm2 save
pm2 startup

# یا مستقیم
npm start
```

---

## ⚙️ تنظیم قیمت‌ها

قیمت‌ها از طریق **پنل مدیریت** (تب «قیمت‌ها») قابل ویرایش هستند.

| محصول | حجم/دوره | قیمت پیش‌فرض |
|-------|---------|--------------|
| کانفیگ مولتی | ۱۰ گیگ | ۲۵,۰۰۰ تومان |
| کانفیگ مولتی | ۲۰ گیگ | ۴۵,۰۰۰ تومان |
| کانفیگ مولتی | ۵۰ گیگ | ۹۰,۰۰۰ تومان |
| آی‌پی استاتیک | ۱۰ گیگ | ۳۵,۰۰۰ تومان |
| استارلینک | ۱۰ گیگ | ۵۵,۰۰۰ تومان |
| اکسپرس VPN | ۱ ماهه | ۱۲۰,۰۰۰ تومان |
| اکسپرس VPN | ۳ ماهه | ۳۲۰,۰۰۰ تومان |
| اکسپرس VPN | ۶ ماهه | ۵۸۰,۰۰۰ تومان |
| اکسپرس VPN | ۱۲ ماهه | ۹۹۰,۰۰۰ تومان |

---

## 🔄 جریان کاری

```
کاربر /start → ثبت در دیتابیس → باز شدن Web App
    ↓
انتخاب محصول → انتخاب حجم/دوره → افزودن به سبد
    ↓
بررسی موجودی → ثبت سفارش → کسر از کیف پول
    ↓
اطلاع‌رسانی به ادمین → ارسال کانفیگ توسط ادمین
    ↓
ارسال کانفیگ به کاربر از طریق پیام تلگرام
```

---

## 🛡️ امنیت

- ادمین ID در متغیرهای محیطی ذخیره می‌شود
- تمام API‌های ادمین نیاز به هدر `x-admin-id` دارند
- دیتابیس SQLite به صورت محلی ذخیره می‌شود
- WAL mode برای عملکرد بهتر فعال است

---

</div>

---

<h1 id="english">🇬🇧 English Documentation</h1>

## 🔐 VPN Shop — Telegram Web App Bot

A full-featured Telegram Web App bot for selling V2Ray configs and VPN accounts, with a complete admin panel, user wallet system, and automated order management.

---

## ✨ Features

### 🛒 Shop
| Feature | Description |
|---------|-------------|
| 🌐 Multi Config | Multi-protocol V2Ray config with volume selection |
| 🔒 Static IP Config | Dedicated static IP V2Ray config |
| 🛸 Starlink Config | Ultra-fast config routed through Starlink |
| ⚡ ExpressVPN Account | 1, 3, 6, and 12-month subscription plans |

### 💰 Wallet
- Individual balance per user
- Charge requests via bot
- Auto-notification on balance update

### ⚙️ Admin Panel
- View all users and balances
- Manually charge any user's wallet
- Manage orders and send configs
- Edit prices for each product variant independently

---

## 📂 Project Structure

```
vpn-shop-bot/
├── backend/
│   ├── bot.js              # Core bot logic + REST API
│   └── database.js         # SQLite database layer
├── frontend/
│   └── index.html          # Telegram Web App UI (glassmorphism)
├── docs/
│   └── nginx.conf          # Nginx reverse proxy config
├── data/                   # Auto-created database directory
├── .env.example            # Environment variable template
├── ecosystem.config.js     # PM2 process config
└── package.json
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Bot Framework | Telegraf.js v4 |
| Web Server | Express.js |
| Database | SQLite (better-sqlite3) |
| Frontend | Vanilla JS + CSS (no build step) |
| Process Manager | PM2 |
| Web Server | Nginx |
| Fonts | Vazirmatn, Syne (Google Fonts) |

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Linux VPS with static IP
- Domain with valid SSL (required for Telegram Web Apps)

### Installation

**1. Clone & Install**
```bash
git clone https://github.com/UniqueKingAI/vpn-shop-bot.git
cd vpn-shop-bot
npm install
```

**2. Create your Telegram Bot**
- Message `@BotFather`
- `/newbot` → set name and username
- Copy your bot token

**3. Set up Web App URL in BotFather**
- `/mybots` → select your bot → Bot Settings → Menu Button
- Set the Web App URL to your domain

**4. Configure environment**
```bash
cp .env.example .env
```

Edit `.env`:
```env
BOT_TOKEN=your_bot_token
ADMIN_IDS=your_telegram_user_id
WEB_APP_URL=https://your-domain.com
BOT_USERNAME=YourBotUsername
```

**5. Deploy frontend**
```bash
cp frontend/index.html /var/www/vpn-shop-bot/frontend/
```

**6. Configure Nginx**
```bash
cp docs/nginx.conf /etc/nginx/sites-available/vpn-shop-bot
ln -s /etc/nginx/sites-available/vpn-shop-bot /etc/nginx/sites-enabled/
certbot --nginx -d your-domain.com
nginx -t && systemctl reload nginx
```

**7. Start with PM2**
```bash
npm install -g pm2
pm2 start ecosystem.config.js
pm2 save && pm2 startup
```

---

## 📡 API Endpoints

| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| GET | `/api/products` | None | List all products with prices |
| GET | `/api/user/:id` | None | Get user info & balance |
| POST | `/api/order` | None | Place an order |
| GET | `/api/admin/users` | Admin | List all users |
| POST | `/api/admin/balance` | Admin | Add balance to user |
| GET | `/api/admin/orders` | Admin | List all orders |
| PUT | `/api/admin/orders/:id` | Admin | Update order + send config |
| PUT | `/api/admin/products/:id` | Admin | Update product prices |
| GET | `/api/admin/charge-requests` | Admin | List charge requests |

---

## 🔄 User Flow

```
User /start → Registered in DB → Web App opens
    ↓
Select product → Select volume/plan → Add to cart
    ↓
Check balance → Place order → Deduct from wallet
    ↓
Admin notified → Admin sends config via panel
    ↓
User receives config via Telegram message
```

---

## 💡 Admin Workflow

1. User requests wallet charge via bot
2. Admin receives notification with Approve/Reject buttons
3. On approval, user's balance is updated automatically
4. User places order; admin receives notification
5. Admin opens panel → Orders tab → enters config → confirms
6. Config is automatically sent to user via bot message

---

## 📄 License

MIT License — © 2024 [UniqueKingAI](https://uniquekingai.com)

---

<p align="center">
  Made with ❤️ by <a href="https://uniquekingai.com">UniqueKingAI</a>
</p>
