**Dockerfile** - что такое ?
Ну это образ для [[Что такое Docker|контейнера]]

#### Пример как создавать докер файл!

Итак допустим мы имеем пайтон файл, который считает до ста:
```python
import time

total = 0
count = 0
while count < total:
    count += 1
    print("Line:" + str(count))
    time.sleep(1)
```

Что бы создать образ контейнера мы создадим **Dockerfile**:
```Dockerfile
FROM python:3.12-alpine
WORKDIR /python-app
COPY . .
CMD ["python", "project.py"]
```

Где у нас:
1. Скачивается образ alpine linux, с интерпритатором python
2. Создается рабочая директория
3. Копируются все файлы из текущей директории в контейнер
4.  И внутри контейнера запускаются комманды: `python` и `project.py`

Затем у нас прописывается **[[Комманды Docker|docker build -t]]** и мы создадим образ контейнера (**-t** в данном случае это тэг)