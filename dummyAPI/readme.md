# DummyAPI Postman collection

### Использованы CRUD HTTP методы : GET, POST, PUT, DELETE.

### Коллекция включает : 
- Создание коллекции запросов с разделением по объектам тестирования (user, post, comment, tags).
- Создание тестового окружения с использованием автозаполнения переменных.
- Добавлением SNIPPETS тестов на проверку статус кода ("Status code is 200").
- Использование динамических переменных из библиотеки Postman для создания объектов ($random...).
- Создание массивов для недостающих переменных в PRE-REQUESTS.
- Добавление документации в раздел Documentation.


## Описание шагов 

### 1. Создаем DummyAPI коллекцию: 

**1) Добавляем в коллекцию токен авторизации, присвоенный сайтом.** 
`Type : API Key; Key : app-id; Value : 63760c781f1d8505e69a587c`

![image](https://user-images.githubusercontent.com/112896404/202894953-5917047d-c43f-4de3-a562-001d2b4d46a6.png)

**2) Добавляем в коллекцию SNIPPETS тест на проверку кода "Status code is 200".**

![image](https://user-images.githubusercontent.com/112896404/202895203-0f577d8d-69c6-42a4-8798-773a0dbd0c6d.png)

**3) Разбиваем коллекцию на папки по объектам : User, Post, Comment, Tags.**

![image](https://user-images.githubusercontent.com/112896404/202894550-15905afd-2a76-4829-84e5-6bed3f6c35bc.png)

**4) Добавляем в папки запросы.**

![image](https://user-images.githubusercontent.com/112896404/202896513-6410c6ac-f55a-497b-baea-acbcca09f8a6.png)

**5) Задаем метод и путь для наших запросов (рассмотрим данный шаг на основе объекта User).**
   
   ```
   - Get User by List : Method : GET | Path : {{url}}user/
   - Get User by ID : Method : GET | Path : {{url}}user/{{user_id}}
   - Create User :  Method : POST | Path : {{url}}user/create
   - Update User : Method : PUT | Path : {{url}}user/{{user_id}}
   - Delete User : Method : DELETE | Path : {{url}}user/{{user_id}}
   ```
**6) Заполняем тело POST запроса. Тип данных JSON.**
   
   
   Для данных, кроме *title, gender, timezone, state* в библиотеки Postman можно задать динамическую переменную с формированием рандомного значения.
   
   ![image](https://user-images.githubusercontent.com/112896404/202897583-d3e05403-145d-4ba3-ad36-71c6e6c0f39f.png)

   Для *title, gender, timezone, state* задаем имена переменных :
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



### 2. Создаем DummyAPI окружение
![image](https://user-images.githubusercontent.com/112896404/202894771-341f8e3b-0633-499b-8de1-1fde196ae04d.png)

**1) Добавляем в окружение базовый URL, как переменную.** `Key : url; Value : https://dummyapi.io/data/v1/`

**2) Добавляем в окружение переменные user_id, post_id, comment_id. Значение данным переменным не задаем.**

![image](https://user-images.githubusercontent.com/112896404/202896142-af84a6dd-8421-4430-873e-d38c03a416be.png)


