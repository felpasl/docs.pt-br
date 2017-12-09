---
title: "Como usar componentes compatíveis com o padrão assíncrono baseado em evento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49e03a8d886ccd4ed6e4b2a19692c1874f5928ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="f2709-102">Como usar componentes compatíveis com o padrão assíncrono baseado em evento</span><span class="sxs-lookup"><span data-stu-id="f2709-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="f2709-103">Muitos componentes oferecem a opção de executar seu trabalho de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="f2709-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="f2709-104">O <xref:System.Media.SoundPlayer> e <xref:System.Windows.Forms.PictureBox> componentes, por exemplo, habilitar a carga sons e imagens "em segundo plano", enquanto o thread principal continua em execução sem interrupções.</span><span class="sxs-lookup"><span data-stu-id="f2709-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="f2709-105">Usando métodos assíncronos em uma classe que oferece suporte a [baseado em evento visão geral do padrão assíncrono](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) pode ser tão simples quanto anexando um manipulador de eventos para o componente *MethodName* `Completed` evento, Assim como faria para qualquer outro evento.</span><span class="sxs-lookup"><span data-stu-id="f2709-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's *MethodName*`Completed` event, just as you would for any other event.</span></span> <span data-ttu-id="f2709-106">Quando você chama o *MethodName* `Async` método, seu aplicativo continuará em execução sem interrupção até que o *MethodName* `Completed` é gerado.</span><span class="sxs-lookup"><span data-stu-id="f2709-106">When you call the *MethodName*`Async` method, your application will continue running without interruption until the *MethodName*`Completed` event is raised.</span></span> <span data-ttu-id="f2709-107">O manipulador de eventos, você pode examinar o <xref:System.ComponentModel.AsyncCompletedEventArgs> parâmetro para determinar se a operação assíncrona foi concluída com êxito ou se foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="f2709-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="f2709-108">Para obter mais informações sobre o uso de manipuladores de eventos, consulte [visão geral de manipuladores de evento](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f2709-108">For more information about using event handlers, see [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="f2709-109">O procedimento a seguir mostra como usar o recurso de carregamento de imagem assíncrono de um <xref:System.Windows.Forms.PictureBox> controle.</span><span class="sxs-lookup"><span data-stu-id="f2709-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="f2709-110">Para ativar um controle PictureBox assincronamente carregar uma imagem</span><span class="sxs-lookup"><span data-stu-id="f2709-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1.  <span data-ttu-id="f2709-111">Criar uma instância do <xref:System.Windows.Forms.PictureBox> componente no formulário.</span><span class="sxs-lookup"><span data-stu-id="f2709-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2.  <span data-ttu-id="f2709-112">Atribuir um manipulador de eventos para o <xref:System.Windows.Forms.PictureBox.LoadCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="f2709-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="f2709-113">Verifique os erros que possam ter ocorrido durante o download assíncrono aqui.</span><span class="sxs-lookup"><span data-stu-id="f2709-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="f2709-114">Isso também é onde você verifica o cancelamento.</span><span class="sxs-lookup"><span data-stu-id="f2709-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  <span data-ttu-id="f2709-115">Adicione dois botões, chamados `loadButton` e `cancelLoadButton`, ao formulário.</span><span class="sxs-lookup"><span data-stu-id="f2709-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="f2709-116">Adicionar <xref:System.Windows.Forms.Control.Click> manipuladores de eventos para iniciar e cancelar o download.</span><span class="sxs-lookup"><span data-stu-id="f2709-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="f2709-117">Execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f2709-117">Run your application.</span></span>  
  
     <span data-ttu-id="f2709-118">Conforme o download da imagem prossegue, mover o formulário gratuitamente, minimize- e maximizá-lo.</span><span class="sxs-lookup"><span data-stu-id="f2709-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2709-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f2709-119">See Also</span></span>  
 [<span data-ttu-id="f2709-120">Como executar uma operação em segundo plano</span><span class="sxs-lookup"><span data-stu-id="f2709-120">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="f2709-121">Visão Geral do Padrão Assíncrono Baseado em Evento</span><span class="sxs-lookup"><span data-stu-id="f2709-121">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="f2709-122">NÃO está em compilação: Multithread no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2709-122">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)