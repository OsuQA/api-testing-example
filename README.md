В качестве примера я протестировал публичное API reqres.in в Postman, которое имитирует поведение REST-сервиса.

Протестированный endpoint:
GET https://reqres.in/api/users/2

Результат запроса:
Код ответа: 200 OK
Ответ:
{
    "data": {
        "id": 2,
        "email": "janet.weaver@reqres.in",
        "first_name": "Janet",
        "last_name": "Weaver",
        "avatar": "https://reqres.in/img/faces/2-image.jpg"
    },
    "support": {
        "url": "https://contentcaddy.io?utm_source=reqres&utm_medium=json&utm_campaign=referral",
        "text": "Tired of writing endless social media content? Let Content Caddy generate it for you."
    }
}

Проверки, которые я выполнил:
Код ответа соответствует успешному запросу (200)
Все ожидаемые поля (id, email, first_name, last_name, avatar) присутствуют
Значение data.id соответствует запрашиваемому 2
Проверка формата email и ссылки на аватар (валидный URL)

Также я проверил:
GET https://reqres.in/api/users/23 (несуществующий пользователь)
Ожидаемый код: 404 Not Found
Фактический ответ: код 404, тело ответа пустое {}
