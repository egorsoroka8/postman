# DummyAPI Postman collection

### Использованы HTTP методы : GET, POST, PUT, DELETE.

### Коллекция включает : 
- Создание коллекции запросов с разделением по объектам тестирования (user, post, comment, tags).
- Создание тестового окружения с использованием автозаполнения переменных.
- Добавлением SNIPPETS тестов на проверку статус кода ("Status code is 200").
- Использование динамических переменных из библиотеки Postman для создания объектов ($random...).
- Создание массивов для недостающих переменных в PRE-REQUESTS.
- Добавление документации в раздел Documentation.

Файлы : [коллекция](https://github.com/egorsoroka8/postman/tree/main/dummyAPI/DummyAPI.postman_collection.json), [окружение](https://github.com/egorsoroka8/postman/blob/main/dummyAPI/Dummy%20API.postman_environment.json).


## Пошаговое описание

### Настройка окружения.

**1) Создаем окружение DummyAPI**

**2) Добавляем в окружение базовый URL, как переменную.** 

**3) Добавляем в окружение переменные user_id, post_id, comment_id. Значения для этих переменных оставляем пустыми.**

![image](https://user-images.githubusercontent.com/112896404/202923149-36e9c852-e8d4-4c19-a3e5-17a901b8657f.png)



### Создание и настройка коллекции.

**1) Создаем коллекцию DummyAPI**

**2) Добавляем в коллекцию токен авторизации, присвоенный сайтом.** 

![image](https://user-images.githubusercontent.com/112896404/202894953-5917047d-c43f-4de3-a562-001d2b4d46a6.png)

**3) Добавляем в коллекцию SNIPPETS тест на проверку кода "Status code is 200".**

![image](https://user-images.githubusercontent.com/112896404/202895203-0f577d8d-69c6-42a4-8798-773a0dbd0c6d.png)

**4) Разбиваем коллекцию на папки по объектам : User, Post, Comment, Tags.**

![image](https://user-images.githubusercontent.com/112896404/202894550-15905afd-2a76-4829-84e5-6bed3f6c35bc.png)

**5) Добавляем в папки запросы.**

![image](https://user-images.githubusercontent.com/112896404/202896513-6410c6ac-f55a-497b-baea-acbcca09f8a6.png)

**6) Задаем метод и путь для наших запросов (дальнейшие шаги рассмотрим на основе объекта User).**
   
   ```
   - Get User by List : Method : GET | Path : {{url}}user/
   - Get User by ID : Method : GET | Path : {{url}}user/{{user_id}}
   - Create User :  Method : POST | Path : {{url}}user/create
   - Update User : Method : PUT | Path : {{url}}user/{{user_id}}
   - Delete User : Method : DELETE | Path : {{url}}user/{{user_id}}
   ```
**7) Заполняем тело POST запроса. Формат данных JSON.**

   Для данных, кроме *title, gender, timezone, state* задам динамическую переменную с формированием рандомного значения из библиотеки Postman.
   
   ![image](https://user-images.githubusercontent.com/112896404/202897583-d3e05403-145d-4ba3-ad36-71c6e6c0f39f.png)

   Для *title, gender, timezone, state* задаем имена переменных в стилистики Postman :
   ```
   "title" : "{{$randomTitle}}"
   "gender" : "{{$randomGender}}"
   "timezone" : "{{$randomTimezone}}"
   "state" : "{{$randomState}}"
   ```
   Во вкладке коллекции PRE-REQUESTS, создаем для данных переменных массивы. 

![image](https://user-images.githubusercontent.com/112896404/202899553-c4d23ec5-9c8b-4fa4-9862-d65545770897.png)

В конечном итоге, имеем формирование рандомного значения для каждого параметра.
![image](https://user-images.githubusercontent.com/112896404/202899616-527b6e43-c813-44ca-9e8b-63e0a529e795.png)

**8) Отправляем POST запрос на создание User, все данные сформированы.**

![image](https://user-images.githubusercontent.com/112896404/202899995-c15c2ca6-5f50-43d7-a370-816df9eb7526.png)

**9) Во вкладке тест прописываем скрипт на добавление id пользователя из тела ответа в параметры окружения, значение переменной устанавливаем user_id**

![image](https://user-images.githubusercontent.com/112896404/202914311-138c7af7-a403-413b-901d-84a9e01676ac.png)

**10) Отправляем повторно запрос и проверяем что новый id записан в окружение**

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/202914639-c1605806-c224-45cf-b1ae-8dca6079e5b3.png">
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/202914859-e1d9fa4a-7c78-460c-815b-185554e279df.png">
</p>

**11) По аналогии заполняем данные для объектов Post, Comment, Tags**

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/202989233-d2cf9f88-0c7d-4d81-bef5-d96703e28d84.png">
</p>

### Запуск тестов.

**1) Формируем коллекцию перед запуском тестов. Порядок запросов POST -> GET -> PUT -> DELETE**

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/202923591-fb66c2d8-416d-4403-babb-683711946bdb.png">
</p>

**2) Результат после запуска коллекции, все запросы имеют статус 200 OK.**

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/202988848-dbc50ed1-1fd9-4d57-9e97-c76005f90906.png">
</p>


<p align="center">
  <img src="">
</p>
