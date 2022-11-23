# PetStoreAPI Postman collection

### Методы создания коллекции и настройке окружения, соответствуют рассмотренным в моем подробном гайде [DummyAPI](https://github.com/egorsoroka8/postman/blob/main/dummyAPI/readme.md), за исключением метода получения переменной для дальнейшего тестирования :

В DummyAPI, при создании объекта User, в теле ответа возвращалось значение id, необходимое для создания последующих объектов и проведения тестирования, при помощи скрипта записывалось в окружение.

**Тело запроса и тело ответа :**
<p align="center">
    <img src="https://user-images.githubusercontent.com/112896404/203510992-fcb127f2-779d-4fad-9e7f-f74915fe30e4.png">
</p>

**Скрипт получение переменной из JSON объекта и его запись в окружение :**

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/203511486-8a45d313-c68d-4f1c-9215-3c76f2eee192.png">
</p>

В PetStore, при создании объекта User, в теле ответа не возвращается значение username, необходимое для дальнейших запросов значение записывается из тела запроса, при помощи скрипта во вкладке тест.

**Тело запроса и тело ответа :**

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/203508936-439d69ca-6589-407f-9a17-1c1b57e75b6f.png">
</p>

**Скрипт парсинга JSON объекта и его записи в окружение :**

<p align="center">
  <img src="https://user-images.githubusercontent.com/112896404/203509046-daba6cc2-801e-40d0-a728-cfed9e0f676b.png">
</p>
