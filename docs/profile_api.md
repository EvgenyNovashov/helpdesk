Шаги ниже описывают создания страницы с профилем пользователя Личного кабинета ИТ пользователя

Шаг 1. Создай миграцию для таблицы user_status:
       поля status_id - primary key , status_name - VARCHAR(50).
       Используй Alembic. Заполни таблицу статусами: "Активный", "Неактивный"

Шаг 2. Создай миграцию для таблицы user:
       поля user_id - primary key, user_created_at - timestamp, user_status_id - FOREIGN KEY, user_pwd - varchar2(12), user_about - varchar2(12), email - varchar2(50), login - varchar2(50), fullname - varchar2(255)
       Используй Alembic. Cтатусы брать из таблицы user_status

Шаг 3. Напиши модель User в models/user.py
       и репозиторий UserRepository в repositories/user.py
       с методами create, block

Шаг 4. Напиши сервис UserService в services/user.py
       с методом create(user_login, user_pwd, user_about, user_email, user_fullname) 
       Используй UserRepository. 

Шаг 5. Добавь эндпоинты POST /api/user и GET /api/user
       в routes/user.py. Используй UserRepository. 

Шаг 6. Добавь в существующей frontend блок Пользователи
       в view/user.py Используй /api/user. 
       Добавить функцию фильтрации и сортировки задач