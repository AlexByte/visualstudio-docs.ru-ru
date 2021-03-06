---
title: Как выполнить Изменение пространства имен доменного языка
ms.date: 10/31/2018
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 68566324c77796df8ce952135c0752cbb16033a5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54984968"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Как выполнить Изменение пространства имен доменного языка

Вы можете изменить пространство имен доменного языка. Внесите изменения в **обозреватель DSL**в свойствах проекта Dsl и в сведениях о сборке.

## <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Чтобы изменить пространство имен доменного языка

1. В **обозреватель DSL**выберите **Dsl** узла.

2. В **свойства** измените **пространства имен** свойство.

3. Сохраните решение и преобразования шаблонов.

4. На **проекта** меню, выберите **Dsl свойства**.

   Отобразятся свойства проекта.

5. Выберите **приложения** вкладки.

6. Изменение **пространство имен по умолчанию** свойство на новое имя пространства имен.

7. Если требуется, чтобы изменить имя сборки, измените **свойство имени сборки.**

8. Если вы изменили имя сборки, откройте DslPackage\Package.tt и обновите следующую строку:

   `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. Если вы написали ни строчки кода, не забудьте заменить ссылки на пространство имен и класс в файлах кода.

10. Сброс Visual Studio экспериментального экземпляра.

    1. Удалить **\Users\\**_{имя}_**\AppData\Local\Microsoft\VisualStudio\\\*Exp**.

    2. В Windows **запустить** меню, выберите **все программы** > **Microsoft Visual Studio 2010 SDK** > **средства**  >  **Сброс экспериментального экземпляра**.

11. На **построения** меню, выберите **Перестроить решение**.

## <a name="see-also"></a>См. также

[Глоссарий по средствам доменного языка работы](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)