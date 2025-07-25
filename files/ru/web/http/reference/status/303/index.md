---
title: 303 See Other
slug: Web/HTTP/Reference/Status/303
---

HTTP код перенаправления **`303 See Other`** обычно отправляется в результате {{HTTPMethod("PUT")}} или {{HTTPMethod("POST")}} запроса и указывает, что перенаправление производится не на новый (только что загруженный) ресурс, а на другую страницу, например, страницу подтверждения или страницу с результатами загрузки. Метод, используемый для отображения страницы, на которую производится перенаправление - всегда {{HTTPMethod("GET")}}.

## Статус

```
303 See Other
```

## Пример

### Запрос клиента

```http
POST /api/items/delete HTTP/1.1
Host: www.example.org
```

### Ответ сервера

```http
HTTP/1.1 303 See Other
Location: /confirmation
```

## Спецификации

| Спецификация                               | Название                                                      |
| ------------------------------------------ | ------------------------------------------------------------- |
| {{RFC("7231", "303 See Other" , "6.4.4")}} | Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content |

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- {{HTTPStatus("302", "302 Found")}}, временное перенаправление
