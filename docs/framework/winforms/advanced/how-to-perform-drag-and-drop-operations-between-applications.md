---
title: "Como executar operações de arrastar e soltar entre aplicativos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 513c6b2a15502625e4b42aeee4947ff36e4bfd17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a><span data-ttu-id="028ef-102">Como executar operações de arrastar e soltar entre aplicativos</span><span class="sxs-lookup"><span data-stu-id="028ef-102">How to: Perform Drag-and-Drop Operations Between Applications</span></span>
<span data-ttu-id="028ef-103">Executar operações de arrastar e soltar entre aplicativos é não diferente de ativar esta ação dentro de um aplicativo, como os dois aplicativos envolvidos se comportem de acordo com o "contrato" estabelecido entre o <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> e <xref:System.Windows.Forms.DragEventArgs.Effect%2A> Propriedades.</span><span class="sxs-lookup"><span data-stu-id="028ef-103">Performing drag-and-drop operations between applications is no different than enabling this action within an application, as long as both applications involved behave according to the "contract" established between the <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> and <xref:System.Windows.Forms.DragEventArgs.Effect%2A> properties.</span></span>  
  
 <span data-ttu-id="028ef-104">No procedimento a seguir, você usará um aplicativo do Windows que você criou e o processador de texto WordPad incluído no sistema operacional Windows para executar operações do tipo "arrastar e soltar" entre aplicativos.</span><span class="sxs-lookup"><span data-stu-id="028ef-104">In the following procedure, you will use a Windows-based application you create and the WordPad word processor that is included with the Windows operating system to perform drag-and-drop operations between applications.</span></span> <span data-ttu-id="028ef-105">O WordPad tem um certo conjunto de efeitos permitidos para o texto que está sendo arrastado e solto; o aplicativo do Windows para o qual o código está sendo escrito funcionará com esses efeitos para que as operações do tipo "arrastar e soltar" possam ser concluídas com êxito.</span><span class="sxs-lookup"><span data-stu-id="028ef-105">WordPad has a certain set of allowed effects for text being dragged and dropped; the Windows-based application you will write code for will work with these effects so that drag-and-drop operations may be completed successfully.</span></span>  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a><span data-ttu-id="028ef-106">Realizar um procedimento do tipo "arrastar e soltar" entre aplicativos</span><span class="sxs-lookup"><span data-stu-id="028ef-106">To perform a drag-and-drop procedure between applications</span></span>  
  
1.  <span data-ttu-id="028ef-107">Criar um novo aplicativo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="028ef-107">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="028ef-108">Adicione um controle <xref:System.Windows.Forms.TextBox> ao seu formulário.</span><span class="sxs-lookup"><span data-stu-id="028ef-108">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
3.  <span data-ttu-id="028ef-109">Configurar o <xref:System.Windows.Forms.TextBox> controle para receber dados soltos.</span><span class="sxs-lookup"><span data-stu-id="028ef-109">Configure the <xref:System.Windows.Forms.TextBox> control to receive dropped data.</span></span>  
  
     <span data-ttu-id="028ef-110">Para obter mais informações, consulte [Instruções passo a passo: executando uma operação do tipo "arrastar e soltar" nos Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="028ef-110">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
4.  <span data-ttu-id="028ef-111">Execute seu aplicativo do Windows e, enquanto o aplicativo está em execução, execute o WordPad.</span><span class="sxs-lookup"><span data-stu-id="028ef-111">Run your Windows-based application, and while the application is running, run WordPad.</span></span>  
  
     <span data-ttu-id="028ef-112">O WordPad é um editor de texto instalado pelo Windows que permite realizar operações do tipo "arrastar e soltar".</span><span class="sxs-lookup"><span data-stu-id="028ef-112">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="028ef-113">Ele pode ser acessado pressionando o botão **Iniciar**, selecionando **Executar** e digitando `WordPad` na caixa de texto da caixa de diálogo **Executar** e clicando em **OK**.</span><span class="sxs-lookup"><span data-stu-id="028ef-113">It is accessible by pressing the **Start** button, selecting **Run**, and then typing `WordPad` into the text box of the **Run** dialog box and clicking **OK**.</span></span>  
  
5.  <span data-ttu-id="028ef-114">Após abrir o WordPad, digite uma cadeia de caracteres de texto nele.</span><span class="sxs-lookup"><span data-stu-id="028ef-114">Once WordPad is open, type a string of text into it.</span></span>  
  
6.  <span data-ttu-id="028ef-115">Usando o mouse, selecione o texto e arraste o texto selecionado para o <xref:System.Windows.Forms.TextBox> controle em seu aplicativo baseado no Windows.</span><span class="sxs-lookup"><span data-stu-id="028ef-115">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.TextBox> control in your Windows-based application.</span></span>  
  
     <span data-ttu-id="028ef-116">Observe que quando você passa o mouse sobre o <xref:System.Windows.Forms.TextBox> controle (e, consequentemente, gera o <xref:System.Windows.Forms.Control.DragEnter> evento), o cursor muda e você pode remover o texto selecionado para o <xref:System.Windows.Forms.TextBox> controle.</span><span class="sxs-lookup"><span data-stu-id="028ef-116">Observe that when you mouse over the <xref:System.Windows.Forms.TextBox> control (and, consequently, raise the <xref:System.Windows.Forms.Control.DragEnter> event), the cursor changes, and you can drop the selected text into the <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
     <span data-ttu-id="028ef-117">Além disso, você pode configurar seu <xref:System.Windows.Forms.TextBox> controle para permitir que cadeias de caracteres de texto a ser arrastadas e soltas no WordPad.</span><span class="sxs-lookup"><span data-stu-id="028ef-117">Additionally, you can configure your <xref:System.Windows.Forms.TextBox> control to allow text strings to be dragged and dropped into WordPad.</span></span> <span data-ttu-id="028ef-118">Para obter mais informações, consulte [Instruções passo a passo: executando uma operação do tipo "arrastar e soltar" nos Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="028ef-118">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="028ef-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="028ef-119">See Also</span></span>  
 [<span data-ttu-id="028ef-120">Como Adicionar Dados à Área de Transferência</span><span class="sxs-lookup"><span data-stu-id="028ef-120">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [<span data-ttu-id="028ef-121">Como Recuperar Dados da Área de Transferência</span><span class="sxs-lookup"><span data-stu-id="028ef-121">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [<span data-ttu-id="028ef-122">Operações do Tipo "Arrastar e Soltar" e Suporte à Área de Transferência</span><span class="sxs-lookup"><span data-stu-id="028ef-122">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)