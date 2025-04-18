# ArticleSpring
Веб-приложение на Spring Boot для создания статьи, теги. Реализована регистрация, авторизация, прав доступа и функциональность для администратора и обычных пользователей. 

## Структура проекта
![image](https://github.com/user-attachments/assets/935fc45f-d4bf-4628-a4d7-033cc73369a9)

config-Конфигурации Spring Security, инициализация данных

controllers - Контроллеры для обработки HTTP-запросов

entity - JPA-сущности: классы, представляющие таблицы в БД

repository - Интерфейсы Spring Data JPA для работы с БД

service - Интерфейсы бизнес-логики для сервисов

serviceImpl - Реализация сервисов

ArticlesApplication - Главный класс запуска Spring Boot

## Как запустить проект
Убедитесь, что у вас установлены:
   - Java 17+
   - Maven
   - PostgreSQL (или H2, если используется встроенная)
2. Настройте `application.properties`
3.Соберите и запустите проект:
./mvnw spring-boot:run
4.Перейдите в браузере на http://localhost:8080/login

## База данных
ER-диаграмма (основные сущности):
![image](https://github.com/user-attachments/assets/8ffcf10a-c014-4c90-ad85-c1f9fe7a70c9)

-- Создание базы данных

```bash
mysql -u root -p
```

```bash
CREATE DATABASE IF NOT EXISTS articles2 CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
```

```bash
CREATE USER IF NOT EXISTS 'articles2test'@'localhost' IDENTIFIED BY 'articles2test';
```

```bash
GRANT ALL PRIVILEGES ON articles2.* TO 'articles2test'@'localhost';
```

```bash
FLUSH PRIVILEGES;
```


## Функциональность 

Регистрация / Вход

Просмотр всех статей

Поиск по заголовку

Просмотр конкретной статьи

Добавление / редактирование / удаление статьи (автор или админ)

Добавление тегов

Привязка статьи к тегам

Модальное приветствие для администратора

Авторизация с ролями

Возможность входа как гость (только просмотр)

## Роли пользователей

Гость (не авторизован)
Может просматривать статьи
Не может создавать, редактировать, удалять

Пользователь (USER)
Может создавать статьи
Может редактировать / удалять только свои статьи

Администратор (ADMIN)
Может редактировать / удалять любые статьи
Имеет расширенные права

