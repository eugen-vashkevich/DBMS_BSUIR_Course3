## Функциональные Требования

1. **Управление пользователями:**
   - Регистрация и авторизация пользователей.
   - Управление профилями пользователей.
   - Назначение ролей пользователям (пациент, доктор, администратор).

2. **Управление расписанием:**
   - Создание и обновление расписания врачей.
   - Проверка доступности времени для записи.

3. **Управление записями на прием:**
   - Создание, изменение и отмена записей на прием.
   - Уведомления о предстоящих приемах.

4. **Управление медицинскими картами:**
   - Создание и обновление медицинских карт пациентов.
   - Просмотр истории записей.

5. **Система отзывов:**
   - Оставление отзывов о врачах и услугах.
   - Просмотр оценок и отзывов.

6. **Управление вопросами и ответами:**
   - Задание вопросов пользователями.
   - Ответы на вопросы и изменение статуса.

7. **Управление акциями:**
   - Создание и обновление акций на услуги.
   - Применение скидок к услугам.

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
