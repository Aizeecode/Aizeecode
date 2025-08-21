# 🧑‍💻 QA Portfolio — Ailat Internship

Добро пожаловать в мой QA-портфолио!  
Здесь собраны примеры моей работы во время стажировки над продуктом Ailat(Android приложения по инвестициям по Шариату), а также дополнительные учебные и практические материалы по тестированию.  

---

## 📌 Обо мне
Я начинающий QA-инженер с опытом стажировки, где занималась тестированием мобильного-приложения, поиском багов и улучшением UX.  
Умею работать с:
- написанием баг-репортов, тест-кейсов, чек-листов
- **API-тестированием** (Postman, Swagger)  
- базами данных (**SQLite**)  
- таск-трекерами (**Jira, Notion**)
- Admin panel (**создать, удалить пользователя, добавить продукт и услугу на сайт**)
- Web тестирование(**dev tools**)

---

## 📂 Структура репозитория
- **BugReports/** — примеры баг-репортов (60 штук за время стажировки, здесь представлены основные) **https://codeunion.notion.site/21fe5d447d058007a89fdb8b29e1afa8?v=21fe5d447d05818d91ef000c06a92cac**
- **BugReports** - (примеры учебных баг-репортов) **https://docs.google.com/spreadsheets/d/16cuGDkDigcdgfvf4KzGqeUoIMyD-X69poCn41jYYaQ8/edit?usp=sharing**
- **TestCases/** — тест-кейсы для функционального тестирования по учебному проекту Arbuz.kz **https://docs.google.com/spreadsheets/d/1o5ud8AnWf7TgU1Fszlur-I2fwMGvUU3oi4_Ecf0fh_8/edit?gid=0#gid=0https://docs.google.com/spreadsheets/d/1o5ud8AnWf7TgU1Fszlur-I2fwMGvUU3oi4_Ecf0fh_8/edit?gid=0#gid=0**  
- **Checklists/** — чек-листы (по учебному проекту)  **https://docs.google.com/spreadsheets/d/1F8kYo3KiyhYn_XIznxaabDDdGZr_ZLvuevSZFS4vpXM/edit?gid=0#gid=0**
**  
---

## 🐞 Пример баг-репорта
```markdown
# Bug 001: [Back] Неверное сообщение при входе

**Описание:**
При попытке входа на эндпоинт **{{api_base_url}}/{{authentication_prefix}}/tokens/new**
с правильным email и **неверным паролем**, API возвращает сообщение (ниже), что не соответствует контексту действия.
Проверка "прочности" пароля должна выполняться только при регистрации или смене пароля, но не при логине.

{
"statusCode": 400,
"error":
{"message": "password is not strong enough",
"code": "USER_PASSWORD"}
}

**Окружение:**

Инструмент: Postman
Метод: `POST`
Endpoint: `{{api_base_url}}/{{authentication_prefix}}/tokens/new`

**Ожидаемый результат:**
HTTP статус: `401 Unauthorized`
Тело ответа:  "message": "Неверный логин или пароль”

**Фактический результат:**
{
"statusCode": 400,
"error": {"message": "password is not strong enough",
"code": "USER_PASSWORD"}
}




