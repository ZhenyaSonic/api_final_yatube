# api_final
API для Yatube
Python Django Pytest Postman

Описание
Яндекс Практикум. Итоговый проект. API для Yatube.

Функционал
Подписка и отписка от авторизованного пользователя;
Авторизованный пользователь просматривает посты, создавёт новые, удаляет и изменяет их;
Просмотр сообществ;
Комментирование, просмотр, удаление и обновление комментариев;
Фльтрация по полям.
Установка
Клонировать репозиторий:

git clone git@github.com:ZhenyaSonic/api_final_yatube.git
Перейти в папку с проектом:

cd api_final_yatube/
Установить виртуальное окружение для проекта:

python -m venv venv
Активировать виртуальное окружение для проекта:

# для OS Lunix и MacOS
source venv/bin/activate

# для OS Windows
source venv/Scripts/activate
Установить зависимости:

python3 -m pip install --upgrade pip
pip install -r requirements.txt
Выполнить миграции на уровне проекта:

cd yatube
python3 manage.py makemigrations
python3 manage.py migrate
Запустить проект:

python manage.py runserver

Примеры запросов
Получение токена

Отправить POST-запрос на адрес api/v1/jwt/create/ и передать 2 поля в data:

username - имя пользователя.
password - пароль пользователя.
Создание поста

Отправить POST-запрос на адрес api/v1/posts/ и передать обязательное поле text, в заголовке указать Authorization:Bearer <токен>.

Пример запроса:

{
  "text": "Мой первый пост."
}
Пример ответа:

{
  "id": 2,
  "author": "Dmitrii",
  "text": "Мой первый пост.",
  "pub_date": "2022-04-22T12:00:22.021094Z",
  "image": null,
  "group": null
}
Комментирование поста пользователя

Отправить POST-запрос на адрес api/v1/posts/{post_id}/comments/ и передать обязательные поля post и text, в заголовке указать Authorization:Bearer <токен>.

Пример запроса:

{
  "post": 1,
  "text": "Тест"
}
Пример ответа:

{
  "id": 1,
  "author": "Dmitrii",
  "text": "Тест",
  "created": "2022-04-22T12:06:13.146875Z",
  "post": 1
}
