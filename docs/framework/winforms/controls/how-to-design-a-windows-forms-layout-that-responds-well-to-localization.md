---
title: 'Como: Projetar um Layout de formulários do Windows que responde bem à localização'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: 15f290f7d076eede7a8092d7295df810e4e51bf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563516"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Como: Projetar um Layout de formulários do Windows que responde bem à localização
Criação de formulários que estão prontos para serem localizados aumenta a velocidade de desenvolvimento para mercados internacionais. Você pode usar o <xref:System.Windows.Forms.TableLayoutPanel> controle para implementar os layouts que respondem normalmente como controles redimensionam devido a alterações nas suas <xref:System.Windows.Forms.Control.Text%2A> valores de propriedade.  
  
## <a name="example"></a>Exemplo  
 Este formulário demonstra como criar um layout que ajusta proporcionalmente quando você converter valores de cadeia de caracteres exibidos em outros idiomas. Esse processo de conversão é chamado *localização*. Para obter mais informações, consulte [localização](../../../../docs/standard/globalization-localization/localization.md).  
  
 Há um suporte abrangente para esta tarefa no Visual Studio.  Consulte também [passo a passo: Criando um Layout que ajusta proporção para localização](https://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [Como: Alinhar e Alongar um controle em um controle TableLayoutPanel](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [Passo a passo: Organizando controles nos Windows Forms utilizando um FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))  
  
3.  [Como: Abranger linhas e colunas em um controle TableLayoutPanel](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4.  [Como: Editar colunas e linhas em um controle TableLayoutPanel](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5.  [Passo a passo: Realizando tarefas comuns usando Smart Tags no Windows, controles de formulários](https://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))  
  
6.  [Passo a passo: Organizando controles nos Windows Forms utilizando um TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
7.  [Passo a passo: Definindo o layout dos Windows Forms controles com preenchimento, margens e a propriedade AutoSize](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))  
  
8.  [Como: Suporte à localização em formulários do Windows usando AutoSize e o controle TableLayoutPanel](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))  
  
9. [Passo a passo: Criando um formulário do Windows redimensionável para entrada de dados](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Referências aos assemblies System, System.Data, System.Drawing e System.Windows.Forms.  
  
 Para obter informações sobre como compilar este exemplo da linha de comando para o Visual Basic ou Visual c#, consulte [compilando da linha de comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [criação de linha de comando com csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Você também pode criar este exemplo no Visual Studio colando o código em um novo projeto.  Consulte também [como: Compilar e executar um exemplo de código completa do Windows Forms usando o Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Localização](../../../../docs/standard/globalization-localization/localization.md)
