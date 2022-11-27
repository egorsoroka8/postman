# BookerAPI Postman collection

### Методы создания коллекции и настройке окружения, соответствуют рассмотренным в моем подробном гайде [DummyAPI](https://github.com/egorsoroka8/postman/blob/main/dummyAPI/readme.md), за исключением получения токена авторизации :

В данной коллекции, для выполнения запросов PUT и PATCH необходим токен авторизации.</br>
Для получения токена, выполняем запрос, и записываем его значение в окружение.

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/204147907-639bc659-5d38-4452-b79a-bb5b079d3d25.png">
</p>

Получаем значение токена из окружения, зададим ему имя rawToken. По спецификации ключ токена : Cookie, значение : token="token_value".
Задаем новую переменную AuthToken = "token=" + rawToken. Теперь значение токена соответствует спецификации. Записываем скрип на добавление заголовка и выполняем запрос. Статус код запроса 200 OK. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/204149385-893e3da6-d66d-404b-9e84-a126e803d5a2.png">
</p>

Несмотря на отсутствие токена во вкладке Headers, его можно найти в консоли в соотвествующей вкладке.

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/204148803-9bee3d36-37b4-4f20-ad64-8ecc0fad0639.png">
</p>



