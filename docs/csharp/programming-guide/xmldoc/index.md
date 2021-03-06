---
title: Comentários de documentação XML - Guia de programação C#
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: f5a507bc35b0cc0a679fd055bfc255bb3cb9a090
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2020
ms.locfileid: "76789791"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>Comentários de documentação XML (guia de programação C#)

Em C#, você pode criar documentação para o seu código, incluindo elementos XML em campos de comentários especiais (indicados por cortes triplos) no código-fonte diretamente antes do bloco de código ao qual os comentários se referem, por exemplo.

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

Quando você compila com a opção [-doc,](../../language-reference/compiler-options/doc-compiler-option.md) o compilador procurará todas as tags XML no código-fonte e criará um arquivo de documentação XML. Para criar a documentação final com base no arquivo gerado pelo compilador, crie uma ferramenta personalizada ou use uma ferramenta como o [DocFX](https://dotnet.github.io/docfx/) ou o [Sandcastle](https://github.com/EWSoftware/SHFB).

Para consultar elementos XML (por exemplo, sua função processa elementos XML específicos que você deseja descrever em um comentário da documentação XML), você pode usar o mecanismo de citação padrão (`<` e `>`).  Para consultar identificadores genéricos em elementos de referência de código (`cref`), você pode usar os caracteres de escape (por exemplo, `cref="List&lt;T&gt;"`) ou chaves (`cref="List{T}"`).  Como um caso especial, o compilador analisa as chaves como colchetes angulares para tornar o comentário da documentação menos incômodo para o autor ao fazer referência a identificadores genéricos.

> [!NOTE]
> Os comentários da documentação XML não são metadados; eles não estão incluídos no assembly compilado e, portanto, não são acessíveis através de reflexão.

## <a name="in-this-section"></a>Nesta seção

- [Marcas recomendadas para comentários de documentação](./recommended-tags-for-documentation-comments.md)

- [Processando o arquivo XML](./processing-the-xml-file.md)

- [Delimitadores para marcações de documentação](./delimiters-for-documentation-tags.md)

- [Como usar os recursos de documentação do XML](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a>Seções relacionadas

Para obter mais informações, consulte:

- [-doc (Comentários de documentação do processo)](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a>especificação da linguagem C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Confira também

- [C# Guia de Programação](../index.md)
