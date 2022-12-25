1) Для начала скачаем все необходимые данные отсюда:
https://git.ai.ssau.ru/tk/big_data/src/branch/master/data
2) Выполним развертывание MapR с помощью Docker. Для этого выберем образ для скачивания с сайта:
https://hub.docker.com/r/maprtech/dev-sandbox-container.
Я использовал maprtech/dev-sandbox-container 7.0.0.0_8.1.0_ubuntu18.
3) Воспользуемся файлом docker-compose.yml для конфигурации MapR.
4) Собирем файл образа с помощью команды:
docker-compose up --build -d
5) Подключение к контейнеру по ssh с помощью команды:
ssh root@localhost -p 2222
С таким паролем:
mapr
6) Выполнение настройки Spark с помощью команды:
echo 'export PATH=$PATH:/opt/mapr/spark/spark-3.2.0/bin' > /root/.bash_profile
В итоге будет создан файл .bash_profile.
7) source /root/.bash_profile
8) apt-get update && apt-get install -y python3-distutils python3-apt
9) wget https://bootstrap.pypa.io/pip/3.6/get-pip.py
10) python3 get-pip.py
11) Установка Jupyter:
pip install jupyter
12) Установка PySpark:
pip install pyspark
13) Запустим Jupyter Notebook на сервере:
jupyter-notebook --ip=0.0.0.0 --port=50001 --allow-root --no-browser
Перейдем по одной из двух ссылок.
14) Скачанные файлы поместим в «рабочую» папку. 
15) Далее вся работа осуществляется в файле с раcширением .ipynb.
