# MiniDB 📦

MiniDB — це легка та гнучка in-memory база даних, написана на Python. Вона дозволяє створювати таблиці, вставляти дані, виконувати запити та з'єднувати таблиці без використання зовнішньої СУБД.

## ⚡ Основні можливості:

✔️ **Гнучка типізація**: підтримка `IntegerType`, `StringType`, `BooleanType`, `DateType`
✔️ **Модель бази даних**: `Column`, `Row`, `Table`, `Database`
✔️ **Запити до таблиць**: `SimpleQuery` з підтримкою фільтрації, агрегації та сортування
✔️ **Операції з даними**: додавання, оновлення, видалення та пошук рядків
✔️ **Збереження та завантаження** даних у форматі JSON
✔️ **Об'єднання таблиць** (`JoinedTable`)

---

## 🚀 Встановлення

### 1️⃣ Клонування репозиторію:

git clone https://github.com/yourusername/minidb.git
cd minidb
2️⃣ Створення та активація віртуального середовища:
sh
Copy
Edit
python -m venv .venv
source .venv/bin/activate  # Linux/macOS
.venv\Scripts\activate     # Windows
3️⃣ Встановлення залежностей:

pip install -r requirements.txt
🛠 Використання

### 📌 1. Створення таблиці та додавання даних:

from minidb.datatypes import IntegerType, StringType
from minidb.column import Column
from minidb.table import Table

columns = [Column("id", IntegerType(0)), Column("name", StringType(""))]
table = Table("users", columns)

table.insert({"id": 1, "name": "Alice"})
table.insert({"id": 2, "name": "Bob"})

for row in table:
    print(row)

### 🔍 2. Виконання запитів:

from minidb.query import SimpleQuery

query = SimpleQuery(table).aggregate("id")
print(f"Сума ID: {query.aggregate_sum()}")  # Виведе: Сума ID: 3
🔗 3. Об'єднання таблиць:

from minidb.joinedtable import JoinedTable

users = Table("users", [Column("id", IntegerType(0)), Column("name", StringType(""))])
orders = Table("orders", [Column("user_id", IntegerType(0)), Column("total", IntegerType(0))])

users.insert({"id": 1, "name": "Alice"})
orders.insert({"user_id": 1, "total": 100})

joined = JoinedTable(users, orders, "id", "user_id")

for row in joined:
    print(row)

## ✅ Тестування


Виконати всі тести:

python -m unittest discover tests

Запустити конкретний тест:

python -m unittest tests.test_table

## 📂 Структура проекту

minidb/
├── .venv/            # Віртуальне середовище
├── .gitignore        # Ігнорування файлів для Git
├── README.md         # Опис проекту
├── requirements.txt  # Залежності
├── minidb/           # Основний пакет
│   ├── __init__.py
│   ├── datatypes.py  # Типи даних
│   ├── column.py     # Клас Column
│   ├── row.py        # Клас Row
│   ├── table.py      # Клас Table
│   ├── query.py      # Запити до таблиць
│   ├── joinedtable.py # З'єднання таблиць
│   ├── database.py   # База даних
├── tests/            # Тести
│   ├── test_datatypes.py
│   ├── test_column.py
│   ├── test_row.py
│   ├── test_table.py
│   ├── test_query.py
│   ├── test_database.py
└── examples/         # Приклади використання
    └── demo.py       # Демонстраційний скрипт
