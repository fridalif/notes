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

