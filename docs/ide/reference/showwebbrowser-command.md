---
title: Команда ShowWebBrowser
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: df5983b0cbc33abe0f5919a93af1450394134a99
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53985831"
---
# <a name="showwebbrowser-command"></a>Команда ShowWebBrowser

Предназначена для отображения URL-адреса, указанного в окне браузера внутри или вне интегрированной среды разработки (IDE).

## <a name="syntax"></a>Синтаксис

```cmd
View.ShowWebBrowser URL [/new][/ext]
```

## <a name="arguments"></a>Аргументы
 `URL`

 Обязательный. URL-адрес для веб-сайта.

## <a name="switches"></a>Переключатели
 /new

 Необязательный параметр. Указывает, что страница отображается в новом экземпляре браузера.

 /ext

 Необязательный параметр. Указывает, что страница отображается в браузере по умолчанию вне интегрированной среды разработки.

## <a name="remarks"></a>Примечания
 Псевдоним для команды **ShowWebBrowser** имеет значение **navigate** или **nav**.

## <a name="example"></a>Пример
 Следующий пример отображает домашнюю страницу сайта "Документация Майкрософт" в веб-браузере вне интегрированной среды разработки. Если экземпляр веб-браузера уже открыт, то используется он. В противном случае запускается новый экземпляр.

```cmd
>View.ShowWebBrowser https://docs.microsoft.com /ext
```

## <a name="see-also"></a>См. также раздел

- [Команды Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Командное окно](../../ide/reference/command-window.md)
- [Поле "Поиск/команда"](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)