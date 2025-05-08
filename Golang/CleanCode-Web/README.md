# CleanCode архитектура для Web

## Общая архитектура в ФС

```
\
|--go.mod
|--go.sum
|--\cmd
|--|--main.go
|--|--.env
|--\pkg
|--|--\package1
|--|--|--something.go
|--|--|--something_mocks.go
|--|--|--something_test.go
|--|--\package2...
|--\internal
|--|--\handler
|--|--|--handler1.go
|--|--|--handler1_mocks.go
|--|--|--handler1_test.go
|--|--|--handler2.go
|--|--|--handler2_mocks.go
|--|--|--handler2_test.go...
|--|--\repository
|--|--|--repository1.go
|--|--|--repository1_mocks.go
|--|--|--repository1_test.go
|--|--|--repository2.go
|--|--|--repository2_mocks.go
|--|--|--repository2_test.go..
|--|--\service
|--|--|--service1.go
|--|--|--service1_mocks.go
|--|--|--service1_test.go
|--|--|--service2.go
|--|--|--service2_mocks.go
|--|--|--service2_test.go..
|--|--\ipackage1
|--|--\ipackage2...
```

## Предназначение директорий

### cmd

Предназначена для хранения проекта, директория из которой зачастую билдиться и запускается проект. Часто содержит кроме main.go зависимости (например .env) и скомпилированный файл.

### internal

Предназначена для организации критических пакетов, реализующих бизнес-логику. Особенностью данной директории является то, что её нельзя скачать через go get в отличии от pkg.
Зачастую в Web выделяют минимум 3 пакета:
- repository (Содержит логику работы с БД)
- service (Содержит бизнес-логику, вызывает repository)
- handler (Содержит обработку запросов-ответов, вызывает service)

Также могут выделяться и другие критические пакеты например middlewares

Файлы внутри директорий организованы следующим образом:
- файл.go - какая-то логика
- файл_mock.go - моки на интерфейсы необходимые для тестирования
- файл_test.go - тесты для модуля

### pkg

Предназначена для организации некритических пакетов. Организация как в internal.

