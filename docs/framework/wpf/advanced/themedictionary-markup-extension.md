---
title: Extensão de marcação ThemeDictionary
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: 450956de1c7498bf2b92096b38ad2f64745a0b2d
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141091"
---
# <a name="themedictionary-markup-extension"></a>Extensão de marcação ThemeDictionary
Fornece uma maneira para autores de controles personalizados ou aplicativos que integram controles de terceiros de carregar os dicionários de recursos específicos de temas para uso ao aplicar estilo ao controle.  
  
## <a name="xaml-attribute-usage"></a>Uso do Atributo XAML  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" ... />  
```  
  
## <a name="xaml-object-element-usage"></a>Uso de elemento Object do XAML  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`assemblyUri`|O URI (Uniform Resource Identifier) do assembly que contém informações de tema. Normalmente, esse é um URI "pack://" que referencia um assembly no pacote maior. Recursos de assembly e URIs "pack://" simplificam os problemas de implantação. Para obter mais informações, consulte [URIs de pacote no WPF](../app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Comentários  
 Esta extensão destina-se a preencher apenas um valor de propriedade específico: um <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>valor para.  
  
 Usando essa extensão, você pode especificar um único assembly somente de recursos que contém alguns estilos para usar somente quando o tema Windows Aero é aplicado ao sistema do usuário, outros estilos somente quando o tema Luna está ativo e assim por diante. Usando essa extensão, o conteúdo de um dicionário de recursos específico do controle pode ser invalidado e recarregado automaticamente para ser específico para outro tema quando necessário.  
  
 A `assemblyUri` cadeia de<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> caracteres (valor da propriedade) forma a base de uma Convenção de nomenclatura que identifica qual dicionário se aplica a um tema específico. A <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> lógica para `ThemeDictionary` conclui a Convenção gerando um URI (Uniform Resource Identifier) que aponta para uma variante de dicionário de tema específica, como contido em um assembly de recurso pré-compilado. A descrição dessa convenção, ou as interações dos temas com estilos gerais de controle e estilos de nível de página/aplicativo como um conceito não é abordado completamente aqui. O cenário básico para usar `ThemeDictionary` é especificar a <xref:System.Windows.ResourceDictionary.Source%2A> propriedade de um `ResourceDictionary` declarado no nível do aplicativo. Quando você fornece um URI para o assembly por meio `ThemeDictionary` de uma extensão, em vez de um URI direto, a lógica de extensão fornecerá lógica de invalidação que se aplica sempre que o tema do sistema for alterado.  
  
 A sintaxe de atributo é a sintaxe mais comum usada com essa extensão de marcação. O token da cadeia de caracteres fornecido após a cadeia de caracteres identificadora `ThemeDictionary` é atribuído como o valor <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> da classe de extensão subjacente <xref:System.Windows.ThemeDictionaryExtension>.  
  
 `ThemeDictionary` também pode ser usado na sintaxe de elemento de objeto. Nesse caso, é necessário especificar o valor da <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> propriedade.  
  
 `ThemeDictionary` também pode ser usado em um atributo detalhado que especifica a propriedade <xref:System.Windows.Markup.StaticExtension.Member%2A> como sendo o par propriedade=valor:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" ... />  
```  
  
 O uso detalhado geralmente é útil para as extensões que têm mais de uma propriedade configurável, ou caso algumas propriedades sejam opcionais. Como `ThemeDictionary` tem apenas uma propriedade configurável, que é necessária, esse uso detalhado não é típico.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Na implementação do processador, o tratamento para essa extensão de marcação é definido pela <xref:System.Windows.ThemeDictionaryExtension> classe.  
  
 `ThemeDictionary` é uma extensão da marcação. Extensões de marcação são tipicamente implementadas quando existe um requisito que permite que valores de atributo sejam diferentes de valores literais ou nomes de manipuladores, e o requisito é mais global do que simplesmente colocar conversores de tipo em certos tipos ou propriedades. Todas as extensões de marcação em [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usam os caracteres { e } na sintaxe de atributo, que é a convenção pela qual um processador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconhece que uma extensão de marcação deve processar o atributo. Para obter mais informações, consulte [Extensões de marcação e XAML do WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Veja também

- [Estilo e modelagem](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Visão geral de XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensões de marcação e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Arquivos de recurso, conteúdo e dados do aplicativo WPF](../app-development/wpf-application-resource-content-and-data-files.md)
