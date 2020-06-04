---
title: Publicar um aplicativo de Olá, Mundo do .NET Core com Visual Studio Code
description: A publicação cria o conjunto de arquivos necessários para executar um aplicativo .NET Core.
ms.date: 05/28/2020
ms.openlocfilehash: b49b12bf41e3ea7be8dbc459eb7d9b1fbef25790
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "84246678"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio-code"></a><span data-ttu-id="f5de5-103">Tutorial: publicar um aplicativo de console do .NET Core com o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f5de5-103">Tutorial: Publish a .NET Core console application with Visual Studio Code</span></span>

<span data-ttu-id="f5de5-104">Este tutorial mostra como publicar um aplicativo de console para que outros usuários possam executá-lo.</span><span class="sxs-lookup"><span data-stu-id="f5de5-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="f5de5-105">A publicação cria o conjunto de arquivos necessários para executar um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5de5-105">Publishing creates the set of files that are needed to run an application.</span></span> <span data-ttu-id="f5de5-106">Para implantar os arquivos, copie-os para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="f5de5-106">To deploy the files, copy them to the target machine.</span></span>

<span data-ttu-id="f5de5-107">O CLI do .NET Core é usado para publicar o aplicativo, para que você possa seguir este tutorial com um editor de código diferente de Visual Studio Code se preferir.</span><span class="sxs-lookup"><span data-stu-id="f5de5-107">The .NET Core CLI is used to publish the app, so you can follow this tutorial with a code editor other than Visual Studio Code if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5de5-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f5de5-108">Prerequisites</span></span>

- <span data-ttu-id="f5de5-109">Este tutorial funciona com o aplicativo de console que você cria em [criar um aplicativo de console do .NET Core no Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="f5de5-109">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="f5de5-110">Publicar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="f5de5-110">Publish the app</span></span>

1. <span data-ttu-id="f5de5-111">Abra o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f5de5-111">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="f5de5-112">Abra a pasta do projeto *HelloWorld* que você criou em [criar um aplicativo de console do .net Core no Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="f5de5-112">Open the *HelloWorld* project folder that you created in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="f5de5-113">Escolha **Exibir**  >  **terminal** no menu principal.</span><span class="sxs-lookup"><span data-stu-id="f5de5-113">Choose **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="f5de5-114">O terminal é aberto na pasta *HelloWorld* .</span><span class="sxs-lookup"><span data-stu-id="f5de5-114">The terminal opens in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="f5de5-115">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f5de5-115">Run the following command:</span></span>

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   <span data-ttu-id="f5de5-116">A configuração de compilação padrão é *debug*, portanto, esse comando especifica a configuração da compilação da *versão* .</span><span class="sxs-lookup"><span data-stu-id="f5de5-116">The default build configuration is *Debug*, so this command specifies the *Release* build configuration.</span></span> <span data-ttu-id="f5de5-117">A saída da configuração de Build de versão tem informações de depuração simbólicas mínimas e é totalmente otimizada.</span><span class="sxs-lookup"><span data-stu-id="f5de5-117">The output from the Release build configuration has minimal symbolic debug information and is fully optimized.</span></span>

   <span data-ttu-id="f5de5-118">A saída do comando é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f5de5-118">The command output is similar to the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

   Determining projects to restore...
   All projects are up-to-date for restore.
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a><span data-ttu-id="f5de5-119">Inspecionar os arquivos</span><span class="sxs-lookup"><span data-stu-id="f5de5-119">Inspect the files</span></span>

<span data-ttu-id="f5de5-120">Por padrão, o processo de publicação cria uma implantação dependente de estrutura, que é um tipo de implantação em que o aplicativo publicado é executado em um computador que tem o tempo de execução do .NET Core instalado.</span><span class="sxs-lookup"><span data-stu-id="f5de5-120">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="f5de5-121">Para executar o aplicativo publicado, você pode usar o arquivo executável ou executar o `dotnet HelloWorld.dll` comando em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="f5de5-121">To run the published app you can use the executable file or run the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="f5de5-122">Nas etapas a seguir, você examinará os arquivos criados pelo processo de publicação.</span><span class="sxs-lookup"><span data-stu-id="f5de5-122">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="f5de5-123">Selecione o **Gerenciador** na barra de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="f5de5-123">Select the **Explorer** in the left navigation bar.</span></span>

1. <span data-ttu-id="f5de5-124">Expanda *bin/Release/netcoreapp 3.1/publicar*.</span><span class="sxs-lookup"><span data-stu-id="f5de5-124">Expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Explorer mostrando arquivos publicados":::

   <span data-ttu-id="f5de5-126">Como mostra a imagem, a saída publicada inclui os seguintes arquivos:</span><span class="sxs-lookup"><span data-stu-id="f5de5-126">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="f5de5-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="f5de5-127">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="f5de5-128">Este é o arquivo de dependências de tempo de execução do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5de5-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="f5de5-129">Ele define os componentes do .NET Core e as bibliotecas (incluindo a biblioteca de vínculo dinâmico que contém seu aplicativo) necessárias para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5de5-129">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="f5de5-130">Para obter mais informações, consulte [arquivos de configuração de tempo de execução](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="f5de5-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="f5de5-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="f5de5-131">*HelloWorld.dll*</span></span>

      <span data-ttu-id="f5de5-132">Esta é a versão de [implantação dependente de estrutura](../deploying/deploy-with-cli.md#framework-dependent-deployment) do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5de5-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="f5de5-133">Para executar essa biblioteca de vínculo dinâmico, digite `dotnet HelloWorld.dll` em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="f5de5-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="f5de5-134">Esse método de execução do aplicativo funciona em qualquer plataforma que tenha o tempo de execução do .NET Core instalado.</span><span class="sxs-lookup"><span data-stu-id="f5de5-134">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="f5de5-135">*HelloWorld. exe* (*HelloWorld* no Linux, não criado no MacOS).</span><span class="sxs-lookup"><span data-stu-id="f5de5-135">*HelloWorld.exe* (*HelloWorld* on Linux, not created on macOS.)</span></span>

      <span data-ttu-id="f5de5-136">Esta é a versão [executável dependente de estrutura](../deploying/deploy-with-cli.md#framework-dependent-executable) do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5de5-136">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="f5de5-137">O arquivo é específico do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f5de5-137">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="f5de5-138">*HelloWorld.pdb* (opcional para implantação)</span><span class="sxs-lookup"><span data-stu-id="f5de5-138">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="f5de5-139">Este é o arquivo de símbolos de depuração.</span><span class="sxs-lookup"><span data-stu-id="f5de5-139">This is the debug symbols file.</span></span> <span data-ttu-id="f5de5-140">Não é necessário implantar esse arquivo juntamente com seu aplicativo, embora você deva salvá-lo caso precise depurar a versão publicada do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5de5-140">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="f5de5-141">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="f5de5-141">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="f5de5-142">Este é o arquivo de configuração de tempo de execução do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5de5-142">This is the application's run-time configuration file.</span></span> <span data-ttu-id="f5de5-143">Identifica a versão do .NET Core com base na qual o aplicativo foi criado para ser executado.</span><span class="sxs-lookup"><span data-stu-id="f5de5-143">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="f5de5-144">Você também pode adicionar opções de configuração a ela.</span><span class="sxs-lookup"><span data-stu-id="f5de5-144">You can also add configuration options to it.</span></span> <span data-ttu-id="f5de5-145">Para obter mais informações, consulte [definições de configuração de tempo de execução do .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="f5de5-145">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="f5de5-146">Executar o aplicativo publicado</span><span class="sxs-lookup"><span data-stu-id="f5de5-146">Run the published app</span></span>

1. <span data-ttu-id="f5de5-147">No **Gerenciador**, clique com o botão direito do mouse na pasta de *publicação* (ou <kbd>Ctrl</kbd>+ clique em MacOS) e selecione **abrir no terminal**.</span><span class="sxs-lookup"><span data-stu-id="f5de5-147">In **Explorer**, right-click the *publish* folder (or <kbd>Ctrl</kbd>+click on macOS), and select **Open in Terminal**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Menu de contexto mostrando abrir no terminal":::

1. <span data-ttu-id="f5de5-149">No Windows ou Linux, execute o aplicativo usando o executável.</span><span class="sxs-lookup"><span data-stu-id="f5de5-149">On Windows or Linux, run the app by using the executable.</span></span>

   1. <span data-ttu-id="f5de5-150">No Windows, digite `.\HelloWorld.exe` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f5de5-150">On Windows, enter `.\HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="f5de5-151">No Linux, digite `./HelloWorld` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f5de5-151">On Linux, enter `./HelloWorld` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="f5de5-152">Insira um nome em resposta ao prompt e pressione qualquer tecla para sair.</span><span class="sxs-lookup"><span data-stu-id="f5de5-152">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="f5de5-153">Em qualquer plataforma, execute o aplicativo usando o [`dotnet`](../tools/dotnet.md) comando:</span><span class="sxs-lookup"><span data-stu-id="f5de5-153">On any platform, run the app by using the  [`dotnet`](../tools/dotnet.md) command:</span></span>

   1. <span data-ttu-id="f5de5-154">Insira `dotnet HelloWorld.dll` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f5de5-154">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="f5de5-155">Insira um nome em resposta ao prompt e pressione qualquer tecla para sair.</span><span class="sxs-lookup"><span data-stu-id="f5de5-155">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5de5-156">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f5de5-156">Additional resources</span></span>

- [<span data-ttu-id="f5de5-157">Implantação de aplicativo .NET Core</span><span class="sxs-lookup"><span data-stu-id="f5de5-157">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="f5de5-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f5de5-158">Next steps</span></span>

<span data-ttu-id="f5de5-159">Neste tutorial, você publicou um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="f5de5-159">In this tutorial, you published a console app.</span></span> <span data-ttu-id="f5de5-160">Para saber como criar bibliotecas, consulte [desenvolver bibliotecas com o CLI do .NET Core](libraries.md).</span><span class="sxs-lookup"><span data-stu-id="f5de5-160">To learn how to build libraries, see [Develop libraries with the .NET Core CLI](libraries.md).</span></span>

<!--In the next tutorial, you create a class library.

> [!div class="nextstepaction"]
> [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md)
-->