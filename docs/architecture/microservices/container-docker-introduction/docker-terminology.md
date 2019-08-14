---
title: Terminologia do Docker
description: Arquitetura de microsserviços do .NET para aplicativos .NET em contêineres | Terminologia do Docker
ms.date: 01/07/2019
ms.openlocfilehash: 700cd9a00c30b0a5fc87f9ffcd63821bb578b0cc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674823"
---
# <a name="docker-terminology"></a><span data-ttu-id="ccf30-103">Terminologia do Docker</span><span class="sxs-lookup"><span data-stu-id="ccf30-103">Docker terminology</span></span>

<span data-ttu-id="ccf30-104">Esta seção lista os termos e definições que você deve conhecer antes de se aprofundar no Docker.</span><span class="sxs-lookup"><span data-stu-id="ccf30-104">This section lists terms and definitions you should be familiar with before getting deeper into Docker.</span></span> <span data-ttu-id="ccf30-105">Para obter mais definições, consulte o amplo [glossário](https://docs.docker.com/glossary/) fornecido pelo Docker.</span><span class="sxs-lookup"><span data-stu-id="ccf30-105">For further definitions, see the extensive [glossary](https://docs.docker.com/glossary/) provided by Docker .</span></span>

<span data-ttu-id="ccf30-106">**Imagem de contêiner**: Um pacote com todas as dependências e informações necessárias para criar um contêiner.</span><span class="sxs-lookup"><span data-stu-id="ccf30-106">**Container image**: A package with all the dependencies and information needed to create a container.</span></span> <span data-ttu-id="ccf30-107">Uma imagem inclui todas as dependências (como estruturas), além da configuração de implantação e execução a ser usada por um tempo de execução de contêiner.</span><span class="sxs-lookup"><span data-stu-id="ccf30-107">An image includes all the dependencies (such as frameworks) plus deployment and execution configuration to be used by a container runtime.</span></span> <span data-ttu-id="ccf30-108">Geralmente, uma imagem deriva de várias imagens base que são camadas empilhadas umas sobre as outras para formar o sistema de arquivos do contêiner.</span><span class="sxs-lookup"><span data-stu-id="ccf30-108">Usually, an image derives from multiple base images that are layers stacked on top of each other to form the container's filesystem.</span></span> <span data-ttu-id="ccf30-109">Uma imagem é imutável depois de ser criada.</span><span class="sxs-lookup"><span data-stu-id="ccf30-109">An image is immutable once it has been created.</span></span>

<span data-ttu-id="ccf30-110">**Dockerfile**: Um arquivo de texto que contém instruções sobre como criar uma imagem do Docker.</span><span class="sxs-lookup"><span data-stu-id="ccf30-110">**Dockerfile**: A text file that contains instructions for how to build a Docker image.</span></span> <span data-ttu-id="ccf30-111">É como um script em lotes, a primeira linha declara a imagem base com a qual começar e, em seguida, siga as instruções para instalar os programas necessários, copie os arquivos e assim por diante, até que você obtenha o ambiente de trabalho que precisa.</span><span class="sxs-lookup"><span data-stu-id="ccf30-111">It's like a batch script, the first line states the base image to begin with and then follow the instructions to install required programs, copy files and so on, until you get the working environment you need.</span></span>

<span data-ttu-id="ccf30-112">**Build**: A ação de criação de uma imagem de contêiner com base nas informações e no contexto fornecidos pelo Dockerfile, além de arquivos adicionais na pasta em que a imagem é criada.</span><span class="sxs-lookup"><span data-stu-id="ccf30-112">**Build**: The action of building a container image based on the information and context provided by its Dockerfile, plus additional files in the folder where the image is built.</span></span> <span data-ttu-id="ccf30-113">Você pode criar imagens com o comando **docker build** do Docker.</span><span class="sxs-lookup"><span data-stu-id="ccf30-113">You can build images with the Docker **docker build** command.</span></span> 

<span data-ttu-id="ccf30-114">**Contêiner**: Uma instância de uma imagem do Docker.</span><span class="sxs-lookup"><span data-stu-id="ccf30-114">**Container**: An instance of a Docker image.</span></span> <span data-ttu-id="ccf30-115">Um contêiner representa a execução de um único aplicativo, processo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="ccf30-115">A container represents the execution of a single application, process, or service.</span></span> <span data-ttu-id="ccf30-116">Consiste no conteúdo de uma imagem do Docker, um ambiente de execução e um conjunto padrão de instruções.</span><span class="sxs-lookup"><span data-stu-id="ccf30-116">It consists of the contents of a Docker image, an execution environment, and a standard set of instructions.</span></span> <span data-ttu-id="ccf30-117">Ao dimensionar um serviço, você cria várias instâncias de um contêiner da mesma imagem.</span><span class="sxs-lookup"><span data-stu-id="ccf30-117">When scaling a service, you create multiple instances of a container from the same image.</span></span> <span data-ttu-id="ccf30-118">Ou um trabalho em lotes pode criar vários contêineres da mesma imagem, passando parâmetros diferentes para cada instância.</span><span class="sxs-lookup"><span data-stu-id="ccf30-118">Or a batch job can create multiple containers from the same image, passing different parameters to each instance.</span></span>

<span data-ttu-id="ccf30-119">**Volumes**: Oferecem um sistema de arquivos gravável que pode ser usado pelo contêiner.</span><span class="sxs-lookup"><span data-stu-id="ccf30-119">**Volumes**: Offer a writable filesystem that the container can use.</span></span> <span data-ttu-id="ccf30-120">Uma vez que as imagens são somente leitura, mas a maioria dos programas precisam gravar para o sistema de arquivos, os volumes adicionam uma camada gravável sobre a imagem de contêiner, de modo que os programas têm acesso a um sistema de arquivos gravável.</span><span class="sxs-lookup"><span data-stu-id="ccf30-120">Since images are read-only but most programs need to write to the filesystem, volumes add a writable layer, on top of the container image, so the programs have access to a writable filesystem.</span></span> <span data-ttu-id="ccf30-121">O programa não sabe que está acessando um sistema de arquivos em camadas, é apenas o sistema de arquivos como de costume.</span><span class="sxs-lookup"><span data-stu-id="ccf30-121">The program doesn't know it is accessing a layered filesystem, it is just the filesystem as usual.</span></span> <span data-ttu-id="ccf30-122">Os volumes ficam no sistema de host e são gerenciados pelo Docker.</span><span class="sxs-lookup"><span data-stu-id="ccf30-122">Volumes live in the host system and are managed by Docker.</span></span>

<span data-ttu-id="ccf30-123">**Tag**: Uma marca ou um rótulo que pode ser aplicado a imagens, de modo que as diferentes imagens ou versões da mesma imagem (dependendo do número de versão ou do ambiente de destino) possam ser identificadas.</span><span class="sxs-lookup"><span data-stu-id="ccf30-123">**Tag**: A mark or label you can apply to images so that different images or versions of the same image (depending on the version number or the target environment) can be identified.</span></span>

<span data-ttu-id="ccf30-124">**Build de vários estágios**: É uma funcionalidade disponível no Docker 17.05 ou posterior que ajuda a reduzir o tamanho das imagens finais.</span><span class="sxs-lookup"><span data-stu-id="ccf30-124">**Multi-stage Build**: Is a feature, since Docker 17.05 or higher, that helps to reduce the size of the final images.</span></span> <span data-ttu-id="ccf30-125">Em algumas frases, com o build de vários estágios você pode usar, por exemplo, uma imagem base grande contendo o SDK para compilar e publicar o aplicativo e, em seguida, usar a pasta de publicação com uma pequena imagem base somente de tempo de execução para produzir uma imagem final muito menor</span><span class="sxs-lookup"><span data-stu-id="ccf30-125">In a few sentences, with multi-stage build you can use, for example, a large base image, containing the SDK, for compiling and publishing the application and then using the publishing folder with a small runtime-only base image, to produce a much smaller final image</span></span>

<span data-ttu-id="ccf30-126">**Repositório**: Uma coleção de imagens do Docker relacionadas, rotuladas com uma tag que indica a versão da imagem.</span><span class="sxs-lookup"><span data-stu-id="ccf30-126">**Repository (repo)**: A collection of related Docker images, labeled with a tag that indicates the image version.</span></span> <span data-ttu-id="ccf30-127">Alguns repositórios contêm diversas variantes de uma imagem específica, como uma imagem que contém o SDKs (mais pesada), uma imagem que contém somente tempos de execução (mais leves) etc. Essas variantes podem ser marcadas com marcas.</span><span class="sxs-lookup"><span data-stu-id="ccf30-127">Some repos contain multiple variants of a specific image, such as an image containing SDKs (heavier), an image containing only runtimes (lighter), etc. Those variants can be marked with tags.</span></span> <span data-ttu-id="ccf30-128">Um único repositório pode conter variantes de plataforma, como uma imagem do Linux e uma imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="ccf30-128">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span>

<span data-ttu-id="ccf30-129">**Registro**: Um serviço que fornece acesso aos repositórios.</span><span class="sxs-lookup"><span data-stu-id="ccf30-129">**Registry**: A service that provides access to repositories.</span></span> <span data-ttu-id="ccf30-130">O registro padrão para as imagens mais públicas é o [Docker Hub](https://hub.docker.com/) (propriedade da Docker como uma organização).</span><span class="sxs-lookup"><span data-stu-id="ccf30-130">The default registry for most public images is [Docker Hub](https://hub.docker.com/) (owned by Docker as an organization).</span></span> <span data-ttu-id="ccf30-131">Um registro geralmente contém repositórios de várias equipes.</span><span class="sxs-lookup"><span data-stu-id="ccf30-131">A registry usually contains repositories from multiple teams.</span></span> <span data-ttu-id="ccf30-132">As empresas geralmente têm registros privados para armazenar e gerenciar as imagens que criaram.</span><span class="sxs-lookup"><span data-stu-id="ccf30-132">Companies often have private registries to store and manage images they've created.</span></span> <span data-ttu-id="ccf30-133">O Registro de Contêiner do Azure é outro exemplo.</span><span class="sxs-lookup"><span data-stu-id="ccf30-133">Azure Container Registry is another example.</span></span>

<span data-ttu-id="ccf30-134">**Imagem de vários arcos**: Para várias arquiteturas, é uma funcionalidade que simplifica a seleção da imagem apropriada, de acordo com a plataforma em que o Docker está sendo executado; por exemplo, quando um Dockerfile solicita uma imagem base **FROM mcr.microsoft.com/dotnet/core/sdk:2.2** do Registro, na verdade, ele obtém **2.2-sdk-nanoserver-1709**, **2.2-sdk-nanoserver-1803**, **2.2-sdk-nanoserver-1809** ou **2.2-sdk-stretch**, dependendo do sistema operacional e da versão em que o Docker está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="ccf30-134">**Multi-arch image**: For multi-architecture, is a feature that simplifies the selection of the appropriate image, according to the platform where Docker is running, e.g. when a Dockerfile requests a base image **FROM mcr.microsoft.com/dotnet/core/sdk:2.2** from the registry it actually gets **2.2-sdk-nanoserver-1709**, **2.2-sdk-nanoserver-1803**, **2.2-sdk-nanoserver-1809** or **2.2-sdk-stretch**, depending on the operating system and version where Docker is running.</span></span>

<span data-ttu-id="ccf30-135">**Hub do Docker**: Um registro público para fazer upload de imagens e trabalhar com elas.</span><span class="sxs-lookup"><span data-stu-id="ccf30-135">**Docker Hub**: A public registry to upload images and work with them.</span></span> <span data-ttu-id="ccf30-136">O Docker Hub hospeda imagens do Docker, registros públicos ou privados, cria gatilhos e ganchos da Web e integra-se com o GitHub e o Bitbucket.</span><span class="sxs-lookup"><span data-stu-id="ccf30-136">Docker Hub provides Docker image hosting, public or private registries, build triggers and web hooks, and integration with GitHub and Bitbucket.</span></span>

<span data-ttu-id="ccf30-137">**Registro de Contêiner do Azure**: Um recurso público para trabalhar com imagens do Docker e seus componentes no Azure.</span><span class="sxs-lookup"><span data-stu-id="ccf30-137">**Azure Container Registry**: A public resource for working with Docker images and its components in Azure.</span></span> <span data-ttu-id="ccf30-138">Fornece um registro que está perto de suas implantações no Azure e que permite controlar o acesso, tornando possível usar as permissões e os grupos do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ccf30-138">This provides a registry that is close to your deployments in Azure and that gives you control over access, making it possible to use your Azure Active Directory groups and permissions.</span></span>

<span data-ttu-id="ccf30-139">**DTR (Registro Confiável do Docker)** : Um serviço de registro do Docker (do Docker) que pode ser instalado localmente, de modo que ele resida no datacenter e na rede da organização.</span><span class="sxs-lookup"><span data-stu-id="ccf30-139">**Docker Trusted Registry (DTR)**: A Docker registry service (from Docker) that can be installed on-premises so it lives within the organization's datacenter and network.</span></span> <span data-ttu-id="ccf30-140">É conveniente para imagens privadas que devem ser gerenciadas dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="ccf30-140">It is convenient for private images that should be managed within the enterprise.</span></span> <span data-ttu-id="ccf30-141">O Docker Trusted Registry é parte do produto Docker Datacenter.</span><span class="sxs-lookup"><span data-stu-id="ccf30-141">Docker Trusted Registry is included as part of the Docker Datacenter product.</span></span> <span data-ttu-id="ccf30-142">Para saber mais, consulte [Docker Trusted Registry (DTR)](https://docs.docker.com/docker-trusted-registry/overview/).</span><span class="sxs-lookup"><span data-stu-id="ccf30-142">For more information, see [Docker Trusted Registry (DTR)](https://docs.docker.com/docker-trusted-registry/overview/).</span></span>

<span data-ttu-id="ccf30-143">**Docker CE (Community Edition)** : Ferramentas de desenvolvimento para Windows e macOS para criação, execução e teste de contêineres localmente.</span><span class="sxs-lookup"><span data-stu-id="ccf30-143">**Docker Community Edition (CE)**: Development tools for Windows and macOS for building, running, and testing containers locally.</span></span> <span data-ttu-id="ccf30-144">O Docker CE para Windows fornece os ambientes de desenvolvimento para Linux e contêineres do Windows.</span><span class="sxs-lookup"><span data-stu-id="ccf30-144">Docker CE for Windows provides development environments for both Linux and Windows Containers.</span></span> <span data-ttu-id="ccf30-145">O host do Docker do Linux no Windows é baseado em uma máquina virtual [Hyper-V](https://www.microsoft.com/cloud-platform/server-virtualization).</span><span class="sxs-lookup"><span data-stu-id="ccf30-145">The Linux Docker host on Windows is based on a [Hyper-V](https://www.microsoft.com/cloud-platform/server-virtualization) virtual machine.</span></span> <span data-ttu-id="ccf30-146">O host para contêineres do Windows se baseia diretamente no Windows.</span><span class="sxs-lookup"><span data-stu-id="ccf30-146">The host for Windows Containers is directly based on Windows.</span></span> <span data-ttu-id="ccf30-147">Docker CE para Mac baseia-se na estrutura do Apple Hypervisor e o [xhyve hypervisor](https://github.com/mist64/xhyve), que fornece uma máquina virtual do host Linux Docker no Mac OS X. O Docker CE para Windows e Mac substitui o Docker Toolbox, que foi baseado no Oracle VirtualBox.</span><span class="sxs-lookup"><span data-stu-id="ccf30-147">Docker CE for Mac is based on the Apple Hypervisor framework and the [xhyve hypervisor](https://github.com/mist64/xhyve), which provides a Linux Docker host virtual machine on Mac OS X. Docker CE for Windows and for Mac replaces Docker Toolbox, which was based on Oracle VirtualBox.</span></span>

<span data-ttu-id="ccf30-148">**Docker EE (Enterprise Edition)** : Uma versão empresarial das ferramentas do Docker para desenvolvimento no Linux e no Windows.</span><span class="sxs-lookup"><span data-stu-id="ccf30-148">**Docker Enterprise Edition (EE)**: An enterprise-scale version of Docker tools for Linux and Windows development.</span></span>

<span data-ttu-id="ccf30-149">**Compose**: Uma ferramenta de linha de comando e formato de arquivo YAML com metadados para definir e executar aplicativos de vários contêineres.</span><span class="sxs-lookup"><span data-stu-id="ccf30-149">**Compose**: A command-line tool and YAML file format with metadata for defining and running multi-container applications.</span></span> <span data-ttu-id="ccf30-150">Você define um único aplicativo com base em várias imagens com um ou mais arquivos .yml que podem substituir valores dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="ccf30-150">You define a single application based on multiple images with one or more .yml files that can override values depending on the environment.</span></span> <span data-ttu-id="ccf30-151">Depois de criar as definições, você pode implantar todo o aplicativo de vários contêineres com um único comando (docker-compose up), que cria um contêiner por imagem no host do Docker.</span><span class="sxs-lookup"><span data-stu-id="ccf30-151">After you have created the definitions, you can deploy the whole multi-container application with a single command (docker-compose up) that creates a container per image on the Docker host.</span></span>

<span data-ttu-id="ccf30-152">**Cluster**: Uma coleção de hosts do Docker expostos como um único host virtual do Docker, de modo que o aplicativo possa ser dimensionado para várias instâncias dos serviços distribuídos em vários hosts do cluster.</span><span class="sxs-lookup"><span data-stu-id="ccf30-152">**Cluster**: A collection of Docker hosts exposed as if it were a single virtual Docker host, so that the application can scale to multiple instances of the services spread across multiple hosts within the cluster.</span></span> <span data-ttu-id="ccf30-153">Os clusters do Docker podem ser criados com o Kubernetes, o Azure Service Fabric, o Docker Swarm e o Mesosphere DC/OS.</span><span class="sxs-lookup"><span data-stu-id="ccf30-153">Docker clusters can be created with Kubernetes, Azure Service Fabric, Docker Swarm and Mesosphere DC/OS.</span></span>

<span data-ttu-id="ccf30-154">**Orchestrator**: Uma ferramenta que simplifica o gerenciamento de clusters e hosts do Docker.</span><span class="sxs-lookup"><span data-stu-id="ccf30-154">**Orchestrator**: A tool that simplifies management of clusters and Docker hosts.</span></span> <span data-ttu-id="ccf30-155">Os orquestradores permitem gerenciar imagens, contêineres e hosts por meio de uma CLI (interface de linha de comando) ou uma interface do usuário gráfica.</span><span class="sxs-lookup"><span data-stu-id="ccf30-155">Orchestrators enable you to manage their images, containers, and hosts through a command line interface (CLI) or a graphical UI.</span></span> <span data-ttu-id="ccf30-156">É possível gerenciar a rede de contêiner, configurações, balanceamento de carga, descoberta de serviço, alta disponibilidade, configuração de host do Docker e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ccf30-156">You can manage container networking, configurations, load balancing, service discovery, high availability, Docker host configuration, and more.</span></span> <span data-ttu-id="ccf30-157">Um orquestrador é responsável por executar, distribuir, dimensionar e reparar de cargas de trabalho em uma coleção de nós.</span><span class="sxs-lookup"><span data-stu-id="ccf30-157">An orchestrator is responsible for running, distributing, scaling, and healing workloads across a collection of nodes.</span></span> <span data-ttu-id="ccf30-158">Normalmente, produtos de orquestrador são os mesmos que fornecem infraestrutura de cluster, como Kubernetes e Azure Service Fabric, além de outras ofertas no mercado.</span><span class="sxs-lookup"><span data-stu-id="ccf30-158">Typically, orchestrator products are the same products that provide cluster infrastructure, like Kubernetes and Azure Service Fabric, among other offerings in the market.</span></span> 

>[!div class="step-by-step"]
><span data-ttu-id="ccf30-159">[Anterior](docker-defined.md)
>[Próximo](docker-containers-images-registries.md)</span><span class="sxs-lookup"><span data-stu-id="ccf30-159">[Previous](docker-defined.md)
[Next](docker-containers-images-registries.md)</span></span>