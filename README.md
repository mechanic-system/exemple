## Команды
#### Запуск сервера:
npm start - запуск сервера на nodemon
Инициализация sequelize:
npx sequelize init - инициализация sequelize
### Создание БД:
npx sequelize db:create - создание БД. Название берется из файла конфигурации config/config.json
### Создание моделей:
USER
npx sequelize model:generate --name User --attributes firstName:string,lastName:string,email:string
CONTACT
npx sequelize model:generate --name Contact --attributes name:string,phone:string,userId:integer
### Создание миграций:
npx sequelize migration:generate --name create-users - создание миграции для таблицы users
npx sequelize migration:generate --name create-contacts - создание миграции для таблицы contacts
npx sequelize db:migrate - применение миграций для всех моделей
### Создание сидов:
npx sequelize seed:generate --name demo-user - создание сида для таблицы users
npx sequelize seed:generate --name demo-contacts - создание сида для таблицы contacts
npx sequelize db:seed:all - применение сидов для всех моделей
### Отмена миграций:
npx sequelize db:migrate:undo - отмена последней миграции
npx sequelize db:migrate:undo:all - отмена всех миграций
npx sequelize-cli db:migrate:undo:all --name 1-user - отмена миграции с именем 1-user
npx sequelize-cli db:migrate:undo:all --name 2-contact - отмена миграции с именем 2-contact
### Примеры REST API
### Получение списка всех книг:
HTTP метод: GET
Endpoint: /books
Ответ: массив книг.

### Получение информации о конкретной книге по её ID:
HTTP метод: GET
Endpoint: /books/{bookId}
Ответ: информация о книге.

### Добавление новой книги:
HTTP метод: POST
Endpoint: /books
Тело запроса: { "title": "Название книги", "author": "Автор" }
Ответ: информация о добавленной книге.

### Обновление информации о книге:
HTTP метод: PUT
Endpoint: /books/{bookId}
Тело запроса: { "title": "Новое название", "author": "Новый автор" }
Ответ: обновлённая информация о книге.

### Частичное обновление информации о книге:
HTTP метод: PATCH
Endpoint: /books/{bookId}
Тело запроса: { "title": "Новое название" }
Ответ: обновлённая информация о книге.

### Удаление книги по её ID:
HTTP метод: DELETE
Endpoint: /books/{bookId}
Ответ: статус успешного удаления.

### Получение списка книг определённого автора:
HTTP метод: GET
Endpoint: /authors/{authorId}/books
Ответ: массив книг данного автора.

### Добавление отзыва к книге:
HTTP метод: POST
Endpoint: /books/{bookId}/reviews
Тело запроса: { "text": "Отличная книга!", "rating": 5 }
Ответ: информация о добавленном отзыве.

### Получение всех отзывов для определенной книги:
HTTP метод: GET
Endpoint: /books/{bookId}/reviews
Ответ: массив отзывов к данной книге.

### Поиск книг по ключевому слову:
HTTP метод: GET
Endpoint: /books/search?q=ключевое_слово
Ответ: массив книг, соответствующих условиям поиска.

### Фильтрация книг по году публикации:
HTTP метод: GET
Endpoint: /books?year=2023
Ответ: массив книг, опубликованных в 2023 году.
