## Test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
```sql
CREATE TABLE Employee(id SERIAL NOT NULL, name VARCHAR(50) NOT NULL, birthday DATE NOT NULL,email VARCHAR(100));
```

## Oluşturduğumuz employee tablosuna '[Mockaroo]'(https://www.mockaroo.com/) servisini kullanarak 50 adet veri ekleyelim.

## Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
```sql
UPDATE employee SET name = 'KEREM', email = 'kerem@gmail.com' WHERE id = 2; 
UPDATE employee SET name = 'KEREM', email = 'kerem@gmail.com' WHERE id = 3;
UPDATE employee SET name = 'KEREM', email = 'kerem@gmail.com' WHERE id = 4;
UPDATE employee SET name = 'KEREM', email = 'kerem@gmail.com' WHERE id = 5;
UPDATE employee SET name = 'KEREM', email = 'kerem@gmail.com' WHERE id = 1;
```

## Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
```sql
DELETE FROM employee WHERE id = 1;
DELETE FROM employee WHERE id = 2;
DELETE FROM employee WHERE id = 3;
DELETE FROM employee WHERE id = 4;
DELETE FROM employee WHERE id = 5;
```
