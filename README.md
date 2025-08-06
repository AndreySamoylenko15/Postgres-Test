🎓 SQLAlchemy Student Management DB
Цей Python-скрипт створює структуру бази даних для студентської системи за допомогою SQLAlchemy та підключається до PostgreSQL.
📦 Таблиці бази даних
Скрипт створює наступні таблиці з взаємозв’язками:

groups

id (PK)

name

⤷ має багато students

students

id (PK)

name

group_id (FK → groups.id)

⤷ має багато grades

teachers

id (PK)

name

⤷ має багато subjects

subjects

id (PK)

name

teacher_id (FK → teachers.id)

⤷ має багато grades

grades

id (PK)

student_id (FK → students.id)

subject_id (FK → subjects.id)

grade

date_received

🧰 Технології
Python 3.x

SQLAlchemy

PostgreSQL

⚙️ Як використовувати
1. Встанови залежності
   pip install sqlalchemy psycopg2-binary

2. Переконайся, що PostgreSQL запущений і налаштований
За замовчуванням підключення встановлюється до: postgresql://postgres:11111@localhost/postgres
🔧 Якщо потрібно — зміни рядок підключення тут: engine = create_engine('postgresql://postgres:11111@localhost/postgres')
3. Запусти скрипт python your_script_name.py
Буде створено всі необхідні таблиці у вказаній базі даних.

📌 Примітки
Встановлено ondelete='CASCADE' для зв’язків ForeignKey, що забезпечує автоматичне видалення пов’язаних записів.

Використовується declarative_base() для оголошення моделей SQLAlchemy.
