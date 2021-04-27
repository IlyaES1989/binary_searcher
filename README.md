# Тестовое задание 

 Реализован Web API осуществляющий бинарный поиск в предварительно отсортированном CSV-файле.  
 Принимает в качестве обязательного параметра искомое значение (sku), в качестве дополнительнного параметра значение вероятности правильной рекомендации (rank).  
 
 Решение строится на допущении, что строки в просматриваемом документе, также как и искомые значения всегда имеют постоянную длину на всем просматриваемом диапазоне.
 Это допущение позволяет использовать модуль mmap для сокращения потребления памяти и увеличения скорости ответа.

 ## Клонирование проекта
 ```
$ git clone https://github.com/IlyaES1989/binary_searcher.git
$ cd binary_searcher/
 ```
 В папку с проектом скопировать CSV-файл с неотсортированными данными.
 
 ## Подготовка CSV-файла
```
$ LC_COLLATE=C sort recommends.csv > sorted_recommends.csv
```
Имя отсортированного файла обязательно должно быть "sorted_recommends.csv"
## Запуск проекта
```
$ python -m api
```
## Взаимодействие с API
 - в другом окне выполнить команду
 ```
$ curl -G "http://127.0.0.1:8000/?sku=искомое_значение&rank=минимальный_порог_близости"
 ```
 ***Пример запроса***
 ```
$ curl -G "http://127.0.0.1:8000/?sku=Ia5f7aPUpM&rank=0.8"
 ```
 - либо перейти по URL  http://127.0.0.1:800/?sku=искомое_значение&rank=минимальный_порог_близости в браузере.

 ***Пример URL http://127.0.0.1:8000/?sku=Ia5f7aPUpM&rank=0.8***
