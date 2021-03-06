# Демопроект Specsful
Описание демопроекта *Bank Application* в Specsful

## 1) экраны и состояния экранов приложения

В Specsful можно хранить экраны приложения и их части, фрагменты (не имеет отношения к фрагментам Андроид). Экраны и фрагменты могут иметь состояния.

### Пример для экрана приложения:

Экран [Список операций](https://app.specsful.io/project/1/screen/9) помимо [основного состояния](https://app.specsful.io/project/1/screen/9) имеет [состояние загрузки](https://app.specsful.io/project/1/screen/9/state/10).

### Для фрагмента экрана:

Фрагмент [Элемент списка счетов](https://app.specsful.io/project/1/screen/28) имеет состояния:

* [с картой](https://app.specsful.io/project/1/screen/28/state/30)
* [накопительный счет](https://app.specsful.io/project/1/screen/28/state/31)

## 2) структуры данных приложения в связке с элементами на экране

Фрагмент [Элемент списка счетов](https://app.specsful.io/project/1/screen/28) использует модель данных [`BankProduct`](https://app.specsful.io/project/1/model/33). Для отображения баланса на фрагменте используются данные из этой модели по пути: `balance / value`. Также на фрагменте прописано откуда брать все остальные видимые элементы.

## 3) работу приложения с сетью и формат передаваемых данных

[Экран авторизации](https://app.specsful.io/project/1/screen/2) работает с сетевым запросом [Login]( https://app.specsful.io/project/1/request/56) передавая ему модель `LoginRequest`. Поле ввода номера телефона на экране связано со значением `phoneNumber` модели `LoginRequest`. 

## 4) параметры для написания автоматических тестов приложения

В демо проекте у каждого элемента на экране прописан ID. Например, на [экране авторизации](https://app.specsful.io/project/1/screen/2) у поля номер телефона ID: `phoneNumber`. Это id для разметки (часто XML) элементов. По этим ID можно писать автотесты для приложения. Если ID разметки прописать в документации до создания экранов приложения, они будут одинаковые для всех платформ приложения, что позволит сильно сократить труд при написании автотестов.

## 5) локализации

Если приложение пишется на нескольких языках, то также как поле модели данных на экране можно прописать ключ локализации и его значения для различных языков. Например на [экране авторизации](https://app.specsful.io/project/1/screen/2) текст «_Подтвердите ваш номер телефона_» привязан к ключу [`PHONE_CONFIRMATION_LABEL`](https://app.specsful.io/project/1/text/PHONE_CONFIRMATION_LABEL), который имеет значение на нескольких языках.
