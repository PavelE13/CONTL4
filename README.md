# CONTL4
1. Создаемтестовую директорию и заходим c sudo
   sudo -s
   mkdir docker_test
   cd docker_test
2.  Coздаем приложение python 3 app.py
   nano app.py
print "HELLO Z!"

При написании программы с командой ввода данных input контейнер при выполнении выдас ошибку, потому что программа ожидает ввода данных из стандартного ввода, но не получает их. В данном случае, когда программа запускается в контейнере, стандартный ввод закрыт, поэтому программа не может получить данные и выходит с ошибкой.
4. Создаем докерфайл
   nano Dockerfile
   
    FROM ubuntu:latest
    RUN apt-get update && apt-get install -y python3
    COPY app.py /app/
    WORKDIR /app
    CMD ["python3", "app.py"]

5. Собираем докерфайл
    docker build -t my-python-app .
6. Запускаем докерфайл
   docker run my-python-app
   ![L4_2](https://github.com/PavelE13/CONTL4/assets/94640966/b51dcd00-97ab-4206-ab94-ed3297b69b6f)
