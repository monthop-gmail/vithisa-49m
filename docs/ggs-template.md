# GGS Template — คอลัมน์สำหรับ Google Sheet

> สำหรับ อ.เต้ สร้าง Google Sheet ตาม template นี้
>
> แต่ละสาขาจะมี 1 Google Sheet มี 3 sheets ด้านล่าง
>
> **สำคัญ:** ต้องแชร์เป็น "Anyone with the link" เพื่อให้ระบบดึงข้อมูลได้

---

## Sheet 1: organizations — ลงทะเบียนองค์กร

สาขากรอกเมื่อมีองค์กรมาลงทะเบียน

| คอลัมน์ | ชื่อใน Sheet | ตัวอย่าง | จำเป็น |
|---------|-------------|---------|--------|
| A | id | ORG001 | ✅ |
| B | name | โรงเรียนสาธิต มศว | ✅ |
| C | org_type | โรงเรียน | |
| D | branch_id | B001 | ✅ |
| E | sub_district | คลองเตย | |
| F | district | คลองเตย | |
| G | province | กรุงเทพมหานคร | |
| H | email | school@example.com | |
| I | max_participants | 500 | |
| J | gender_male | 200 | |
| K | gender_female | 280 | |
| L | gender_unspecified | 20 | |
| M | contact_name | ครูสมใจ | |
| N | contact_phone | 081-xxx-xxxx | |
| O | contact_line_id | @teacher | |
| P | enrolled_date | 2026-05-01 | |
| Q | enrolled_until | 2026-07-31 | |

> **org_type ที่รองรับ:** โรงเรียน, มหาวิทยาลัย, วัด, หน่วยงาน, ชุมชน

---

## Sheet 2: participants — ลงทะเบียนรายคน

สาขากรอกเมื่อมีบุคคลมาสมัคร

| คอลัมน์ | ชื่อใน Sheet | ตัวอย่าง | จำเป็น |
|---------|-------------|---------|--------|
| A | branch_id | B001 | ✅ |
| B | prefix | นาย | |
| C | first_name | สมชาย | ✅ |
| D | last_name | ใจดี | ✅ |
| E | gender | ชาย | |
| F | age | 30 | |
| G | sub_district | คลองเตย | |
| H | district | คลองเตย | |
| I | province | กรุงเทพมหานคร | |
| J | phone | 081-xxx-xxxx | |
| K | line_id | @somchai | |
| L | enrolled_date | 2026-05-01 | |

> **เพศที่รองรับ:** ชาย, หญิง, ไม่ระบุ
>
> **คำนำหน้าที่รองรับ:** นาย, นาง, นางสาว, เด็กชาย, เด็กหญิง

---

## Sheet 3: records — บันทึกนาทีรายวัน

สาขากรอกทุกวันที่มีการปฏิบัติ

### แบบกลุ่ม (องค์กร)

| คอลัมน์ | ชื่อใน Sheet | ตัวอย่าง | จำเป็น |
|---------|-------------|---------|--------|
| A | type | bulk | ✅ |
| B | branch_id | B001 | ✅ |
| C | name | โรงเรียนสาธิต มศว | ✅ |
| D | org_id | ORG001 | |
| E | date | 2026-05-15 | ✅ |
| F | morning_male | 120 | |
| G | morning_female | 150 | |
| H | morning_unspecified | 10 | |
| I | afternoon_male | 80 | |
| J | afternoon_female | 100 | |
| K | afternoon_unspecified | 5 | |
| L | evening_male | 50 | |
| M | evening_female | 70 | |
| N | evening_unspecified | 5 | |
| O | submitted_by | ครูสมใจ | |
| P | submitted_phone | 081-xxx-xxxx | |

> **minutes** จะถูกคำนวณอัตโนมัติ = (รวมคนทุกรอบ) × 5
>
> **participant_count** จะถูกคำนวณอัตโนมัติ = จำนวนคนสูงสุดในรอบใดรอบหนึ่ง

### แบบรายคน

| คอลัมน์ | ชื่อใน Sheet | ตัวอย่าง | จำเป็น |
|---------|-------------|---------|--------|
| A | type | individual | ✅ |
| B | branch_id | B001 | ✅ |
| C | name | สมชาย ใจดี | ✅ |
| D | date | 2026-05-15 | ✅ |
| E | morning | 1 | |
| F | afternoon | 1 | |
| G | evening | 0 | |

> **morning/afternoon/evening:** 1 = ปฏิบัติ, 0 = ไม่ปฏิบัติ
>
> **minutes** จะถูกคำนวณอัตโนมัติ = จำนวนรอบ × 5

---

## วิธีแชร์ Google Sheet

1. เปิด Google Sheet
2. กด **Share** (แชร์)
3. เลือก **Anyone with the link** (ทุกคนที่มีลิงก์)
4. สิทธิ์: **Viewer** (ผู้ดู)
5. คัดลอก URL มาให้ระบบ

**URL format:** `https://docs.google.com/spreadsheets/d/XXXXXXXXX/edit`

ระบบจะดึงข้อมูลจาก Sheet อัตโนมัติ

---

> สถานะ: **พร้อมใช้** — อ.เต้ สร้าง GGS ตาม template นี้ได้เลย
