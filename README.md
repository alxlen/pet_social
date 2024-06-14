# Проект Kittygram.

### Запуск в контейнерах и CI/CD с помощью GitHub Actions

![CI/CD Status](https://github.com/alxlen/kittygram_final/actions/workflows/main.yml/badge.svg)

### Описание.

Проект представляет собой пользовательскую базу данных котиков.
Любой желающий может добавить в базу своего любимца и похвастаться его достижениям.
Проект имеет развлекательный харрактер.

API предоставляет следующие возможности: 
- управлять пользователями;
- просматривать пользователям БД котиков;
- добавлять в БД своих котиков;
- редактировать свой контент и удалять его.

### Технологии.

- Python 3.9
- Django 3.2
- Django REST Framework 3.12
- PostgreSQL
- Docker
- Nginx

### Развертывание проекта.

Клонируйте репозиторий на GitHub
Убедитесь, что в репозитории присутствует файл docker-compose.production.yml, 
Dockerfiles для backend, frontend и nginx. 
Добавьте в корень проекта файл .env со следующими переменными окружения:
ALLOWED_HOSTS='Адрес вашего сервера'
DB_HOST=db
DB_PORT=5432
DEBUG=False
DOCKER_USERNAME='Ваше имя пользователя на DockerHub'
POSTGRES_DB=django
POSTGRES_PASSWORD=mysecretpassword
POSTGRES_USER=django_user
SECRET_KEY='Ваш секретный пароль для Django'

Создание секретов GitHub
Перейдите в настройки вашего репозитория на GitHub и добавьте следующие секреты:
DOCKER_USERNAME: Ваше имя пользователя на DockerHub.
DOCKER_PASSWORD: Ваш пароль на DockerHub.
HOST: Адрес вашего сервера для деплоя.
USER: Имя пользователя для подключения по SSH.
SSH_KEY: Приватный SSH-ключ для подключения к серверу.
SSH_PASSPHRASE: Пароль от SSH-ключа.
TELEGRAM_TO: Идентификатор чата Telegram, куда будет отправлено уведомление.
TELEGRAM_TOKEN: Токен вашего Telegram-бота.

Сделайте пуш в ветку main вашего репозитория. 
GitHub Actions автоматически запустит workflow:
Протестирует backend и frontend.
Соберет Docker образы и отправит их в DockerHub.
Задеплоит проект на ваш сервер с помощью SSH и Docker Compose.
Отправит уведомление в Telegram о успешном деплое.

### Автор.

Александр Ленко.
