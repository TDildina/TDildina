# BR_UI_01: Ошибка 400 при отправке формы регистрации после прохождения капчи

| Поле | Значение |
|------|----------|
| **ID** | BR_UI_01 |
| **Серьёзность** | High |
| **Приоритет** | Medium |
| **Модуль** |book store aplication, login|
| **Окружение** |Windows 10, 192.168.0.8;  Chrome, ver 144.0.7559.133;   |
| **URL** | `https://demoqa.com/register` |

## Preconditions

1. Открыт браузер с доступом к интернету
2. Пользователь не авторизован
3. Страница регистрации загружена


## Steps to Reproduce

1. Открыть страницу: https://demoqa.com/book-store
2. Перейти в раздел Book Store Application → Register
3. Заполнить форму:
   - First Name: User_1
   - Last Name: TEST
   - Username: USER_1
   - Password: 1234
4. Установить галку "I'm not a robot"(прохождение капчи)
5. Нажать кнопку "Register"

## Actual Result

- В DevTools → Network виден POST-запрос с ошибкой: POST https://demoqa.com/Account/v1/User 400 (Bad Request) 
- В консоли браузера: Captcha Loaded Successfully. Форма не отправляется, данные не сохраняются


## Expected Result

- Успешная регистрация с кодом 200 OK или 201 Created
- Перенаправление на страницу профиля после регистрации

## Attachments

![Скриншот](./bug-reports/BR_UI_01.jpg)

