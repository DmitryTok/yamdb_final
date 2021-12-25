## YaMDb
![example workflow](https://github.com/DmitryTok/yamdb_final/actions/workflows/yamdb_workflows.yml/badge.svg)
[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-464646?style=flat-square&logo=PostgreSQL)](https://www.postgresql.org/)
[![Nginx](https://img.shields.io/badge/-NGINX-464646?style=flat-square&logo=NGINX)](https://nginx.org/ru/)
[![gunicorn](https://img.shields.io/badge/-gunicorn-464646?style=flat-square&logo=gunicorn)](https://gunicorn.org/)
[![docker](https://img.shields.io/badge/-Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)
[![GitHub%20Actions](https://img.shields.io/badge/-GitHub%20Actions-464646?style=flat-square&logo=GitHub%20actions)](https://github.com/features/actions)
[![Yandex.Cloud](https://img.shields.io/badge/-Yandex.Cloud-464646?style=flat-square&logo=Yandex.Cloud)](https://cloud.yandex.ru/)
## Description of progect YaMDb
* User registration
* List of all titles
* List of all genres 
* List of all categories
* List of all rewiews
* List of all comments to rewiew
* List of all users

## Create and feel the .env file
```
DB_ENGINE=<...> # specify that we work with postgresql data base
DB_NAME=<...> # data base name
POSTGRES_USER=<...> # login for connecting to data base
POSTGRES_PASSWORD=<...> # password for connection to data base (create your own)
DB_HOST=<...> # name of the servise (container)
DB_PORT=<...> # port for conection to data base
SECRET_KEY=<...> # kay from settings.py
```

1.Assembly and run the container
```
docker-compose up -d --build
```
2.Migrations
```
docker-compose exec web python manage.py migrate
```
3.Create a Django superuser
```
docker-compose exec web python manage.py createsuperuser
```
4.Collect static
```
docker-compose exec web python manage.py collectstatic --no-input
```

Redoc:
http://127.0.0.1/redoc/
***
### Example of API request:

Request for a creation posts:
```python
import requests
from pprint import pprint
url = 'http://127.0.0.1/api/v1/categories/'
request = requests.get(url).json()
pprint(request)
```
Response from API:
```json
{"count": 3,
 "next": "None",
 "previous": "None",
 "results": [{"name": "Film", "slug": "movie"},
             {"name": "Booc", "slug": "book"},
             {"name": "Music", "slug": "music"}]}
```
***
## Progect author:
* https://www.linkedin.com/in/dmitry-tokariev-86b182157
***

## Technology

- Python 3
- Django
- Django REST Framework
- Simple JWT

## License

[MIT](http://opensource.org/licenses/MIT).
