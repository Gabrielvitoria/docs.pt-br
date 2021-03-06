---
title: Comando dotnet run
description: O comando dotnet run oferece uma opção conveniente para executar o aplicativo do código-fonte.
ms.date: 02/19/2020
ms.openlocfilehash: 77282fd8615ef01b7867c1bf0f741c834b6ddb30
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102756"
---
# <a name="dotnet-run"></a>dotnet run

**Este artigo se aplica a:** ✔️ .NET Core 2.x SDK e versões posteriores

## <a name="name"></a>Nome

`dotnet run` – Executa o código-fonte sem qualquer comando de compilação ou inicialização explícito.

## <a name="synopsis"></a>Sinopse

```dotnetcli
dotnet run [-c|--configuration <CONFIGURATION>] [-f|--framework <FRAMEWORK>]
    [--force] [--interactive] [--launch-profile <NAME>] [--no-build]
    [--no-dependencies] [--no-launch-profile] [--no-restore]
    [-p|--project <PATH>] [-r|--runtime <RUNTIME_IDENTIFIER>]
    [-v|--verbosity <LEVEL>] [[--] [application arguments]]

dotnet run -h|--help
```

## <a name="description"></a>Descrição

O comando `dotnet run` fornece uma opção conveniente para executar o aplicativo do código-fonte com um comando. Ele é útil para o desenvolvimento iterativo rápido a partir da linha de comando. O comando depende [`dotnet build`](dotnet-build.md) do comando para construir o código. Os requisitos para a compilação, como o projeto, devem ser restaurado primeiro, e se aplicam a `dotnet run` também.

Os arquivos de saída são gravados no local padrão, que é `bin/<configuration>/<target>`. Por exemplo, se você tiver um aplicativo `netcoreapp2.1` e executar `dotnet run`, a saída será colocada em `bin/Debug/netcoreapp2.1`. Os arquivos são substituídos conforme necessário. Os arquivos temporários são colocados no diretório `obj`.

Se o projeto especificar várias estruturas, a execução de `dotnet run` resultará em um erro, a menos que a opção `-f|--framework <FRAMEWORK>` seja usada para especificar a estrutura.

O comando `dotnet run` é usado no contexto de projetos, não assemblies compilados. Se, em vez disso, você estiver tentando executar uma DLL de aplicativo dependente da estrutura, use [dotnet](dotnet.md) sem um comando. Por exemplo, para executar `myapp.dll`, use:

```dotnetcli
dotnet myapp.dll
```

Para saber mais sobre o driver `dotnet`, veja o tópico [CLI (Ferramentas de Linha de Comando) do .NET Core](index.md).

Para executar o aplicativo, o comando `dotnet run` resolve as dependências do aplicativo que estão fora do runtime compartilhado por meio do cache NuGet. Como ele usa as dependências em cache, não recomendamos usar `dotnet run` para executar aplicativos em produção. Em vez disso, [crie uma implantação](../deploying/index.md) usando o comando [`dotnet publish`](dotnet-publish.md) e implante a saída publicada.

### <a name="implicit-restore"></a>Restauração implícita

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a>Opções

- **`--`**

  Delimita os argumentos para `dotnet run` dos argumentos para o aplicativo que está sendo executado. Todos os argumentos após esse delimitador são passados para o aplicativo que está sendo executado.

- **`-c|--configuration <CONFIGURATION>`**

  Define a configuração da compilação. O padrão para `Debug`a maioria dos projetos é, mas você pode substituir as configurações de configuração de compilação em seu projeto.

- **`-f|--framework <FRAMEWORK>`**

  Compila e executa o aplicativo usando a [estrutura](../../standard/frameworks.md) especificada. A estrutura deve ser especificada no arquivo de projeto.

- **`--force`**

  Forçará todas as dependências a serem resolvidas mesmo se última restauração tiver sido bem-sucedida. A especificação desse sinalizador é o mesmo que a exclusão do arquivo *project.assets.json*.

- **`-h|--help`**

  Imprime uma ajuda breve para o comando.

- **`--interactive`**

  Permite que o comando pare e aguarde a entrada ou uma ação do usuário (por exemplo, para concluir a autenticação). Disponível desde o SDK do .NET Core 3.0.

- **`--launch-profile <NAME>`**

  O nome do perfil de inicialização (se houver) a ser usado ao iniciar o aplicativo. Os perfis de lançamento são definidos no arquivo *launchSettings.json* e são tipicamente chamados `Development`, `Staging`e `Production`. Para obter mais informações, consulte [Trabalhando com vários ambientes](/aspnet/core/fundamentals/environments).

- **`--no-build`**

  Não compila o projeto antes da execução. Também define o sinalizador `--no-restore` implicitamente.

- **`--no-dependencies`**

  Ao restaurar um projeto com referências de P2P (projeto a projeto), restaura o projeto raiz, não as referências.

- **`--no-launch-profile`**

  Não tenta usar *launchSettings.json* para configurar o aplicativo.

- **`--no-restore`**

  Não executa uma restauração implícita ao executar o comando.

- **`-p|--project <PATH>`**

  Especifica o caminho do arquivo de projeto a ser executado (nome da pasta ou caminho completo). Se não é especificado, ele usa como padrão o diretório atual.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Especifica o runtime de destino para o qual restaurar os pacotes. Para obter uma lista de RIDs (Identificadores de Runtime), veja o [Catálogo de RIDs](../rid-catalog.md). `-r`opção curta disponível desde .NET Core 3.0 SDK.

- **`-v|--verbosity <LEVEL>`**

  Define o nível de detalhes do comando. Os valores permitidos são `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. O valor padrão é `m`. Disponível desde .NET Core 2.1 SDK.

## <a name="examples"></a>Exemplos

- Execute o projeto no diretório atual:

  ```dotnetcli
  dotnet run
  ```

- Execute o projeto especificado:

  ```dotnetcli
  dotnet run --project ./projects/proj1/proj1.csproj
  ```

- Execute o projeto no diretório atual (o argumento `--help` neste exemplo é passado para o aplicativo, visto que a opção vazia `--` foi usada):

  ```dotnetcli
  dotnet run --configuration Release -- --help
  ```

- Restaure as dependências e as ferramentas para o projeto no diretório atual, apenas mostrando uma saída mínima e, em seguida, execute o projeto (SDK do .NET Core 2.0 e versões posteriores):

  ```dotnetcli
  dotnet run --verbosity m
  ```
