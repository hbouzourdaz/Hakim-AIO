from pathlib import Path
import re

src = Path("/mnt/data/README (1).md")
text = src.read_text(encoding="utf-8")

start = text.index("## ⬇️ تحميل مباشر")
end = text.index("## المميزات")

buttons = """## ⬇️ التحميل والروابط

<p align="center">
  <a href="https://github.com/hbouzourdaz/Hakim-AIO/releases/latest/download/Hakim_Bouzourdaz_PC_Care_AIO.cmd">
    <img alt="تحميل أحدث إصدار" src="https://img.shields.io/badge/⬇%20تحميل%20أحدث%20إصدار-2EA44F?style=for-the-badge&logo=windows&logoColor=white">
  </a>
  &nbsp;
  <a href="https://github.com/hbouzourdaz/Hakim-AIO/releases/latest">
    <img alt="صفحة الإصدارات" src="https://img.shields.io/badge/الإصدارات-Releases-2563EB?style=for-the-badge&logo=github&logoColor=white">
  </a>
  &nbsp;
  <a href="https://raw.githubusercontent.com/hbouzourdaz/Hakim-AIO/main/Hakim_Bouzourdaz_PC_Care_AIO.cmd">
    <img alt="تحميل من المصدر" src="https://img.shields.io/badge/عرض%20الملف%20المصدري-Raw-7C3AED?style=for-the-badge&logo=github&logoColor=white">
  </a>
</p>

> **ملاحظة:** رابط «تحميل أحدث إصدار» يعمل بعد نشر ملف `Hakim_Bouzourdaz_PC_Care_AIO.cmd` ضمن أصول GitHub Release. أما رابط Raw فيحمّل الملف من الفرع `main`.

"""
text = text[:start] + buttons + text[end:]

out = Path("/mnt/data/README_Buttons.md")
out.write_text(text, encoding="utf-8")
print(out)
