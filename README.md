# api_final
api final
Установка
Клонировать репозиторий и перейти в него в командной строке:

git clone git@github.com:ingarbi/api_yatube.git
cd api_yatube
Cоздать и активировать виртуальное окружение:

python -m venv env
source env/bin/activate
Установить зависимости из файла requirements.txt:

pip install -r requirements.txt
Выполнить миграции:

python manage.py migrate
Запустить проект:

python3 manage.py runserver
Для документации после запуска перейдите: http://127.0.0.1:8000/redoc/