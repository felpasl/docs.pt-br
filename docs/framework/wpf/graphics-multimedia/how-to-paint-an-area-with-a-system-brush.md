---
title: "Como pintar uma área com um pincel de sistema"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 355df3718d90768cdfa8bc9780c44c19eb4bf9bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>Como pintar uma área com um pincel de sistema
O <xref:System.Windows.SystemColors> classe fornece acesso a sistema pincéis e cores, como <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, e <xref:System.Windows.SystemColors.DesktopBrush%2A>. Um pincel de sistema é um <xref:System.Windows.Media.SolidColorBrush> objeto que pinta uma área com a cor de sistema especificado. Um pincel do sistema sempre produz um preenchimento sólido; ele não pode ser usado para criar um gradiente.  
  
 Você pode usar pincéis do sistema como um recurso dinâmico ou estático. Use um recurso dinâmico se desejar que o pincel seja atualizado automaticamente se o usuário alterar o pincel do sistema enquanto o aplicativo está em execução; caso contrário, use um recurso estático. A classe SystemColors contém uma variedade de propriedades estáticas que seguem uma convenção de nomenclatura estrita:  
  
-   *\<SystemColor>*Pincel  
  
     Obtém uma referência estática a uma <xref:System.Windows.Media.SolidColorBrush> de cor do sistema especificada.  
  
-   *\<SystemColor>*BrushKey  
  
     Obtém uma referência dinâmica para um <xref:System.Windows.Media.SolidColorBrush> de cor do sistema especificada.  
  
-   *\<SystemColor>*Cor  
  
     Obtém uma referência estática a uma <xref:System.Windows.Media.Color> estrutura de cor do sistema especificada.  
  
-   *\<SystemColor>*ColorKey  
  
     Obtém uma referência dinâmica para o <xref:System.Windows.Media.Color> estrutura de cor do sistema especificada.  
  
 Uma cor do sistema é um <xref:System.Windows.Media.Color> estrutura que pode ser usada para configurar um pincel. Por exemplo, você pode criar um gradiente usando cores do sistema definindo o <xref:System.Windows.Media.GradientStop.Color%2A> propriedades de um <xref:System.Windows.Media.LinearGradientBrush> paradas de gradiente do objeto com cores do sistema. Para obter um exemplo, consulte [usar cores do sistema em um gradiente](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa uma referência de pincel de sistema dinâmico para definir a tela de fundo de um botão.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 O exemplo a seguir usa uma referência de pincel de sistema estático para definir a tela de fundo de um botão.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Para obter um exemplo mostrando como usar uma cor do sistema em um gradiente, consulte [usar cores do sistema em um gradiente](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="see-also"></a>Consulte também  
 [Usar cores do sistema em um gradiente](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [Visão geral da pintura com cores sólidas e gradientes](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)