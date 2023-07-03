# infra_sprint1
Проект позволяте обмениваться фотографиями котов и собак.
Реализован функционал регистрации и сохранения изображений на сервере
## Установка
- Установить окружение backend:
  python3 -m venv venv
  source venv/bin/activate
  pip install -r requirements.txt
- Выполнить миграции и создать пользователя:
  python3 manage.py migrate
  python3 manage.py createsuperuser
- Соберите статику бэкенд-приложения:
  python3 manage.py collectstatic
  sudo cp -r путь_к_директории_с_бэкендом/static_backend /var/www/название_проекта
- Собрать frontend и его статику
  npm i
  npm run build
  sudo cp -r путь_к_директории_с_фронтенд-приложением/build/. /var/www/имя_проекта/

- Запустить сервер gunicorn с настройками из ропозитория
  /etc/systemd/system/gunicorn_kittygram.service
- Установить настройки для сервера nginx из файла в репозитории
  /etc/nginx/sites-enabled/default
