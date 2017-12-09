---
title: Como herdar de controles dos Windows Forms existentes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e6133576d65e95ac42a1680de152d84892e2c5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="9929a-102">Como herdar de controles dos Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="9929a-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="9929a-103">Se você quiser estender a funcionalidade de um controle existente, poderá criar um controle derivado de um controle existente por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="9929a-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="9929a-104">Ao herdar de um controle existente, você herda todas as funcionalidades e propriedades visuais desse controle.</span><span class="sxs-lookup"><span data-stu-id="9929a-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="9929a-105">Por exemplo, se você estivesse criando um controle que é herdado de <xref:System.Windows.Forms.Button>, o novo controle seria e funcionam exatamente como um padrão <xref:System.Windows.Forms.Button> controle.</span><span class="sxs-lookup"><span data-stu-id="9929a-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="9929a-106">Dessa forma, você poderia estender ou modificar a funcionalidade de seu novo controle por meio da implementação de métodos e propriedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="9929a-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="9929a-107">Em alguns controles, você também pode alterar a aparência visual do seu controle herdado, substituindo seu <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="9929a-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9929a-108">As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas.</span><span class="sxs-lookup"><span data-stu-id="9929a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9929a-109">Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="9929a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9929a-110">Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="9929a-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="9929a-111">Criar um controle herdado</span><span class="sxs-lookup"><span data-stu-id="9929a-111">To create an inherited control</span></span>  
  
1.  <span data-ttu-id="9929a-112">Para criar um novo projeto de **Aplicativo do Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="9929a-112">Create a new **Windows Forms Application** project.</span></span>  
  
2.  <span data-ttu-id="9929a-113">No menu **Projeto**, escolha **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="9929a-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="9929a-114">A caixa de diálogo **Adicionar Novo Item** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9929a-114">The **Add New Item** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="9929a-115">Na caixa de diálogo **Adicionar Novo Item**, clique duas vezes em **Controle personalizado**.</span><span class="sxs-lookup"><span data-stu-id="9929a-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="9929a-116">Um novo controle personalizado será adicionado ao projeto.</span><span class="sxs-lookup"><span data-stu-id="9929a-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="9929a-117">Se você usar o Visual Basic, no **Gerenciador de Soluções**, clique em **Mostrar todos os arquivos**.</span><span class="sxs-lookup"><span data-stu-id="9929a-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="9929a-118">Expanda CustomControl1.vb e abra CustomControl1.Designer.vb no Editor de Código.</span><span class="sxs-lookup"><span data-stu-id="9929a-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5.  <span data-ttu-id="9929a-119">Se você estiver usando C#, abra CustomControl1.cs no Editor de Código.</span><span class="sxs-lookup"><span data-stu-id="9929a-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6.  <span data-ttu-id="9929a-120">Localize a declaração de classe que herda de <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="9929a-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7.  <span data-ttu-id="9929a-121">Altere a classe base para o controle do qual você deseja herdar.</span><span class="sxs-lookup"><span data-stu-id="9929a-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="9929a-122">Por exemplo, se você deseja herdar de <xref:System.Windows.Forms.Button>, altere a declaração de classe para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9929a-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  <span data-ttu-id="9929a-123">Se você estiver usando Visual Basic, salve e feche CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="9929a-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="9929a-124">Abra CustomControl1.vb no Editor de Código.</span><span class="sxs-lookup"><span data-stu-id="9929a-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="9929a-125">Implemente os métodos ou propriedades personalizados que o controle incorporará.</span><span class="sxs-lookup"><span data-stu-id="9929a-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="9929a-126">Se você quiser modificar a aparência do gráfica de seu controle, substituir o <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="9929a-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9929a-127">Substituindo <xref:System.Windows.Forms.Control.OnPaint%2A> não permitirá que você modifique a aparência de todos os controles.</span><span class="sxs-lookup"><span data-stu-id="9929a-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="9929a-128">Esses controles que têm todas as sua pintura feita pelo Windows (por exemplo, <xref:System.Windows.Forms.TextBox>) nunca chamar seus <xref:System.Windows.Forms.Control.OnPaint%2A> método e, portanto, nunca use o código personalizado.</span><span class="sxs-lookup"><span data-stu-id="9929a-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="9929a-129">Consulte a documentação de ajuda para o controle específico que você deseja modificar para ver se o <xref:System.Windows.Forms.Control.OnPaint%2A> método está disponível.</span><span class="sxs-lookup"><span data-stu-id="9929a-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="9929a-130">Para obter uma lista de todos os controles do Windows Forms, consulte [Controles a serem usados no Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9929a-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="9929a-131">Se um controle não possui <xref:System.Windows.Forms.Control.OnPaint%2A> listado como um método de membro, você não pode alterar sua aparência substituir esse método.</span><span class="sxs-lookup"><span data-stu-id="9929a-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="9929a-132">Para obter mais informações sobre pintura personalizada, consulte [Pintura e renderização de controle personalizado](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="9929a-132">For more information about custom painting, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. <span data-ttu-id="9929a-133">Salve e teste seu controle.</span><span class="sxs-lookup"><span data-stu-id="9929a-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9929a-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9929a-134">See Also</span></span>  
 [<span data-ttu-id="9929a-135">Variedades de Controles Personalizados</span><span class="sxs-lookup"><span data-stu-id="9929a-135">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="9929a-136">Como herdar da classe de controle</span><span class="sxs-lookup"><span data-stu-id="9929a-136">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="9929a-137">Como herdar da classe UserControl</span><span class="sxs-lookup"><span data-stu-id="9929a-137">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="9929a-138">Como Criar Controles para o Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9929a-138">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="9929a-139">Solucionando problemas de manipuladores de eventos herdados no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9929a-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="9929a-140">Passo a passo: herdando um controle dos Windows Forms com Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9929a-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="9929a-141">Passo a passo: herdando um controle dos Windows Forms com Visual C#</span><span class="sxs-lookup"><span data-stu-id="9929a-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)