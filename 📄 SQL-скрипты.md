## 📄 SQL-скрипты
### SQL-скрипт - это...
Обычный текстовый файл, содержащий SQL-команды. 

Например, `schema.sql` может содержать:

    CREATE TABLE users (
        id SERIAL PRIMARY KEY,
        username VARCHAR(50) NOT NULL
    );
## 📚 Почему разбивать SQL на несколько файлов
### Можно написать огромный: `database.sql`
Но постепенно он превратится в 2000 строк SQL, где в перемешку хранятся:

    CREATE DATABASE
    CREATE TABLE
    INSERT 
    CREATE INDEX
    SELECT
    UPDATE

Разделение делает проект понятнее. Например:

    schema/
    структура БД

    data/
    тестовые данные
    
    queries/
    запросы
## 📋 Порядок выполнения SQL
Условно:

    создание БД
        ↓
    создание схем
        ↓
    создание таблиц
        ↓
    PRIMARY KEY
        ↓
    FOREIGN KEY
        ↓
    CHECK / UNIQUE / NOT NULL
        ↓
    индексы
        ↓
    тестовые данные