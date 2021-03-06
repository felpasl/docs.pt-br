---
title: 'Como: Criar um formulário MDI com mesclagem de Menu e controles ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 6cbab3c588aa74809a7aef80ae6ffc4c3772069f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646010"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Como: Criar um formulário MDI com mesclagem de Menu e controles ToolStrip
O <xref:System.Windows.Forms?displayProperty=nameWithType> namespace oferece suporte a vários aplicativos MDI (interface MDI) de documento e o <xref:System.Windows.Forms.MenuStrip> controle dá suporte à mesclagem de menu. Formulários MDI também podem <xref:System.Windows.Forms.ToolStrip> controles.  
  
 Há suporte abrangente para este recurso no Visual Studio.  
  
 Consulte também [passo a passo: Criando um formulário MDI com mesclagem de Menu e controles ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir demonstra como usar <xref:System.Windows.Forms.ToolStripPanel> controles com um formulário MDI. O formulário também dá suporte à mesclagem com menus filho.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo de código requer:  
  
-   Referências aos assemblies System.Drawing e System.Windows.Forms.  
  
 Para obter informações sobre como compilar este exemplo da linha de comando para o Visual Basic ou Visual c#, consulte [compilando da linha de comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [criação de linha de comando com csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Você também pode criar este exemplo no Visual Studio colando o código em um novo projeto.  Consulte também [como: Compilar e executar um exemplo de código completa do Windows Forms usando o Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Consulte também
- [Controle ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
