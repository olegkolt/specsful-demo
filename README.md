# Specsful Demo Project
Specsful [*Bank Application*](https://app.specsful.io/project/141) Demo Project description

## 1) Application screens and screens states

In Specsful, you can store application screens and their parts, fragments (not related to Android fragments). Screens and fragments may have states.

### Application screen example:

In addition to the [main state](https://app.specsful.io/project/141/screen/144), the [Events](https://app.specsful.io/project/141/screen/144) screen has a [loading state](https://app.specsful.io/project/141/screen/144/state/149).

### Screen fragment example:

Fragment [Element of accounts list](https://app.specsful.io/project/141/screen/146) has the following states:

* [Card Account](https://app.specsful.io/project/141/screen/146/state/147)
* [Savings Account](https://app.specsful.io/project/141/screen/146/state/148)

## 2) Application data structures in conjunction with elements on the screen

Fragment [Element of accounts list](https://app.specsful.io/project/141/screen/146) uses [`BankProduct`](https://app.specsful.io/project/141/model/150) data model. To display the balance on the fragment, data from this model is used along the path: `balance / value`. Also, the fragment says where to get all the other visible elements.

## 3) The operation of the application with the network and the format of the transmitted data

[Login](https://app.specsful.io/project/141/screen/142) screen works with the network [Login]( https://app.specsful.io/project/141/request/152) request passing the `LoginRequest` model to it. The phone number input field on the screen is associated with the `phoneNumber` value of the `LoginRequest` model. 

## 4) Options for writing automated application tests

In the demo project, each element on the screen has an ID. For example, on the [Login](https://app.specsful.io/project/141/screen/142) screen near the field, the phone number is ID: `phoneNumberInput`. This is the id for markup (often XML) elements. Using these ID, you can write autotests for the application. If the markup ID is written in the documentation before creating the application screens, they will be the same for all platforms of application, which will greatly reduce the scope of work when writing autotests.

## 5) Localization texts

If the application is written in several languages, then just like the data model field on the screen, you can register the localization key and its values for different languages. For example, on the [Login](https://app.specsful.io/project/141/screen/142) screen, the text «_Confirm your phone number_» attached to the key [`PHONE_CONFIRMATION_LABEL`](https://app.specsful.io/project/141/text/PHONE_CONFIRMATION_LABEL), which has a meaning in several languages.
