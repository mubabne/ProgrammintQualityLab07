# Лаборатори 7 — Exploratory тест ба SBTM

Оюутан: Ч.Мөнхбаяр  
Код: B242270045  
Node.js: v24.11.1  
Браузер: Google Chrome 155.0.8059.80  
Үйлдлийн систем: Windows 11

Энэ репод багшийн өгсөн **Уншлагын жагсаалт v2.0** апп дээр хийсэн 60 минутын exploratory тестийн charter, session report, bug report болон нотолгоо багтсан. Аппын `app.js` файл нь багшийн материал тул репод оруулаагүй.

## Файлын бүтэц

- `charter.md` — session эхлэхээс өмнө гаргасан зорилго, аяллууд
- `session-report.md` — цаг тэмдэглэсэн түүхий ажиглалт ба цагийн задаргаа
- `bugs/` — дахин гаргах алхамтай алдааны тайлангууд
- `screenshots/` — UI согогийн зураг
- `evidence/` — API туршилтын бүтэн `curl -i` гаралт

## Олдсон согогууд

- [BUG-01](bugs/bug-01.md) · [BUG-02](bugs/bug-02.md) · [BUG-03](bugs/bug-03.md) · [BUG-04](bugs/bug-04.md)
- [BUG-05](bugs/bug-05.md) · [BUG-06](bugs/bug-06.md) · [BUG-07](bugs/bug-07.md) · [BUG-08](bugs/bug-08.md)
- [BUG-09](bugs/bug-09.md) · [BUG-10](bugs/bug-10.md) · [BUG-11](bugs/bug-11.md) · [BUG-12](bugs/bug-12.md)
- [BUG-13](bugs/bug-13.md) · [BUG-14](bugs/bug-14.md)

## Дүгнэлт

Supermodel аялал хамгийн үр дүнтэй байж, BUG-01, BUG-02, BUG-03, BUG-08, BUG-09, BUG-10, BUG-11, BUG-12-ыг илрүүлэв. Saboteur аяллаар BUG-04, BUG-05, BUG-06, BUG-07, BUG-13-ыг API болон хүчингүй оролтоор оллоо. Charter-аас гадуур Fed-Ex өгөгдлийн замаар тусгай тэмдэгтүүдийг entity болгож хадгалдаг BUG-14 илэрсэн. Хамгийн санаандгүй үр дүн нь `/old` линк 500 алдаа өгөх болон JSON `null` хүсэлт бүх серверийг унагаах явдал байв. Firefox болон бусад браузер, олон хэрэглэгчийн зэрэг хүсэлт, accessibility бүрэн шалгагдаагүй үлдсэн. Дараагийн session-ий charter эдгээр browser, concurrency, accessibility чиглэлийг хамарна. Playwright DOM assertion ашиглавал тоолуур, validation, давхардал, хайлт, эвдэрсэн линк, буруу мессеж, урт оролтын хэмжээг автомат тестээр барьж чадна. HTTP түвшний автомат тест malformed JSON, `null` хүсэлтийн crash болон буруу status code-ыг барина. Харин ногоон устгах товч, латин `x`, таслалтай он болон хүснэгтийн харааны эвдрэлийг хүний нүд эсвэл visual regression тестээр илрүүлэх нь илүү тохиромжтой.

