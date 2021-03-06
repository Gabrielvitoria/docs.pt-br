---
title: Controles com suporte de desenho do proprietário interno
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: f0d4b99f9ee0134fc7334a941dd5ef4fd7ba3df3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930188"
---
# <a name="controls-with-built-in-owner-drawing-support"></a>Controles com suporte de desenho do proprietário interno
Proprietário do desenho nos Windows Forms, que é também conhecido como desenho personalizado, é uma técnica para alterar a aparência visual de certos controles.  
  
> [!NOTE]
> A palavra "controle" neste tópico é usada para significar classes que derivam de um <xref:System.Windows.Forms.Control> ou <xref:System.ComponentModel.Component>.  
  
 Normalmente, o Windows manipula a pintura automaticamente usando configurações de propriedade <xref:System.Windows.Forms.Control.BackColor%2A> , como para determinar a aparência de um controle. Com o desenho do proprietário, assumir o processo de pintura, alterando os elementos que não estão disponíveis usando propriedades de aparência. Por exemplo, muitos controles permitem que você defina a cor do texto que é exibido, mas você está limitado a uma única cor. Desenho do proprietário permite que você faça coisas como parte do texto de exibição em preto e parte em vermelho.  
  
 Na prática, o desenho do proprietário é semelhante ao desenho de gráficos em um formulário. Por exemplo, você pode usar métodos gráficos em um manipulador para o evento do <xref:System.Windows.Forms.Control.Paint> formulário para emular um `ListBox` controle, mas você teria que escrever seu próprio código para lidar com toda a interação do usuário. Com o desenho do proprietário, o controle usa seu código para desenhar seu conteúdo, mas caso contrário retém todos os seus recursos intrínsecos. Você pode usar métodos gráficos para desenhar cada item no controle ou personalizar alguns aspectos de cada item enquanto você usa a aparência padrão para outros aspectos de cada item.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Desenho do proprietário no Controle dos Windows Forms  
 Para executar o desenho do proprietário na controles que oferecem suporte a ele, você normalmente define uma propriedade e manipular um ou mais eventos.  
  
 A maioria dos controles têm de desenho do proprietário que suporte uma propriedade `OwnerDraw` ou `DrawMode` que indica se o controle será aumentará seu evento ou eventos de desenho quando ela pinta a si mesma.  
  
 Controles que não têm uma propriedade `OwnerDraw` ou `DrawMode`, incluem o `DataGridView` controle, que fornece eventos de desenho que ocorrem automaticamente e o `ToolStrip` controle, que é desenhado usando uma classe de renderização externa que tem seus próprios eventos relacionados ao desenho.  
  
 Há muitos tipos diferentes de eventos de desenho, mas ocorre um evento típico de desenho para desenhar um único item em um controle. O manipulador de eventos recebe um `EventArgs` objeto que contém informações sobre o item que está sendo desenhado e ferramentas que você pode usar para desenhá-lo. Por exemplo, esse objeto normalmente contém o número de índice do item dentro de sua coleção pai <xref:System.Drawing.Rectangle> , um que indica os limites de exibição do item <xref:System.Drawing.Graphics> e um objeto para chamar métodos de pintura. Em alguns casos, o `EventArgs` objeto fornece informações adicionais sobre o item e os métodos que você pode chamar para pintar alguns aspectos do item por padrão, como a tela de fundo ou um retângulo de foco.  
  
 Para criar um controle reutilizável que contém as personalizações desenhados pelo proprietário, crie uma nova classe que deriva de uma classe de controle que dá suporte ao desenho do proprietário. Em vez de manipular eventos de desenho, incluir o código de desenho do proprietário em substituições de método ou métodos apropriados de `On` *EventName* na nova classe. Certifique-se de que você chamar o método ou métodos da classe base `On` *EventName* nesse caso, para que os usuários de seu controle possam manipular eventos de desenho do proprietário e fornecer personalização adicional.  
  
 O Windows Forms a seguir controla desenho do proprietário em todas as versões do .NET Framework:  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <xref:System.Windows.Forms.MenuItem>(usado por <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu>)  
  
- <xref:System.Windows.Forms.TabControl>  
  
 Os controles a seguir dão suporte ao desenho do proprietário somente no .NET Framework 2,0:  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 Os seguintes controles dão suporte ao desenho do proprietário e são novos no .NET Framework 2,0:  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 As seções a seguir fornecem detalhes adicionais para cada um desses controles.  
  
### <a name="listbox-and-combobox-controls"></a>Controles de Caixa de Combinação e Caixa de listagem  
 Os <xref:System.Windows.Forms.ListBox> controles <xref:System.Windows.Forms.ComboBox> e permitem que você desenhe itens individuais no controle em um só tamanho ou em tamanhos variados.  
  
> [!NOTE]
> Embora o <xref:System.Windows.Forms.CheckedListBox> controle seja derivado <xref:System.Windows.Forms.ListBox> do controle, ele não dá suporte ao desenho do proprietário.  
  
 Para desenhar cada item com o mesmo tamanho, defina `DrawMode` a propriedade <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> como e manipule `DrawItem` o evento.  
  
 Para desenhar cada item usando um tamanho diferente, defina a `DrawMode` Propriedade como <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> e manipule os `MeasureItem` eventos e `DrawItem` . O evento `MeasureItem` permite indicar o tamanho de um item antes do evento `DrawItem` ocorrer para aquele item.  
  
 Para obter mais informações, incluindo exemplos de código, consulte os seguintes tópicos:  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [Como: Criar texto de tamanho variável em um controle ComboBox](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>Componente do MenuItem  
 O <xref:System.Windows.Forms.MenuItem> componente representa um único item de menu em <xref:System.Windows.Forms.MainMenu> um <xref:System.Windows.Forms.ContextMenu> componente ou.  
  
 Para desenhar um <xref:System.Windows.Forms.MenuItem>, defina sua `OwnerDraw` Propriedade como `true` e manipule seu `DrawItem` evento. Para personalizar o tamanho do item de menu antes do evento `DrawItem` ocorrer, identifique os eventos `MeasureItem` do item.  
  
 Para obter mais informações, incluindo exemplos de código, consulte os seguintes tópicos de referência:  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>Controle TabControl  
 O <xref:System.Windows.Forms.TabControl> controle permite que você desenhe guias individuais no controle. O desenho do proprietário afeta apenas as guias; o <xref:System.Windows.Forms.TabPage> conteúdo não é afetado.  
  
 Para desenhar cada guia em um <xref:System.Windows.Forms.TabControl>, defina a `DrawMode` Propriedade como <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> e manipule o `DrawItem` evento. Esse evento ocorre uma vez para cada guia somente quando a guia estiver visível no controle.  
  
 Para obter mais informações, incluindo exemplos de código, consulte os seguintes tópicos de referência:  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>Componente ToolTip  
 O <xref:System.Windows.Forms.ToolTip> componente permite que você desenhe toda a dica de ferramenta quando ela é exibida.  
  
 Para desenhar um <xref:System.Windows.Forms.ToolTip>, defina sua `OwnerDraw` Propriedade como `true` e manipule seu `Draw` evento. Para <xref:System.Windows.Forms.ToolTip> personalizar o tamanho do antes de o `Draw` evento ocorrer, manipule o `Popup` evento e defina a <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> Propriedade no manipulador de eventos.  
  
 Para obter mais informações, incluindo exemplos de código, consulte os seguintes tópicos de referência:  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>Controle ListView  
 O <xref:System.Windows.Forms.ListView> controle permite que você desenhe itens individuais, subitens e cabeçalhos de coluna no controle.  
  
 Para habilitar o controle de desenho do proprietário, defina a propriedade `OwnerDraw` para `true`.  
  
 Para desenhar cada item no controle, identifique o evento `DrawItem`.  
  
 Para desenhar cada subitem ou cabeçalho de coluna no controle quando a <xref:System.Windows.Forms.ListView.View%2A> propriedade é definida como <xref:System.Windows.Forms.View.Details>, manipule os `DrawSubItem` eventos `DrawColumnHeader` e.  
  
 Para obter mais informações, incluindo exemplos de código, consulte os seguintes tópicos de referência:  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>Controle TreeView  
 O <xref:System.Windows.Forms.TreeView> controle permite que você desenhe nós individuais no controle.  
  
 Para desenhar apenas o texto exibido em cada nó, defina a `DrawMode` Propriedade como <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> e manipule o `DrawNode` evento para desenhar o texto.  
  
 Para desenhar todos os elementos de cada nó, defina `DrawMode` a propriedade <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> como e manipule `DrawNode` o evento para desenhar os elementos necessários, como texto, ícones, caixas de seleção, sinais de adição e subtração e linhas conectando os nós.  
  
 Para obter mais informações, incluindo exemplos de código, consulte os seguintes tópicos de referência:  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>Controle DataGridView  
 O <xref:System.Windows.Forms.DataGridView> controle permite que você desenhe células e linhas individuais no controle.  
  
 Para desenhar células individuais, identifique o evento `CellPainting`.  
  
 Para desenhar linhas individuais ou elementos de linhas, identifique um ou ambos os eventos `RowPrePaint` e `RowPostPaint`. O evento `RowPrePaint` ocorre antes das células em uma linha serem pintadas e o evento `RowPostPaint` ocorre depois que as células são pintadas. Você pode identificar ambos os eventos e o evento `CellPainting` para pintar a tela de fundo de linha, células individuais e primeiro plano linha separadamente ou você pode fornecer personalizações específicas em que você precisa deles e use a exibição padrão para outros elementos da linha.  
  
 Para obter mais informações, incluindo exemplos de código, consulte os seguintes tópicos:  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [Como: Personalizar a aparência das células no controle Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [Como: Personalizar a aparência das linhas no controle Windows Forms DataGridView](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>Controle ToolStrip  
 <xref:System.Windows.Forms.ToolStrip>e os controles derivados permitem que você personalize qualquer aspecto de sua aparência.  
  
 Para fornecer renderização personalizada para <xref:System.Windows.Forms.ToolStrip> controles, defina a `Renderer` propriedade de um <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>ou <xref:System.Windows.Forms.ToolStripContentPanel> para um `ToolStripRenderer` objeto e manipule um ou mais dos muitos eventos de desenho fornecidos pelo `ToolStripRenderer` classe. Como alternativa, defina uma `Renderer` Propriedade como uma instância de sua própria classe derivada de `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>ou <xref:System.Windows.Forms.ToolStripSystemRenderer> que implemente ou substitua métodos `On` *EventName* específicos.  
  
 Para obter mais informações, incluindo exemplos de código, consulte os seguintes tópicos:  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [Como: Criar e definir um renderizador personalizado para o controle ToolStrip no Windows Forms](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [Como: Desenho personalizado de um controle ToolStrip](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>Consulte também

- [Controles a serem usados nos Windows Forms](controls-to-use-on-windows-forms.md)
