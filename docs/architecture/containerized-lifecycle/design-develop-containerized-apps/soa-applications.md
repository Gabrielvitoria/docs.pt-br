---
title: Aplicativos de SOA
description: Tenha em mente que os contêineres também podem ser uma opção de implantação útil para aplicativos de SOA.
ms.date: 02/15/2019
ms.openlocfilehash: f8619cb50a7d90b911db9ff2c8ef37c3c5fde210
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738380"
---
# <a name="service-oriented-applications"></a>Aplicativos orientados a serviços

A SOA (Arquitetura Orientada a Serviços) era um termo usado de maneira exagerada que significava diferentes coisas para diferentes pessoas. Mas, como um denominador comum, a SOA significa que você estrutura a arquitetura de seu aplicativo o decompondo em vários serviços (mais comumente, como serviços HTTP) que podem ser classificados em diferentes tipos, como subsistemas ou, em outros casos, como camadas.

Atualmente, é possível implantar esses serviços como contêineres do Docker, que resolve problemas de implantação, porque todas as dependências estão incluídas na imagem de contêiner. No entanto, quando precisar expandir SOAs, você poderá encontrar desafios se estiver implantando com base em instâncias únicas. Esse desafio pode ser solucionado usando softwares de clustering ou um orquestrador do Docker. Vamos examinar mais detalhadamente os orquestradores na próxima seção, quando explorarmos as abordagens de microsserviços.

Os contêineres do Docker são úteis (mas não necessários) para arquiteturas tradicionais orientadas a serviço e para as arquiteturas de microsserviços mais avançadas.

Ao considerar tudo, as soluções de clustering de contêiner são úteis para uma arquitetura de SOA tradicional e para uma arquitetura de microsserviços mais avançada na qual cada microsserviço tem seu próprio modelo de dados. E graças a vários bancos de dados, você também pode dimensionar o nível de dados em vez de trabalhar com bancos de dados monolíticos compartilhados pelos serviços SOA. No entanto, a discussão sobre divisão dos dados é puramente sobre arquitetura e design.

>[!div class="step-by-step"]
>[Próximo](state-and-data-in-docker-applications.md)
>[anterior](orchestrate-high-scalability-availability.md)
