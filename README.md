# Lab: Clean Code & Specifications 

**01418211 Software Construction — Week 2**

แลปนี้มี 2 ส่วน:
- **ส่วน A** — เขียนโค้ดให้ผ่านเทสต์ (implement) — ตรวจอัตโนมัติ
- **ส่วน B** — ฝึกเขียน spec (JavaDoc) เอง จากโค้ดที่ให้มา — ผู้สอนตรวจ

แก้ไฟล์ในโฟลเดอร์ `starter/` (มี `// TODO` กำกับ)

## รัน (ตรวจส่วน A)

1. เปิดโฟลเดอร์ `starter` ใน VSCode (ต้องติดตั้ง "Extension Pack for Java")
2. เปิดไฟล์ `src/lab/TestRunner.java`
3. กดปุ่ม Run ▶ ที่มุมขวาบน (หรือกด `Run` เหนือเมธอด main)

> โปรเจกต์ตั้งค่า `-ea` (เปิด assertions) ให้อัตโนมัติแล้วผ่านไฟล์ `.vscode/settings.json`
> จึงกด Run ได้เลย ไม่ต้องพิมพ์คำสั่งอะไรเพิ่ม

ทำส่วน A ครบจะได้ `Part A: PASS 13 / FAIL 0`

---

## ส่วน A — Implement (3 ข้อ)

**ข้อ 1 · `StringUtils.countVowels(String text)`** — Naming + Pure Function
นับสระ a,e,i,o,u (พิมพ์เล็ก/ใหญ่). ใช้ตัวแปร local เท่านั้น. `null` → throw `IllegalArgumentException`

**ข้อ 2 · `Payment.canCharge(User u)`** — Guard Clause
เขียนแบบ return เร็ว แทน if ซ้อน. เก็บเงินได้เมื่อ `u != null` และ `u.active` และ `u.balance > 0`

**ข้อ 3 · `BankAccount.withdraw(int amount)`** — Assertion vs Exception
- `amount <= 0` → throw `IllegalArgumentException` (input ภายนอก = exception)
- `assert amount <= balance` (เงื่อนไขภายใน = assert)
- หลังถอน `balance` ลดลงเท่ากับ `amount`

---

## ส่วน B — เขียน Spec เอง (3 ข้อ)

เปิดไฟล์ `Specs.java` — โค้ดทำงานถูกต้องแล้ว **ห้ามแก้โค้ด**
หน้าที่คือเติม **JavaDoc** ให้ 3 เมธอด: `firstIndexOf`, `circleArea`, `normalize`

JavaDoc แต่ละเมธอดต้องมีครบ 4 อย่าง:
1. บรรทัดสรุปว่าเมธอด **ทำอะไร** (what ไม่ใช่ how)
2. `@param` ของทุกพารามิเตอร์ + **ข้อจำกัด** (pre-condition)
3. `@return` อธิบายค่าที่คืน (post-condition)
4. `@throws` ทุก exception ที่โยน + เงื่อนไข

> อ่านโค้ดในเมธอดให้เข้าใจก่อน แล้วค่อยเขียน spec เช่น เมธอดที่ `throw` เมื่อ input null → ต้องมี `@throws` บอกเงื่อนไขนั้น

---
