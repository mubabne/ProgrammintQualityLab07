# BUG-13: JSON null биетэй POST хүсэлт серверийг унагаана

Орчин: Уншлагын жагсаалт v2.0, curl 8.21.0, Node.js v24.11.1, Windows 11, 2026-10-20

Урьдчилсан нөхцөл: `node app.js`-ийг шинээр асаасан (анхны 3 ном).

## Дахин гаргах алхам

1. `body-null.json` файлд `null` гэж хадгална.
2. `curl.exe -i -X POST http://localhost:3000/api/books -H "Content-Type: application/json" --data-binary "@body-null.json"` ажиллуулна.
3. `http://localhost:3000` руу дахин холбогдоно.

Хүлээгдэж байсан: API `400 Bad Request` буцааж, сервер ажилласаар байна.

Бодит үр дүн: curl `Recv failure: Connection was reset` авна. Node.js процесс `TypeError: Cannot read properties of null` алдаагаар exit хийж, апп ажиллахаа болино.

Ноцтой байдал: **Critical** — нэг хүчингүй хүсэлт бүх хэрэглэгчийн серверийг бүрэн зогсооно.

Хавсралт: [curl гаралт](../evidence/bug-13-curl.txt) · [серверийн алдаа](../evidence/bug-13-server.txt)

Олдсон аялал: Saboteur (Seedy district)
