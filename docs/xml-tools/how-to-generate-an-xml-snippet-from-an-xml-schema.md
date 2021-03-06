---
title: Как выполнить сформировать XML-фрагмент из схемы XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 2c128d2a-aaa6-4814-aa95-e07056afe338
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 54f8a689c83fc0eb370e2e48a9421071151c9271
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55030435"
---
# <a name="how-to-generate-an-xml-snippet-from-an-xml-schema"></a>Как выполнить Создание XML-фрагмент из схемы XML

Редактор XML может создавать XML-фрагменты из схемы на языке XSD. Например, во время работы XML-файл, если курсор находится сразу после имени элемента, можно нажать клавишу **вкладке** для заполнения элемента с данными XML, созданными из информации схемы для этого элемента.

Эта возможность доступна только для элементов. При этом действуют следующие правила.

-   Элемент должен иметь схему связанного с ним типа, то есть элемент должен быть правильным согласно какой-либо связанной схеме. Тип схемы не может быть абстрактным и должен содержать необходимые атрибуты или необходимые дочерние элементы.

-   Текущий элемент в редакторе должен быть пустым, не имеющим атрибутов. Например, все приведенные ниже элементы являются правильными.

    -   `<Account`

    -   `<Account>`

    -   `<Account></Account>`

-   Курсор должен находиться непосредственно справа от имени элемента.

Созданный фрагмент содержит все необходимые атрибуты и элементы. Если значение `minOccurs` больше единицы, во фрагмент включается необходимое минимальное количество экземпляров этого элемента. Максимум составляет 100 экземпляров. Любые фиксированные значения, обнаруженные в схеме, становятся фиксированными значениями во фрагменте. Элементы `xsd:any` и `xsd:anyAttribute` не учитываются и не увеличивают конструкцию фрагмента.

Значения по умолчанию создаются и помечаются как редактируемые значения. Если в схеме указано значение по умолчанию, используется это значение. Но если в схеме значением по умолчанию является пустая строка, редактор создает значения по умолчанию следующим образом.

-   Если тип схемы содержит аспекты перечисления, заданные прямо или косвенно с помощью любого из членов типа объединения, то по умолчанию используется первое перечисляемое значение, найденное в модели объектов схемы.

-   Если тип схемы является атомарным, редактор получает атомарный тип и вставляет имя атомарного типа. Для производного простого типа используется базовый простой тип. Для типа списка в качестве типа `itemType` используется атомарный тип. Атомарным типом для объединения является атомарный тип первого типа `memberType`.

## <a name="example"></a>Пример

 Действия, описанные в этом разделе показано, как использовать функцию фрагмент кода XML в редакторе XML сформированные схемой.

> [!NOTE]
> Прежде чем приступать к этим процедурам, сохраните файл схемы на локальном компьютере.

### <a name="to-create-a-new-xml-file-and-associate-it-with-an-xml-schema"></a>Чтобы создать новый XML-файл и связать его со схемой XML

1.  На **файл** последовательно выберите пункты **New**и нажмите кнопку **файл**.

2.  Выберите **XML-файл** в **шаблоны** область и выберите команду **откройте**.

     Новый файл открывается в редакторе. Этот файл содержит XML-декларацию по умолчанию: `<?xml version="1.0" encoding="utf-8">`.

3.  В окне свойств документа нажмите кнопку обзора (**...** ) на **схемы** поля.

     **XSD-схемы** диалоговое окно.

4.  Нажмите кнопку **Добавить**.

     **Открытие XSD-схемы** диалоговое окно.

5.  Выберите файл схемы и нажмите кнопку **откройте**.

6.  Нажмите кнопку **ОК**.

     Схема XML — связанные с XML-документа.

### <a name="to-generate-an-xml-snippet"></a>Создание XML-фрагмента

1.  Наберите `<` на панели редактора.

2.  Список членов отображает следующие возможные элементы:

     **!--** для добавления комментария.

     **! DOCTYPE** для добавления типа документа.

     **?** для добавления инструкции обработки.

     **Обратитесь к** для добавления корневого элемента.

3.  Выберите **контакт** из списка членов и нажмите кнопку **ввод**.

     Редактор добавляет открывающий тег, `<Contact`, и помещает курсор после имени элемента.

4.  Нажмите клавишу **вкладке** для создания XML-данных для `Contact` элемента на основании информации схемы.

## <a name="input"></a>Входные данные

 В этом пошаговом руководстве используется следующий файл схемы.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<xs:schema elementFormDefault="qualified"
           xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:simpleType name="phoneType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Voice"/>
      <xs:enumeration value="Fax"/>
      <xs:enumeration value="Pager"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:element name="Contact">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="Name">
          <xs:simpleType>
            <xs:restriction base="xs:string"></xs:restriction>
          </xs:simpleType>
        </xs:element>
        <xs:element name="Title"
                    type="xs:string" />
        <xs:element name="Phone"
                    minOccurs="1"
                    maxOccurs="unbounded">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Number"
                          minOccurs="1">
                <xs:simpleType>
                  <xs:restriction base="xs:string"></xs:restriction>
                </xs:simpleType>
              </xs:element>
              <xs:element name="Type"
                          default="Voice"
                          minOccurs="1"
                          type="phoneType"/>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

### <a name="output"></a>Вывод

 Далее приведены XML-данные, созданные на основе информации схемы, которая связана с элементом `Contact`. Элементы, помеченные как `bold` обозначают редактируемые поля в XML-фрагмент.

```xml
<Contact>
  <Name>name</Name>
  <Title>title</Title>
  <Phone>
    <Number>number</Number>
    <Type>Voice</Type>
  </Phone>
</Contact>
```

## <a name="see-also"></a>См. также

- [XML-фрагменты](../xml-tools/xml-snippets.md)
- [Практическое руководство. Использовать XML-фрагменты](../xml-tools/how-to-use-xml-snippets.md)