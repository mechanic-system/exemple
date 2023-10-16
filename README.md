## Команды
### Запуск сервера:
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

## Примеры REST API
### Получение списка всех книг:
HTTP метод: GET <br>
Endpoint: /books <br>
Ответ: массив книг. <br>

### Получение информации о конкретной книге по её ID:
HTTP метод: GET <br>
Endpoint: /books/{bookId} <br>
Ответ: информация о книге. <br>

### Добавление новой книги:
HTTP метод: POST <br>
Endpoint: /books <br> 
Тело запроса: { "title": "Название книги", "author": "Автор" } <br>
Ответ: информация о добавленной книге. <br>

### Обновление информации о книге:
HTTP метод: PUT <br>
Endpoint: /books/{bookId} <br>
Тело запроса: { "title": "Новое название", "author": "Новый автор" } <br>
Ответ: обновлённая информация о книге. <br>

### Частичное обновление информации о книге:
HTTP метод: PATCH <br>
Endpoint: /books/{bookId} <br>
Тело запроса: { "title": "Новое название" } <br>
Ответ: обновлённая информация о книге. <br>

### Удаление книги по её ID:
HTTP метод: DELETE
Endpoint: /books/{bookId}
Ответ: статус успешного удаления.

### Получение списка книг определённого автора:
HTTP метод: GET <br>
Endpoint: /authors/{authorId}/books <br>
Ответ: массив книг данного автора. <br>

### Добавление отзыва к книге:
HTTP метод: POST <br>
Endpoint: /books/{bookId}/reviews <br>
Тело запроса: { "text": "Отличная книга!", "rating": 5 } <br>
Ответ: информация о добавленном отзыве. <br>

### Получение всех отзывов для определенной книги:
HTTP метод: GET <br>
Endpoint: /books/{bookId}/reviews <br>
Ответ: массив отзывов к данной книге. <br>

### Поиск книг по ключевому слову:
HTTP метод: GET <br>
Endpoint: /books/search?q=ключевое_слово <br>
Ответ: массив книг, соответствующих условиям поиска.<br>

### Фильтрация книг по году публикации:
HTTP метод: GET <br>
Endpoint: /books?year=2023 <br>
Ответ: массив книг, опубликованных в 2023 году. <br>
