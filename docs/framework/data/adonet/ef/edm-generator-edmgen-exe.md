---
title: Gerador de EDM (EdmGen.exe)
ms.date: 03/30/2017
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
ms.openlocfilehash: 858525a81e7779e7631ee8ac959110ba946cf652
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738526"
---
# <a name="edm-generator-edmgenexe"></a>Gerador de EDM (EdmGen.exe)

EdmGen. exe é uma ferramenta de linha de comando usada para trabalhar com Entity Framework modelo e arquivos de mapeamento. Você pode usar a ferramenta EdmGen.exe para:

- Conecte-se a uma fonte de dados usando um provedor de dados .NET Framework específico da fonte de dados e gere o modelo conceitual (. CSDL), o modelo de armazenamento (. SSDL) e os arquivos de mapeamento (. MSL) usados pelo Entity Framework. Para obter mais informações, consulte [como: usar EdmGen. exe para gerar o modelo e os arquivos de mapeamento](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

- Validar um modelo existente. Para obter mais informações, consulte [como: usar EdmGen. exe para validar arquivos de modelo e de mapeamento](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md).

- Gerar um arquivo C# ou de código Visual Basic que contém as classes de objeto geradas a partir de um arquivo de modelo conceitual (.csdl). Para obter mais informações, consulte [como: usar EdmGen. exe para gerar código de camada de objeto](how-to-use-edmgen-exe-to-generate-object-layer-code.md).

- Gerar um arquivo C# ou de código Visual Basic que contém as exibições pré-geradas para um modelo existente. Para obter mais informações, [como: gerar previamente modos de exibição para melhorar o desempenho da consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100)).

A ferramenta EdmGen. exe é instalada no diretório .NET Framework. Muitas vezes, está localizada em C:\windows\Microsoft.NET\Framework\v4.0. Para sistemas de 64 bits, está localizada em C:\windows\Microsoft.NET\Framework64\v4.0. Você também pode acessar a ferramenta EdmGen. exe no prompt de comando do Visual Studio (clique em **Iniciar**, aponte para **todos os programas**, aponte para **Microsoft Visual Studio 2010**, aponte para **Ferramentas do Visual Studio**e clique em **Visual Studio 2010 Prompt de comando**).

## <a name="syntax"></a>Sintaxe

```console
EdmGen /mode:choice [options]
```

## <a name="mode"></a>Modo

Ao usar a ferramenta EdmGen.exe, você deve especificar um dos modos a seguir.

|Modo|Descrição|
|----------|-----------------|
|`/mode:ValidateArtifacts`|Valida arquivos .msl, .ssdl e .csdl, e exibe todos os erros ou avisos.<br /><br /> Esta opção requer pelo menos um dos argumentos `/inssdl` ou `/incsdl`. Se `/inmsl` estiver especificado, os argumentos `/inssdl` e `/incsdl` também serão obrigatórios.|
|`/mode:FullGeneration`|Usa informações de conexão de banco de dados especificadas na opção `/connectionstring` e gera .csdl, .ssdl, .msl, camada de objeto e arquivos de exibição.<br /><br /> Esta opção requer um argumento `/connectionstring` e um argumento `/project` ou os argumentos `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` e `/entitycontainer`.|
|`/mode:FromSSDLGeneration`|Gera arquivos .csdl e .msl, código-fonte, e exibe no arquivo .ssdl especificado.<br /><br /> Esta opção requer o argumento `/inssdl` e um argumento `/project` ou os argumentos `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` e `/entitycontainer`.|
|`/mode:EntityClassGeneration`|Cria um arquivo de código-fonte que contém as classes geradas a partir do arquivo csdl.<br /><br /> Esta opção requer o argumento `/incsdl` e o argumento `/project` ou o argumento `/outobjectlayer`. O argumento `/language` é opcional.|
|`/mode:ViewGeneration`|Cria um arquivo de código-fonte que contém as exibições geradas a partir dos arquivos .csdl, .ssdl e .msl.<br /><br /> Esta opção requer os argumentos `/inssdl`, `/incsdl`, `/inmsl,` e `/project` ou `/outviews`. O argumento `/language` é opcional.|

## <a name="options"></a>Opções

|Opção|Descrição|
|------------|-----------------|
|`/p[roject]:`\<cadeia de caracteres >|Especifica o nome do projeto a ser usado. O nome do projeto é usado como um padrão para configuração de namespace, nome do modelo e arquivos de mapeamento, nome do arquivo de código-fonte do objeto e nome do arquivo de código-fonte de geração de exibição. O nome do contêiner de entidade é definido como \<projeto > contexto.|
|`/prov[ider]:`\<cadeia de caracteres >|O nome do provedor de dados de .NET Framework a ser usado para gerar o arquivo de modelo de armazenamento (. SSDL). O provedor padrão é o .NET Framework Provedor de Dados para SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>).|
|`/c[onnectionstring]:`\<cadeia de conexão >|Especifica a cadeia de caracteres usada para se conectar à fonte de dados.|
|arquivo de\<`/incsdl:`|Especifica o arquivo .csdl ou um diretório em que os arquivos .csdl estão localizados. Esse argumento pode ser especificado várias vezes para que você possa especificar vários diretórios ou arquivos .csdl. Especificar vários diretórios pode ser útil para gerar classes (`/mode:EntityClassGeneration`) ou exibições (`/mode:ViewGeneration`) quando o modelo conceitual é dividido em vários arquivos. Isso também pode ser útil quando você quiser validar vários modelos (`/mode:ValidateArtifacts`).|
|arquivo de\<`/refcsdl:`|Especifica o arquivo .csdl ou arquivos adicionais usados para solucionar todas as referências no arquivo de código-fonte .csdl. (O arquivo de código-fonte .csdl é o arquivo especificado pela opção `/incsdl`). O arquivo `/refcsdl` contém tipos de que o arquivo de código-fonte .csdl depende. Esse argumento pode ser especificado várias vezes.|
|arquivo de\<`/inmsl:`|Especifica o arquivo .msl ou um diretório em que os arquivos .msl estão localizados. Esse argumento pode ser especificado várias vezes para que você possa especificar vários diretórios ou arquivos .msl. Especificar vários diretórios pode ser útil para gerar exibições (`/mode:ViewGeneration`) quando o modelo conceitual é dividido em vários arquivos. Isso também pode ser útil quando você quiser validar vários modelos (`/mode:ValidateArtifacts`).|
|arquivo de\<`/inssdl:`|Especifica o arquivo .ssdl ou um diretório em que os arquivos .ssdl estão localizados. Esse argumento pode ser especificado várias vezes para que você possa especificar vários diretórios ou arquivos .ssdl. Isso pode ser útil quando você quiser validar vários modelos `(/mode:ValidateArtifacts)`.|
|arquivo de\<`/outcsdl:`|Especifica o nome do arquivo. csdl que será criado.|
|arquivo de\<`/outmsl:`|Especifica o nome do arquivo .msl que será criado.|
|arquivo de\<`/outssdl:`|Especifica o nome do arquivo .ssdl que será criado.|
|arquivo de\<`/outobjectlayer:`|Especifica o nome do arquivo de código-fonte que contém os objetos gerados a partir do arquivo .csdl.|
|arquivo de\<`/outviews:`|Especifica o nome do arquivo de código-fonte que contém as exibições geradas.|
|`/language:`[VB&#124;Csharp]|Especifica a linguagem dos arquivos de código-fonte gerados. A linguagem volta automaticamente para C#.|
|`/namespace:`\<cadeia de caracteres >|Especifica o namespace modelo a ser usado. O namespace é definido no arquivo .csdl durante a execução de `/mode:FullGeneration` ou `/mode:FromSSDLGeneration`. O namespace não é usado durante a execução de `/mode:EntityClassGeneration`.|
|`/entitycontainer:`\<cadeia de caracteres >|Especifica o nome que será aplicado ao elemento `<EntityContainer>` nos arquivos de mapeamento e modelos gerados.|
|`/pl[uralize]`|Aplica as regras de língua inglesa para singular e plural aos nomes de `Entity`, de `EntitySet` e de `NavigationProperty` no modelo conceitual. Essa opção executará as seguintes ações:<br /><br /> -Torne todos os nomes de `EntityType` singulares.<br />-Torne todos os nomes de `EntitySet` plural.<br />-Para cada `NavigationProperty` que retorna no máximo uma entidade, torne o nome singular.<br />-Para cada `NavigationProperty` que retorna mais de uma entidade, torne o nome plural.|
|`/SuppressForeignKeyProperties or /nofk`|Evita que as colunas de chave estrangeira sejam expostas como propriedades escalares em tipos de entidade no modelo conceitual.|
|`/help` ou `?`|Exibe sintaxe de comando e opções para a ferramenta.|
|`/nologo`|Suprime a notificação de direitos autorais da exibição.|
|`/targetversion:` \<cadeia de caracteres >|A versão do .NET Framework será usada para compilar o código gerado. As versões com suporte são 4 e 4.5. O padrão é 4.|

## <a name="in-this-section"></a>Nesta seção

[Como usar o EdmGen.exe para gerar o modelo e os arquivos de mapeamento](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

[Como usar o EdmGen.exe para gerar o código da camada de objeto](how-to-use-edmgen-exe-to-generate-object-layer-code.md)

[Como usar o EdmGen.exe para validar o modelo e os arquivos de mapeamento](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)

## <a name="see-also"></a>Consulte também

- [Ferramentas de Modelo de Dados de Entidade de ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Modelo de Dados de Entidade](../entity-data-model.md)
- [CSDL, SSDL, and MSL Specifications](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) (Especificações CSDL, SSDL e MSL)
