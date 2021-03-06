### Nemiro.OAuth.LoginForms

**Nemiro.OAuth.LoginForms** это библиотека классов с готовыми формами для авторизации по протоколу **OAuth** в проектах **Windows Forms** (**.NET Framework**).

Исходный код **Nemiro.OAuth.LoginForms** предоставляется на условиях лицензии **Apache 2.0**.

Для установки **Nemiro.OAuth.LoginForms** выполните следующую команду в консоли диспетчера пакетов (**Package Manager Console**):

`PM> Install-Package Nemiro.OAuth.LoginForms`

[Подробнее об установке](https://www.nuget.org/packages/Nemiro.OAuth.LoginForms/)

[Использование диспетчера пакетов NuGet](http://docs.nuget.org/consume/package-manager-console)

### Системные требования

* [Nemiro.OAuth](https://github.com/alekseynemiro/nemiro.oauth.dll) v1.13 или новее;
* .NET Framework 3.5, 4.0, 4.5, 4.6 или 4.7;
* Windows Forms.

### Лицензия

**Nemiro.OAuth.LoginForms** поставляется на условиях лицензии **Apache License Version 2.0**.

### Как использовать?

Создайте для необходимого поставщика экземпляр формы авторизации.

Используйте **Client ID** и **Secret Key**, которые были получены на сайте поставщика в разделе управления вашим приложением.

Например, создание формы для **DropBox**:

**C#**
```C#
// создаем форму
var login = new DropboxLogin
(
  clientId     : "5nkunr8uscwfoba", 
  clientSecret : "n7x9icfwoe6dehq", 
  returnUrl    : "https://oauthproxy.nemiro.net/",
  autoLogout   : false,
  loadUserInfo : false
);

login.Owner = this;

// показываем форму в режиме "диалог"
login.ShowDialog();

// если авторизация прошла успешно
if (login.IsSuccessfully)
{
  // получаем маркер доступа, который можно использовать для работы с API поставщика
  MessageBox.Show(login.AccessToken.Value);
}
```

**Visual Basic .NET**
```VBNet
' создаем форму
Dim login As New DropboxLogin _
(
  clientId     := "5nkunr8uscwfoba", 
  clientSecret := "n7x9icfwoe6dehq", 
  returnUrl    := "https://oauthproxy.nemiro.net/",
  autoLogout   := False,
  loadUserInfo := False
)

login.Owner = Me

' показываем форму в режиме "диалог"
login.ShowDialog()

' если авторизация прошла успешно
If login.IsSuccessfully Then
  ' получаем маркер доступа, который можно использовать для работы с API поставщика
  MessageBox.Show(login.AccessToken.Value)
End If
```

### Локализация

С библиотекой поставляются ресурсы локализации. 
Для каждой культуры ресурсы находятся в отдельной папке.
Все ресурсы использовать не обязательно, достаточно только необходимые.

Например, для английского, русского и немецкого языка необходимы ресурсы:
* /ru/Nemiro.OAuth.LoginForms.resources.dll
* /de/Nemiro.OAuth.LoginForms.resources.dll

Папки с файлами ресурсов должны находиться в каталоге, в котором располагается файл библиотеки - **Nemiro.OAuth.LoginForms.dll**.

### См. также

* https://github.com/alekseynemiro/nemiro.oauth.dll
* http://nemiro.net