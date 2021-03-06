---
title: 'Como: Carregar um som de forma assíncrona dentro de um Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 5f533d82fcca07a2b64bdbbfb160a7b2a23ce540
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592375"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a>Como: Carregar um som de forma assíncrona dentro de um Windows Form
O exemplo de código a seguir carrega um som de forma assíncrona de uma URL e é reproduzido em um novo thread.  
  
## <a name="example"></a>Exemplo  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
- Referências aos assemblies Sistema e System.Windows.Forms.  
  
- Se você substituir o nome de arquivo `"http://www.tailspintoys.com/sounds/stop.wav"` com um nome de arquivo válido.  
  
## <a name="robust-programming"></a>Programação robusta  
 Operações de arquivo devem ser incluídas dentro de blocos de tratamento de exceção apropriados.  
  
 As seguintes condições podem causar uma exceção:  
  
- O nome do caminho está malformado. Por exemplo, ele contém caracteres que não são válidos ou é somente um espaço em branco (<xref:System.ArgumentException> classe).  
  
- O caminho é somente leitura (<xref:System.IO.IOException> classe).  
  
- É o nome do caminho `Nothing` (<xref:System.ArgumentNullException> classe).  
  
- O nome do caminho é muito longo (<xref:System.IO.PathTooLongException> classe).  
  
- O caminho não é válido (<xref:System.IO.DirectoryNotFoundException> classe).  
  
- O caminho é apenas um dois-pontos ":" (<xref:System.NotSupportedException> classe).  
  
## <a name="net-framework-security"></a>Segurança do .NET Framework  
 Não tome decisões sobre o conteúdo do arquivo com base no nome do arquivo. Por exemplo, o arquivo `Form1.vb` não pode ser um arquivo de origem do Visual Basic. Verifique todas as entradas antes de usar os dados no seu aplicativo.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [Como: Reproduzir um som de um formulário do Windows](how-to-play-a-sound-from-a-windows-form.md)
