---
title: 'Como: Congelar colunas no controle DataGridView do Windows Forms usando o Designer'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: 814eea9bbbee3e1a585eda67ec85d86994d8ce23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539812"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Como: Congelar colunas no controle DataGridView do Windows Forms usando o Designer
Quando os usuários exibem os dados exibidos em um Windows Forms <xref:System.Windows.Forms.DataGridView> controle, às vezes elas precisam para se referir a uma única coluna ou conjunto de colunas com frequência. Por exemplo, quando você exibe uma tabela de informações do cliente que contém várias colunas, é útil exibir o nome do cliente em todos os momentos, enquanto permite que outras colunas rolem para fora da região visível.  
  
 Para obter esse comportamento, você pode congelar colunas no controle. Quando você congela uma coluna, todas as colunas à esquerda (ou à direita em scripts de idioma da direita para esquerda) são congeladas também. Colunas congeladas permanecerão no local enquanto todas as outras colunas podem rolar. Se a reordenação de coluna estiver habilitada, as colunas congeladas serão tratadas como um grupo diferente das colunas não congeladas. Os usuários podem reposicionar colunas em um dos grupos, mas não poderão mover uma coluna de um grupo para outro.  
  
 O procedimento a seguir exige um **aplicativo do Windows** projeto com um formulário que contém um <xref:System.Windows.Forms.DataGridView> controle. Para obter informações sobre como configurar um projeto desse tipo, consulte [como: Criar um projeto de aplicativo do Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [como: Adicionar controles ao Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas. Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**. Para obter mais informações, confira [Personalizar o IDE do Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-freeze-a-column-using-the-designer"></a>Para congelar uma coluna usando o designer  
  
1.  Clique no glifo de marca inteligente (![glifo de Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) no canto superior direito dos <xref:System.Windows.Forms.DataGridView> controle e, em seguida, selecione **Editar colunas**.  
  
2.  Selecione uma coluna na lista **Colunas Selecionadas**.  
  
3.  No **propriedades da coluna** grade, defina o <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> propriedade `true`.  
  
    > [!NOTE]
    >  Você também pode congelar uma coluna ao adicioná-la selecionando a caixa de seleção **Congelada** na caixa de diálogo **Adicionar Coluna**.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [Como: Adicionar e remover colunas no controle DataGridView do Windows Forms usando o Designer](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Como: Habilitar a reorganização de colunas no controle DataGridView do Windows Forms usando o Designer](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)
- [Como: Exibir o texto da direita para a esquerda nos Windows Forms para globalização](https://msdn.microsoft.com/library/f0663385-2354-4c65-8676-706422283b14)
- [Como: Criar um projeto de aplicativo do Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)
- [Como: Adicionar controles ao Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
