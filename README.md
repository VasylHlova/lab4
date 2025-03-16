# MiniDB 📦

MiniDB — це легка та гнучка in-memory база даних, написана на Python. Вона дозволяє створювати таблиці, вставляти дані, виконувати запити та з'єднувати таблиці без використання зовнішньої СУБД.

## ⚡ Основні можливості:

```plaintext
✔️ Гнучка типізація: підтримка IntegerType, StringType, BooleanType, DateType
✔️ Модель бази даних: Column, Row, Table, Database
✔️ Запити до таблиць: SimpleQuery з підтримкою фільтрації, агрегації та сортування
✔️ Операції з даними: додавання, оновлення, видалення та пошук рядків
✔️ Збереження та завантаження даних у форматі JSON
✔️ Об'єднання таблиць (JoinedTable)

```

---

## 🚀 Встановлення

### 1️⃣ Клонування репозиторію:

```powershell
git clone https://github.com/yourusername/minidb.git
cd minidb
```

### 2️⃣ Створення та активація віртуального середовища:

```powershell
python -m venv .venv
source .venv/bin/activate  # Linux/macOS
.venv\Scripts\activate     # Windows
```

### 3️⃣ Встановлення залежностей:

```powershell
pip install -r requirements.txt
```

---


## ✅ Тестування

Виконати всі тести:

```powershell
python -m unittest discover tests
```

Запустити конкретний тест:

```powershell
python -m unittest tests.test_table
```

---

## 📂 Структура проекту

```
minidb/
├── .venv/            # Віртуальне середовище
├── .gitignore        # Ігнорування файлів для Git
├── README.md         # Опис проекту
├── requirements.txt  # Залежності
├── minidb/           # Основний пакет
│   ├── init.py
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
```
