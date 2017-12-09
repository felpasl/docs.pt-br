---
title: "Forma de selecionar um controle de botão dos Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08b5359446a80da257f5afec07cc70e3d4aad46b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="21870-102">Forma de selecionar um controle de botão dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21870-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="21870-103">Um botão dos Windows Forms pode ser selecionado das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="21870-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="21870-104">Use um mouse para clicar no botão.</span><span class="sxs-lookup"><span data-stu-id="21870-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="21870-105">Invocar o botão <xref:System.Windows.Forms.Control.Click> eventos no código.</span><span class="sxs-lookup"><span data-stu-id="21870-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="21870-106">Mova o foco para o botão pressionando a tecla TAB e, em seguida, escolha o botão pressionando a barra de espaços ou ENTER.</span><span class="sxs-lookup"><span data-stu-id="21870-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="21870-107">Pressione a tecla de acesso (ALT + a letra sublinhada) para o botão.</span><span class="sxs-lookup"><span data-stu-id="21870-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="21870-108">Para obter mais informações sobre chaves de acesso, consulte [Como criar chaves de acesso para controles dos Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="21870-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="21870-109">Se o botão for o botão "Aceitar" do formulário, pressionar ENTER seleciona o botão, mesmo se outro controle tiver o foco — exceto se o outro controle for outro botão, uma caixa de texto de várias linhas ou um controle personalizado que intercepte a tecla enter.</span><span class="sxs-lookup"><span data-stu-id="21870-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="21870-110">Se o botão for o botão "Cancelar" do formulário, pressionar ESC seleciona o botão, mesmo se outro controle tiver o foco.</span><span class="sxs-lookup"><span data-stu-id="21870-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="21870-111">Chamar o <xref:System.Windows.Forms.Button.PerformClick%2A> método para selecionar o botão programaticamente.</span><span class="sxs-lookup"><span data-stu-id="21870-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21870-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="21870-112">See Also</span></span>  
 [<span data-ttu-id="21870-113">Visão geral do controle de botão</span><span class="sxs-lookup"><span data-stu-id="21870-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="21870-114">Como responder a cliques no botão dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21870-114">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="21870-115">Controle de botão</span><span class="sxs-lookup"><span data-stu-id="21870-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)