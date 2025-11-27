# คำแนะนำการลบไฟล์และคอมไพล์ใหม่

## ไฟล์ที่ต้องลบก่อนคอมไพล์ใหม่

ไฟล์ต่อไปนี้เป็นไฟล์ที่สร้างจากการคอมไพล์ LaTeX และควรลบก่อนคอมไพล์ใหม่:

1. **thesis.aux** - ไฟล์ auxiliary สำหรับ cross-references
2. **thesis.bbl** - ไฟล์ bibliography ที่สร้างจาก BibTeX
3. **thesis.blg** - ไฟล์ log จาก BibTeX
4. **thesis.lof** - List of Figures
5. **thesis.log** - ไฟล์ log จาก LaTeX
6. **thesis.lot** - List of Tables
7. **thesis.out** - ไฟล์สำหรับ hyperref
8. **thesis.toc** - Table of Contents
9. **thesis.synctex.gz** - ไฟล์สำหรับ SyncTeX (ถ้ามี)

## วิธีการลบและคอมไพล์ใหม่

### วิธีที่ 1: ใช้สคริปต์ PowerShell (แนะนำ)

1. เปิด PowerShell ในโฟลเดอร์โปรเจกต์
2. รันคำสั่ง:
   ```powershell
   .\clean.ps1
   ```
3. จากนั้นรันคำสั่งคอมไพล์:
   ```powershell
   xelatex thesis.tex
   bibtex thesis
   xelatex thesis.tex
   xelatex thesis.tex
   ```

### วิธีที่ 2: ใช้สคริปต์ Batch (Windows)

1. ดับเบิลคลิกที่ไฟล์ `compile.bat`
2. สคริปต์จะลบไฟล์เก่าและคอมไพล์ให้อัตโนมัติ

### วิธีที่ 3: ลบด้วยตนเอง

ลบไฟล์ต่อไปนี้ด้วยตนเอง:

- thesis.aux
- thesis.bbl
- thesis.blg
- thesis.lof
- thesis.log
- thesis.lot
- thesis.out
- thesis.toc

จากนั้นรันคำสั่ง:

```bash
xelatex thesis.tex
bibtex thesis
xelatex thesis.tex
xelatex thesis.tex
```

## คำสั่งคอมไพล์แบบเต็ม

สำหรับการคอมไพล์ที่สมบูรณ์ (รวม bibliography):

```bash
xelatex thesis.tex
bibtex thesis
xelatex thesis.tex
xelatex thesis.tex
```

**หมายเหตุ:** ต้องรัน xelatex 3 ครั้งเพื่อให้ cross-references และ bibliography ถูกต้อง

## คำสั่งคอมไพล์แบบเร็ว (ไม่รวม bibliography)

ถ้าไม่มีการเปลี่ยนแปลง bibliography:

```bash
xelatex thesis.tex
xelatex thesis.tex
```
