---
title: "Encontrar um Elemento de Automação de Interface de Usuário para um Item de Lista"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 16016f5e5b0ab9633f9f8e4ac662838dd7936b18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="f1282-102">Encontrar um Elemento de Automação de Interface de Usuário para um Item de Lista</span><span class="sxs-lookup"><span data-stu-id="f1282-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
>  <span data-ttu-id="f1282-103">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="f1282-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f1282-104">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="f1282-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f1282-105">Este tópico mostra como recuperar um <xref:System.Windows.Automation.AutomationElement> para um item dentro de uma lista quando o índice do item é conhecido.</span><span class="sxs-lookup"><span data-stu-id="f1282-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1282-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f1282-106">Example</span></span>  
 <span data-ttu-id="f1282-107">O exemplo a seguir mostra duas maneiras de recuperar um item especificado de uma lista, uma usando <xref:System.Windows.Automation.TreeWalker> e outra usando <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1282-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="f1282-108">A primeira técnica tende a ser mais rápido para [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controles, mas a segunda é mais rápida para [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] controles.</span><span class="sxs-lookup"><span data-stu-id="f1282-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="f1282-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f1282-109">See Also</span></span>  
 [<span data-ttu-id="f1282-110">Obtendo elementos de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="f1282-110">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)