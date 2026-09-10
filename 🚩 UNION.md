## 🚩 `UNION`, `UNION ALL`
### `UNION` позволяет...
Объединить результаты нескольких `SELECT` в один результат, удаляя дубликаты.

Например: `SELECT name FROM students   UNION   SELECT name FROM teachers;`

### А `UNION ALL` сохраняет все строки...
Например: `SELECT name FROM students   UNION ALL   SELECT name FROM teachers;`

## ❗ Требования к `UNION`
Чтобы объединить два результата, количество столбцов должно совпадать.

✅ Правильно: `SELECT id, name FROM students   UNION   SELECT id, name FROM teachers;`

❌ Неправильно: `SELECT id, name FROM students   UNION   SELECT id, name, age FROM teachers;`

### Типы столбцов должны совпадать

❌ Неправильно: `SELECT id FROM students   UNION   SELECT name FROM teachers;`

Если `students.id` → `INTEGER`, а `teachers.name` → `TEXT`, то PostgreSQL не сможет без подходящего применения привести их к совместимому типу в обычном варианте.

### `UNION` - это объединение результатов, а не таблиц
Это очень важно, так как `SELECT ... UNION SELECT ... ;`  не означает: «Соединить две таблицы по ключу»

`JOIN` → объединяет связанные строки по условию.

`UNION` → складывает результаты выборки друг под другом.