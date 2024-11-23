# Flask API з SQLAlchemy

Це REST API для управління магазинами та товарами, розроблений за допомогою Flask і SQLAlchemy для роботи з базою даних.

## Основні можливості
- **Магазини**: додавання, перегляд та видалення магазинів.
- **Товари**: додавання, перегляд та видалення товарів, що прив’язані до магазинів.

## Вимоги до проекту
- Python 3.x
- Flask
- Flask-SQLAlchemy
- Flask-Smorest
- Marshmallow

## Інструкція з встановлення
1. **Клонування репозиторію**  
   ```bash
   git clone https://github.com/Lutvunenko-Dmutro/flask-api.git
   cd flask-api
   ```

2. **Створення віртуального середовища**  
   ```bash
   python -m venv venv
   ```

3. **Активація віртуального середовища**  
   - Windows:
     ```bash
     venv\Scripts\activate
     ```
   - macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Встановлення залежностей**  
   ```bash
   pip install -r requirements.txt
   ```

5. **Запуск додатку**  
   ```bash
   flask run
   ```
   API буде доступне за адресою: [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

## API Ендпоінти
### Магазини
- `GET /stores` — отримати список всіх магазинів.
- `GET /stores/<int:store_id>` — переглянути магазин за ID.
- `POST /stores` — створити новий магазин.
- `DELETE /stores/<int:store_id>` — видалити магазин за ID.

### Товари
- `GET /item/<int:item_id>` — отримати товар за ID.
- `POST /item` — створити новий товар.
- `DELETE /item/<int:item_id>` — видалити товар за ID.

## Приклади використання
### Додавання магазину  
**POST /stores**  
```json
{
  "name": "Техно Магазин"
}
```

### Додавання товару  
**POST /item**  
```json
{
  "name": "Ноутбук",
  "price": 1200.99,
  "store_id": 1
}
```

## Структура проекту
- **`app.py`** — основний файл програми, що відповідає за налаштування Flask та підключення ендпоінтів.
- **`models/`** — містить моделі SQLAlchemy:
  - `store.py` — модель магазину.
  - `item.py` — модель товару.
- **`resources/`** — логіка обробки HTTP-запитів:
  - `store.py` — ендпоінти для магазинів.
  - `item.py` — ендпоінти для товарів.
- **`schemas.py`** — серіалізація та валідація даних за допомогою Marshmallow.
- **`db.py`** — конфігурація підключення до бази даних SQLAlchemy.
- **`requirements.txt`** — залежності проекту.

## Автор
Кириченко Кіріл  
Група I-23  

