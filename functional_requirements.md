## Функциональные Требования

1. **Управление пользователями:**
   - Регистрация и авторизация пользователей (Пациент, Администратор может создавать врачей).
   - Управление профилями пользователей (Администратор).

2. **Управление расписанием:**
   - Создание и обновление расписания врачей (Администратор).
   - Проверка доступности времени для записи (Администратор, врач, пациент).

3. **Управление записями на прием:**
   - Создание, изменение записей на прием (Врач, администратор).
   - Запись на прием (Пациент).

4. **Управление медицинскими картами:**
   - Создание и обновление медицинских карт пациентов (Врач).
   - Просмотр истории записей (Врач, пациент, администратор).

5. **Система отзывов:**
   - Оставление отзывов о врачах и услугах (Пациент).
   - Просмотр оценок и отзывов (Пациент, врач, администратор).

6. **Управление вопросами и ответами:**
   - Задание вопросов пользователями (Пациент).
   - Ответы на вопросы и изменение статуса (Врач, администратор).

7. **Управление акциями:**
   - Создание и обновление акций на услуги (Администратор).
   - Применение скидок к услугам (Администратор).

8. **Логирование действий:**
   - Запись действий пользователей для аудита и анализа.

## Сущности

### User
- `id`: UUID
- `login`: varchar
- `password`: varchar
- `first_name`: varchar
- `last_name`: varchar
- `role_id`: bigint

### Role
- `id`: UUID
- `name`: bigint

### Schedule
- `id`: UUID
- `doctor_id`: UUID
- `start_date`: date
- `end_date`: date
- `is_available`: boolean

### Appointment
- `id`: UUID
- `patient_id`: UUID
- `doctor_id`: UUID
- `appointment_date`: date
- `service_id`: UUID

### Medical_card
- `id`: UUID
- `patient_id`: UUID
- `records`: text

### Service
- `id`: UUID
- `name`: varchar
- `cost`: decimal

### Promotions
- `id`: UUID
- `title`: varchar
- `description`: text
- `discount`: decimal
- `end_date`: date
- `service_id`: bigint

### Reviews
- `id`: UUID
- `text`: varchar
- `grade`: int
- `user_id`: bigint

### Questions
- `id`: UUID
- `user_id`: bigint
- `question`: varchar
- `answer`: varchar
- `status`: boolean

### ActionLog
- `id`: bigint
- `action`: varchar
- `date`: timestamp
- `user_id`: bigint

https://drawsql.app/teams/test-3398/diagrams/dbms-labs
