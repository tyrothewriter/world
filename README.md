# กระดานราคาตลาดโลก

หน้าเว็บแสดงดัชนีหุ้น (ไทย ญี่ปุ่น ฮ่องกง สิงคโปร์ อินเดีย อินโดนีเซีย ฟิลิปปินส์ มาเลเซีย ออสเตรเลีย อังกฤษ ฝรั่งเศส เยอรมนี อิตาลี สหรัฐฯ),
Dow/S&P/Nasdaq Futures, ทองโลก, ทองไทย, น้ำมัน WTI/Brent และ Baltic Dry Index

## วิธีใช้
1. สร้าง repo ใหม่บน GitHub แล้วอัปโหลดไฟล์ทั้งหมดในโฟลเดอร์นี้
2. Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / `(root)`
3. Settings → Actions → General → Workflow permissions: เลือก `Read and write permissions`
4. แท็บ Actions → `update-market-data` → Run workflow (ครั้งแรก) หลังจากนั้นรันเองทุก 30 นาที
5. เปิดเว็บที่ `https://<ชื่อผู้ใช้>.github.io/<ชื่อ repo>/`

ทดลองในเครื่อง: `pip install -r requirements.txt && python scripts/update_data.py && python -m http.server`

## หมายเหตุ
- ข้อมูลจาก Yahoo Finance (ผ่าน yfinance) ไม่ใช่ข้อมูลเรียลไทม์ และเป็นข้อมูลเพื่อประกอบการดูเท่านั้น
- Baltic Dry Index (`^BDI`) บน Yahoo ไม่เสถียร ถ้าขึ้น "ไม่มีข้อมูล" ให้เปลี่ยนแหล่งใน `scripts/update_data.py`
- ราคาทองไทยมาจาก API ชุมชน `api.chnwt.dev` ถ้าล่มจะแสดงเฉพาะราคาคำนวณจากทองโลก
- เพิ่ม/ลดตลาดได้ที่ลิสต์ `GROUPS` ในไฟล์ `scripts/update_data.py`

## โลโก้และไอคอน
ไอคอนอยู่ใน `assets/` (favicon, apple-touch-icon 180px, PWA 192/512px) ถ้าจะเปลี่ยนโลโก้ ให้แทนที่ไฟล์เหล่านี้ด้วยชื่อเดิม

**เซฟลงหน้าจอโฮม iPhone:** เปิดเว็บใน Safari → ปุ่มแชร์ → เพิ่มไปยังหน้าจอโฮม (ถ้าเคยเพิ่มไว้ก่อนเปลี่ยนไอคอน ให้ลบแล้วเพิ่มใหม่)
