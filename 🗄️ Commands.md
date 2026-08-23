## 🗃️ Команды PostgreSQL
### 🆕 `CREATE` - создание новых объектов.
- 📦 `CREATE DATABASE` - создание базы данных: `CREATE DATABASE base;`
- 📋 `CREATE TABLE` - создание таблицы: `CREATE TABLE users ( id SERIAL4 PRIMARY KEY );`
___
### 🏗️ `ALTER TABLE` - изменение структуры существующей таблицы.
- ➕ `ADD COLUMN` - Добавить колонку: `ALTER TABLE users ADD COLUMN user_id;`
- ❌ `DROP COLUMN` - Удалить колонку: `ALTER TABLE users DROP COLUMN user_id;`
- 🧩 `ALTER COLUMN` - Изменить тип данных колонки: `ALTER TABLE users ALTER COLUMN username TYPE VARCHAR(150);`
- ✏️ `RENAME COLUMN` - Переименовать колонку: `ALTER TABLE users RENAME COLUMN mail TO email;`
- 🖋️ `RENAME TO` - Переименовать таблицу: `ALTER TABLE user RENAME TO users;`
___
### ❌ `DROP` - удаление объектов.
- 📦 `DROP DATABASE` - удаление базы данных: `DROP DATABASE base;`
- 📋 `DROP TABLE` - удаление таблицы: `DROP TABLE users;`
___
### ➕ `INSERT ` - добавление строк в таблицу.
- 📥 `INTO` - указание таблицы и колонок, куда пойдут данные: `INSERT INTO users (username, password) ...`
- 🔹 `VALUES` - блок с конкретными значениями для вставки: `INSERT INTO users (username, password) VALUES ('user', '123');`
___
### 🔄 `UPDATE` - обновление (изменение) существующих строк в таблице.
- `SET` - колонки и новые значения: `UPDATE users SET status = 'active', last_login = NOW();`
- `WHERE` - фильтр, определяющий, какие строки подлежат изменению: `UPDATE users SET status = 'active' WHERE id = 1;`
___
### 🗑️ `DELETE` - удаление существующих строк в таблице.
- 🔗 `FROM` - указание таблицы, из которой нужно удалить строки: `DELETE FROM users;`
- 🎯 `WHERE` - фильтр, определяющий, какие строки подлежат удалению: `DELETE FROM users WHERE id = 1;`
___
### 🔎 `SELECT` - выборка строк.
- 🔗 `FROM` - указание таблицы, откуда берутся данные: `SELECT * FROM users;`
- 🎯 `WHERE` - фильтр, до группировки: `SELECT * FROM users WHERE isVerify = true;`
- - ↔️ `BETWEEN` - диапазон: `WHERE balance BETWEEN 50000 AND 80000 ...`
- - 📝 `LIKE` - выбор по шаблону: `WHERE username LIKE 'And%' ...`
- - 📋 `IN` - выбор из списка: `WHERE username IN ('Andrey', 'Anton', 'David') ...`
- - ➕ `AND` - И: `WHERE balance = 10000 AND name = 'Andrey' ...`
- - 🔀 `OR` - ИЛИ: `WHERE isVerify = true OR balance > 50000 ...`
- - 🔍 `IS` - является ли: `WHERE username IS NULL...`
- - 🔁`NOT` - переворачивает условие: `WHERE username IS NOT NULL ...`
- ↕️ `ORDER BY` - сортировка: `SELECT * FROM users ORDER BY balance DESC;`
- ✂️ `OFFSET` - сколько строк пропустить: `SELECT * FROM users OFFSET 2;`
- 📐 `LIMIT` - лимит выводимых строк: `SELECT * FROM users LIMIT 3;`
- 🗂️ `GROUP BY` - группировка строк: `SELECT category FROM users GROUP BY category;`
- 🚦 `HAVING` - фильтрация, после группировки: `SELECT category FROM users GROUP BY category HAVING AVG(balance) > 10000;`
___
### ⛓️ `JOIN` - объединение строк из двух и более таблиц на основе общего поля.
- 🔸 `ON` - условия связывания: `... JOIN statuses ON user.status = statuses.id ...`
- 🔗 `INNER JOIN` - пересечение (только те строки, которые есть в обеих таблицах): `... INNER JOIN statuses ON user.status = statuses.id ...`
- ⬅️ `LEFT JOIN` - упор на левую таблицу (все строки из левой таблицы и совпадения из правой): `... LEFT JOIN statuses ON user.status = statuses.id ...`
- ➡️ `RIGHT JOIN` - упор на правую таблицу (все строки из правой таблицы и совпадения из левой): `... RIGHT JOIN statuses ON user.status = statuses.id ...`
- 🌐 `FULL JOIN` - полное объединение: `... FULL JOIN statuses ON user.status = statuses.id ...`