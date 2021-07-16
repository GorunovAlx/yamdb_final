# api_yamdb
### Описание
Проект YaMDb собирает отзывы (Review) пользователей на произведения (Title). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»). Сами произведения в YaMDb не хранятся. В каждой категории есть произведения: книги, фильмы или музыка. Читатели оставляют к произведениям текстовые отзывы (Review) и выставляют произведению рейтинг (оценку в диапазоне от одного до десяти). 
### Технологии
- [Python 3.7](https://www.python.org/downloads/release/python-370/)
- [Django 2.2.19](https://docs.djangoproject.com/en/3.2/releases/2.2.19/)
- [Django REST framework](https://www.django-rest-framework.org)
- [JSON Web Token](https://jwt.io)
- [Gunicorn](https://gunicorn.org)
- [Docker](https://docs.docker.com)
- [Nginx](https://nginx.org)
- [PostgreSQL](https://www.postgresql.org)
## Подготовка к запуску
- Необходимо установить:
[Docker](https://www.docker.com/products/docker-desktop)
- Настройте параметры окружения:
Заполните **.env.example**. Не забудьте убрать **.example**
### Запуск проекта
- Запуск docker-контейнера:
```
docker-compose up
```
- Настройка миграций:
```
docker-compose exec web python manage.py migrate --noinput
```
- Создание суперпользователя:
```
docker-compose exec web python manage.py createsuperuser
```
- Сбор статики:
```
docker-compose exec web python manage.py collectstatic --no-input
```
- Чтобы убедиться, что проект работает:
```
Откройте ссылку в браузере (http://178.154.212.81/api/v1/), сделайте запросы к api.
Откройте админку (http://178.154.212.81/admindesert/) и войдите под учетной записью суперпользователя.
redoc: (http://178.154.212.81/redoc/)
```
- Заполнения базы начальными данными:
```
docker-compose exec web python manage.py dumpdata > fixtures.json
```
![yamdb_workflow](https://github.com/GorunovAlx/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
### Автор
[Алексей Горюнов](https://github.com/GorunovAlx)
