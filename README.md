# MFU Clinical Tools

เครื่องมือประเมินทางคลินิก Mae Fah Luang University — static web app, ไม่มี backend, เปิดได้ทันทีจาก browser หรือ GitHub Pages

## เครื่องมือปัจจุบัน

| เมนู | ไฟล์ | คำอธิบาย |
|------|------|-----------|
| VTE Prophylaxis | `mfu-vte-prophylaxis.html` | Caprini RAM calculator, bleeding risk, contraindications, drug choice & duration, documentation |

---

## วิธี deploy ขึ้น GitHub Pages

### ขั้นตอนครั้งแรก (ทำครั้งเดียว)

**1. สร้าง GitHub account** (ถ้ายังไม่มี)
- ไปที่ https://github.com → Sign up

**2. สร้าง repository ใหม่**
- กดปุ่ม **+** (มุมบนขวา) → **New repository**
- Repository name: `mfu-clinical-tools`
- ตั้งเป็น **Public**
- ไม่ต้อง tick Add README (เรามีอยู่แล้ว)
- กด **Create repository**

**3. ติดตั้ง Git** (ถ้ายังไม่มี)
- ดาวน์โหลดที่ https://git-scm.com/download/win → ติดตั้งตาม default

**4. Push ไฟล์ขึ้น GitHub**

เปิด Command Prompt หรือ PowerShell แล้วรันคำสั่งต่อไปนี้ทีละบรรทัด:

```bash
cd "C:\Users\USER69\Documents\mfu-clinical-tools"

git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/mfu-clinical-tools.git
git push -u origin main
```

> แทน `YOUR_USERNAME` ด้วย GitHub username ของคุณ

**5. เปิด GitHub Pages**
- ไปที่ repo บน GitHub → **Settings** → **Pages** (เมนูซ้าย)
- Source: **Deploy from a branch**
- Branch: **main** / **(root)**
- กด **Save**

**6. รอประมาณ 1–2 นาที** แล้วเข้าใช้งานที่:
```
https://YOUR_USERNAME.github.io/mfu-clinical-tools/
```

---

## วิธีอัปเดตไฟล์ (ครั้งต่อไป)

หลังแก้ไขไฟล์ HTML แล้ว รันคำสั่ง:

```bash
cd "C:\Users\USER69\Documents\mfu-clinical-tools"

git add .
git commit -m "อธิบายสิ่งที่แก้ไข"
git push
```

GitHub Pages จะอัปเดตอัตโนมัติภายใน 1–2 นาที

---

## วิธีเพิ่มเมนูใหม่

1. วางไฟล์ HTML ของ tool ใหม่ไว้ใน folder นี้
2. เปิด `index.html` และเพิ่มบรรทัดใน `<ul class="menu">`:

```html
<li class="menu-item" data-src="ชื่อไฟล์ใหม่.html">ชื่อเมนู</li>
```

3. Push ขึ้น GitHub ตามขั้นตอนด้านบน

---

## โครงสร้างไฟล์

```
mfu-clinical-tools/
├── index.html                  ← shell หลัก (sidebar + iframe)
├── mfu-vte-prophylaxis.html    ← VTE Prophylaxis tool
└── README.md                   ← ไฟล์นี้
```
