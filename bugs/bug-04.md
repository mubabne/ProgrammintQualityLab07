# BUG-04: Буруу JSON-той POST хүсэлт 200 OK буцаана

Орчин: Уншлагын жагсаалт v2.0, curl 8.21.0, Windows 11, 2026-10-20

Урьдчилсан нөхцөл: `node app.js`-ийг шинээр асаасан (анхны 3 ном).

## Дахин гаргах алхам

1. `body-invalid.json` файлд `not-json` гэж хадгална.
2. `curl.exe -i -X POST http://localhost:3000/api/books -H "Content-Type: application/json" --data-binary "@body-invalid.json"` ажиллуулна.

Хүлээгдэж байсан: Буруу JSON биетэй хүсэлтэд `400 Bad Request` буцна.

Бодит үр дүн: `HTTP/1.1 200 OK` болон `{"result":"OK"}` буцна.

Ноцтой байдал: **Major** — API хүчингүй хүсэлтийг амжилттай мэт мэдээлж байна.

Хавсралт: [evidence/bug-04-curl.txt](../evidence/bug-04-curl.txt)

Олдсон аялал: Saboteur (Seedy district)
