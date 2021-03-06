---
title: предупреждения мобильности
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- vs.codeanalysis.MobilityRules
helpviewer_keywords:
- managed code analysis warnings, mobility warnings
- mobility warnings
- warnings, mobility
ms.assetid: 9808054c-593b-4fc3-92cc-1fc45f41569c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47bb602da5483b3ea31513b6185ce00e07200a42
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54974010"
---
# <a name="mobility-warnings"></a>предупреждения мобильности
Предупреждения мобильности поддерживают эффективное энергопотребление.

## <a name="in-this-section"></a>В этом разделе

|Правило|Описание|
|----------|-----------------|
|[CA1600: Не используйте приоритет процессов](../code-quality/ca1600-do-not-use-idle-process-priority.md)|Не задавайте для приоритета процесса значение Idle. Процессы с приоритетом System.Diagnostics.ProcessPriorityClass.Idle будут занимать ЦП, который иначе простаивал бы, и тем самым блокировать работу в режиме ожидания.|
|[CA1601: Не используйте таймеры, препятствующие изменению состояния электропитания](../code-quality/ca1601-do-not-use-timers-that-prevent-power-state-changes.md)|Повышение частоты периодических действий приводит к дополнительной нагрузке на ЦП и препятствует работе таймеров энергосберегающих режимов, которые отключают монитор и жесткие диски.|