---
title: Como analisar uma corda (C#)
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: 79821eb9e5cd7187ac3c2a93f85eaae45c5c48ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345805"
---
# <a name="how-to-parse-a-string-c"></a>Como analisar uma corda (C#)

Este tópico mostra como analisar uma cadeia de caracteres para criar uma árvore XML no C#.

## <a name="example"></a>Exemplo

O seguinte código C# mostra como analisar uma seqüência XML:

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

O `Contacts` nó raiz `Contact` tem dois nódulos. Para acessar alguns dados específicos em seu XML analisado, use o método [XElement.Elements(),](xref:System.Xml.Linq.XContainer.Elements) `Contacts` que neste caso retorna os elementos filho do nó raiz. O exemplo a seguir `Contact` imprime o primeiro nó para o console:

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a>Confira também

- [Como encontrar um elemento com um atributo específico (C#)](how-to-find-an-element-with-a-specific-attribute.md)
