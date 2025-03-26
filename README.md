# API аутентификации

Простое API для аутентификации пользователей с использованием JWT токенов.

## Требования

- Node.js
- npm

## Установка

1. Клонируйте репозиторий:
```
git clone https://github.com/Llyesviel/auth5base.git
cd auth
```

2. Установите зависимости:
```
npm install
```

3. Создайте файл `.env` в корневой директории проекта со следующим содержимым:
```
JWT_SECRET=56467901Amy
```

## Запуск сервера

```
npm start
```

Сервер будет запущен на порту 3000: http://localhost:3000

## API Эндпоинты

### Регистрация пользователя
- **URL**: `/register`
- **Метод**: `POST`
- **Тело запроса**:
  ```json
  {
    "username": "имя_пользователя",
    "password": "пароль"
  }
  ```
- **Ответ**:
  ```json
  {
    "message": "User registered successfully"
  }
  ```

### Вход пользователя
- **URL**: `/login`
- **Метод**: `POST`
- **Тело запроса**:
  ```json
  {
    "username": "имя_пользователя",
    "password": "пароль"
  }
  ```
- **Ответ**:
  ```json
  {
    "token": "jwt_токен"
  }
  ```

### Защищенный маршрут
- **URL**: `/protected`
- **Метод**: `GET`
- **Заголовки**:
  ```
  Authorization: Bearer jwt_токен
  ```
- **Ответ**:
  ```json
  {
    "message": "This is a protected route",
    "user": { "userId": 1 }
  }
  ``` 