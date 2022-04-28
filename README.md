# Процедура запуска авто-тестов #

В рамках данного дипломного проекта осуществляется тестирование веб-сервиса по покупке туров (тестирование сценария покупки тура в Марракеш)

### Документация:
 1. План автоматизации (файл [Plan.md](https://github.com/Oksana-Zett/DIPLOMA1/blob/master/Plan.md))

 1. Отчет о проведённом тестировании (файл Report.md)
 1. Отчёт о проведённой автоматизации (файл Summary.md)

### Необходимое ПО для реализации процедуры:
1. GitHub
1. Git
1. IntelliJ IDEA
1. Docker
1. Docker Toolbox (для ОС Windows 7 или  Windows 8)
1. Любой браузер для просмотра веб-страниц 

### Установка, настройка и запуск

1. Склонировать проект с удаленного репозитория на GitHub на локальный компьютер с помощью терминала Git командой: 
```
git clone https://github.com/Oksana-Zett/DIPLOMA1.git
```

*Примечание:*  
*1. файлы для запуска приложения, контейнера и симулятора банковских сервисов находятся в папке [/artifacts](https://github.com/Oksana-Zett/DIPLOMA1/tree/master/artifacts);*  
*2. на проекте поддерживается две СУБД (MySQL, PostgreSQL), для запуска приложения на СУБД MySQL используется файл [docker-compose-mysql.yml](https://github.com/Oksana-Zett/DIPLOMA1/blob/master/artifacts/docker-compose-mysql.yml), на PostgreSQL-[docker-compose-postgresql.yml](https://github.com/Oksana-Zett/DIPLOMA1/blob/master/artifacts/docker-compose-postgresql.yml);*  
*3. для реализации проекта на ОС Windows 10 (и выше), либо Linux/MacOS в файле [application.properties](https://github.com/Oksana-Zett/DIPLOMA1/blob/master/artifacts/application.properties) необходимо указывать хост localhost, на ОС Windows 7 или  Windows 8 необходимо указывать хост 192.168.99.100, установив Docker Toolbox;*  
*4. СУБД MySQL работает на порту 3306, PostgreSQL на порту 5432*

2. Открыть склонированный проект с помощью IntelliJ IDEA
3. Открыть файл [application.properties](https://github.com/Oksana-Zett/DIPLOMA1/blob/master/artifacts/application.properties) и прописать в строке 3:
- для запуска приложения на СУБД MySQL 
```
spring.datasource.url=jdbc:mysql://192.168.99.100:3306/app
``` 
  - для запуска приложения на СУБД PostgreSQL 
```
spring.datasource.url=jdbc:postgresql://192.168.99.100:5432/app
``` 
3. Запустить контейнеры СУБД и симулятора через Docker командой: 
- для СУБД MySQL
```
docker-compose -f docker-compose-mysql.yml up -d
```
- для СУБД PostgreSQL
```
docker-compose -f docker-compose-postgresql.yml up -d
```
*Примечание: остановить контейнеры можно командой:*
- *для СУБД MySQL*
```
docker-compose -f docker-compose-mysql.yml down
```
- *для СУБД PostgreSQL*
```
docker-compose -f docker-compose-postgresql.yml down
```
4. Запустить приложение [aqa-shop.jar](https://github.com/Oksana-Zett/DIPLOMA1/blob/master/artifacts/aqa-shop.jar) командой:
```
java -jar aqa-shop.jar
```
5. Открыть веб-страницу http://localhost:8080 через браузер 
 
