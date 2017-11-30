---
title: "Suporte de automação de interface de usuário para o tipo de controle TitleBar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control types, Title Bar
- Title Bar control type
- UI Automation, Title Bar control type
ms.assetid: 3b7a4e13-0305-45d5-bc33-1f4133c50782
caps.latest.revision: "21"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: ff2eaccb63f790919025ab4a12b23fced3e5b256
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-titlebar-control-type"></a><span data-ttu-id="f8d5a-102">Suporte de automação de interface de usuário para o tipo de controle TitleBar</span><span class="sxs-lookup"><span data-stu-id="f8d5a-102">UI Automation Support for the TitleBar Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="f8d5a-103">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f8d5a-104">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="f8d5a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f8d5a-105">Este tópico fornece informações sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] suporte para o tipo de controle TitleBar.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the TitleBar control type.</span></span> <span data-ttu-id="f8d5a-106">Em [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], um tipo de controle é um conjunto de condições que um controle precisa atender para usar o <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> propriedade.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="f8d5a-107">As condições incluem diretrizes específicas para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] estrutura de árvore [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] valores de propriedade e padrões de controle.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values and control patterns.</span></span>  
  
 <span data-ttu-id="f8d5a-108">Controles da barra de título representam títulos ou barras de legenda em uma janela.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-108">Title bar controls represent titles or caption bars in a window.</span></span>  
  
 <span data-ttu-id="f8d5a-109">As seções a seguir definem as [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eventos para o tipo de controle TitleBar, propriedades, padrões de controle e estrutura de árvore.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-109">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the TitleBar control type.</span></span> <span data-ttu-id="f8d5a-110">O [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos se aplicam a todos os controles de barra de título, se [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], ou [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8d5a-110">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all title bar controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="f8d5a-111">Estrutura de árvore de automação da interface do usuário necessário</span><span class="sxs-lookup"><span data-stu-id="f8d5a-111">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="f8d5a-112">A tabela a seguir descreve o modo de exibição de controle e exibição de conteúdo de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] controles de árvore referente a barra de título e descreve o que pode ser contido em cada modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-112">The following table depicts the control view and the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to title bar controls and describes what can be contained in each view.</span></span> <span data-ttu-id="f8d5a-113">Para obter mais informações sobre o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de árvore, consulte [visão geral de árvore de automação de interface do usuário](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f8d5a-113">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="f8d5a-114">Exibição de controle</span><span class="sxs-lookup"><span data-stu-id="f8d5a-114">Control View</span></span>|<span data-ttu-id="f8d5a-115">Exibição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="f8d5a-115">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="f8d5a-116">Barra de título</span><span class="sxs-lookup"><span data-stu-id="f8d5a-116">TitleBar</span></span><br /><br /> <span data-ttu-id="f8d5a-117">-Menu (0 ou 1)</span><span class="sxs-lookup"><span data-stu-id="f8d5a-117">-   Menu (0 or 1)</span></span><br /><span data-ttu-id="f8d5a-118">-Botão (0 ou mais)</span><span class="sxs-lookup"><span data-stu-id="f8d5a-118">-   Button (0 or more)</span></span>|<span data-ttu-id="f8d5a-119">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-119">Not applicable.</span></span> <span data-ttu-id="f8d5a-120">(o controle de barra de título não possui conteúdo.)</span><span class="sxs-lookup"><span data-stu-id="f8d5a-120">(the title bar control has no content.)</span></span>|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="f8d5a-121">Propriedades de automação de interface do usuário necessário</span><span class="sxs-lookup"><span data-stu-id="f8d5a-121">Required UI Automation Properties</span></span>  
 <span data-ttu-id="f8d5a-122">A seguinte tabela lista o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] propriedades cujos valores ou definição é especialmente relevantes para controles de barra de título.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-122">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to TitleBar controls.</span></span> <span data-ttu-id="f8d5a-123">Para obter mais informações sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] propriedades, consulte [propriedades de automação de interface do usuário para clientes](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f8d5a-123">For more information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="f8d5a-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="f8d5a-124"> Property</span></span>|<span data-ttu-id="f8d5a-125">Valor</span><span class="sxs-lookup"><span data-stu-id="f8d5a-125">Value</span></span>|<span data-ttu-id="f8d5a-126">Observações</span><span class="sxs-lookup"><span data-stu-id="f8d5a-126">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="f8d5a-127">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-127">See notes.</span></span>|<span data-ttu-id="f8d5a-128">O valor dessa propriedade deve ser exclusivo em todos os controles em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-128">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="f8d5a-129">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-129">See notes.</span></span>|<span data-ttu-id="f8d5a-130">O retângulo delimitador de uma barra de título deve abranger todos os controles contidos nele.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-130">The bounding rectangle of a title bar must encompass all of the controls contained within it.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="f8d5a-131">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-131">See notes.</span></span>|<span data-ttu-id="f8d5a-132">Suporte se houver um retângulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-132">Supported if there is a bounding rectangle.</span></span> <span data-ttu-id="f8d5a-133">Se não for todo ponto dentro do retângulo delimitador é clicável, e você executa o teste de hit especializado, substituir e forneça um ponto clicável.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-133">If not every point within the bounding rectangle is clickable, and you perform specialized hit testing, then override and provide a clickable point.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="f8d5a-134">False</span><span class="sxs-lookup"><span data-stu-id="f8d5a-134">False</span></span>|<span data-ttu-id="f8d5a-135">Barras de título nunca têm o foco do teclado.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-135">Title bars never have keyboard focus.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|<span data-ttu-id="f8d5a-136">""</span><span class="sxs-lookup"><span data-stu-id="f8d5a-136">""</span></span>|<span data-ttu-id="f8d5a-137">Na barra de título não é conteúda; suas informações textuais são expostas na janela pai.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-137">The title bar is not content; its textual information is exposed on the parent window.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|<span data-ttu-id="f8d5a-138">Consulte as observações.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-138">See notes.</span></span>|<span data-ttu-id="f8d5a-139">O controle de barra de título geralmente não tem um rótulo.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-139">The title bar control usually does not have a label.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="f8d5a-140">Barra de título</span><span class="sxs-lookup"><span data-stu-id="f8d5a-140">TitleBar</span></span>|<span data-ttu-id="f8d5a-141">Esse valor é o mesmo para todas as estruturas de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-141">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="f8d5a-142">"barra de título"</span><span class="sxs-lookup"><span data-stu-id="f8d5a-142">"title bar"</span></span>|<span data-ttu-id="f8d5a-143">Cadeia de caracteres localizada correspondente ao tipo de controle TitleBar.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-143">Localized string corresponding to the TitleBar control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="f8d5a-144">False</span><span class="sxs-lookup"><span data-stu-id="f8d5a-144">False</span></span>|<span data-ttu-id="f8d5a-145">O controle de barra de título nunca tem conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-145">The title bar control is never content.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="f8d5a-146">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f8d5a-146">True</span></span>|<span data-ttu-id="f8d5a-147">O controle de barra de título sempre deve ser um controle.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-147">The title bar control must always be a control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|<span data-ttu-id="f8d5a-148">Depende</span><span class="sxs-lookup"><span data-stu-id="f8d5a-148">Depends</span></span>|<span data-ttu-id="f8d5a-149">Esse controle retornará um valor dependendo se a barra de título é visível na tela.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-149">This control will return a value depending on whether the title bar is visible on the screen.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|<span data-ttu-id="f8d5a-150">""</span><span class="sxs-lookup"><span data-stu-id="f8d5a-150">""</span></span>|<span data-ttu-id="f8d5a-151">Não é necessário para expor o texto de Ajuda.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-151">It is not necessary to expose Help text.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>|<span data-ttu-id="f8d5a-152">""</span><span class="sxs-lookup"><span data-stu-id="f8d5a-152">""</span></span>|<span data-ttu-id="f8d5a-153">Barras de título nunca tem teclas de aceleração.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-153">Title bars never have accelerator keys.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>|<span data-ttu-id="f8d5a-154">""</span><span class="sxs-lookup"><span data-stu-id="f8d5a-154">""</span></span>|<span data-ttu-id="f8d5a-155">O controle de barra de título não tem uma chave de acesso.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-155">The title bar control does not have an access key.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a><span data-ttu-id="f8d5a-156">Padrões de controle de automação de interface do usuário necessário</span><span class="sxs-lookup"><span data-stu-id="f8d5a-156">Required UI Automation Control Patterns</span></span>  
 <span data-ttu-id="f8d5a-157">O tipo de controle TitleBar não é necessário para dar suporte a nenhum padrão de controle.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-157">The TitleBar control type is not required to support any control patterns.</span></span> <span data-ttu-id="f8d5a-158">Sua funcionalidade é exposta através do padrão de controle janela sobre o controle de janela.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-158">Its functionality is exposed through the Window control pattern on the Window control.</span></span>  
  
## <a name="required-ui-automation-events"></a><span data-ttu-id="f8d5a-159">Eventos de automação de interface do usuário necessário</span><span class="sxs-lookup"><span data-stu-id="f8d5a-159">Required UI Automation Events</span></span>  
 <span data-ttu-id="f8d5a-160">A seguinte tabela lista o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eventos que devem ser suportados por todos os controles de barra de título.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-160">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all title bar controls.</span></span> <span data-ttu-id="f8d5a-161">Para obter mais informações sobre eventos, consulte [visão geral sobre eventos de automação de interface do usuário](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f8d5a-161">For more information about events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="f8d5a-162">Evento</span><span class="sxs-lookup"><span data-stu-id="f8d5a-162"> Event</span></span>|<span data-ttu-id="f8d5a-163">Suporte</span><span class="sxs-lookup"><span data-stu-id="f8d5a-163">Support</span></span>|<span data-ttu-id="f8d5a-164">Observações</span><span class="sxs-lookup"><span data-stu-id="f8d5a-164">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<span data-ttu-id="f8d5a-165"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>evento de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-165"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event.</span></span>|<span data-ttu-id="f8d5a-166">Necessária</span><span class="sxs-lookup"><span data-stu-id="f8d5a-166">Required</span></span>|<span data-ttu-id="f8d5a-167">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f8d5a-167">None</span></span>|  
|<span data-ttu-id="f8d5a-168"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>evento de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-168"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event.</span></span>|<span data-ttu-id="f8d5a-169">Necessária</span><span class="sxs-lookup"><span data-stu-id="f8d5a-169">Required</span></span>|<span data-ttu-id="f8d5a-170">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f8d5a-170">None</span></span>|  
|<span data-ttu-id="f8d5a-171"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>evento de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="f8d5a-171"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event.</span></span>|<span data-ttu-id="f8d5a-172">Nunca</span><span class="sxs-lookup"><span data-stu-id="f8d5a-172">Never</span></span>|<span data-ttu-id="f8d5a-173">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f8d5a-173">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="f8d5a-174">Nunca</span><span class="sxs-lookup"><span data-stu-id="f8d5a-174">Never</span></span>|<span data-ttu-id="f8d5a-175">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f8d5a-175">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="f8d5a-176">Necessária</span><span class="sxs-lookup"><span data-stu-id="f8d5a-176">Required</span></span>|<span data-ttu-id="f8d5a-177">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f8d5a-177">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8d5a-178">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f8d5a-178">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.TitleBar>  
 [<span data-ttu-id="f8d5a-179">Visão geral de tipos de controle de automação da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="f8d5a-179">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="f8d5a-180">Visão geral de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="f8d5a-180">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)