---
title: "Manipulador cancelar a atividade compensável"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b39b5d9277767160225a34be9e0c71a36e7b6d78
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="28d3f-102">Manipulador cancelar a atividade compensável</span><span class="sxs-lookup"><span data-stu-id="28d3f-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="28d3f-103">Este exemplo demonstra o uso de um manipulador cancelar em <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="28d3f-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="28d3f-104">Este exemplo contém dois cenários que demonstram o uso de cancelamento de <xref:System.Activities.Statements.CompensableActivity> . O primeiro cenário contém uma atividade compensável raiz que contém três atividades compensáveis filhos.</span><span class="sxs-lookup"><span data-stu-id="28d3f-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="28d3f-105">Duas atividades filhos completa executar seus corpo da atividade com êxito.</span><span class="sxs-lookup"><span data-stu-id="28d3f-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="28d3f-106">Quando o terceiro corpo filho da atividade é executado, ele encontrar uma exceção que é manipulada cancelar o terceiro processamento de atividade, após o qual cancelamento de atividade da raiz é disparado.</span><span class="sxs-lookup"><span data-stu-id="28d3f-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="28d3f-107">A lógica na atividade raiz nesse exemplo é compensar duas outras atividades filhos que eles concluíram anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28d3f-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
```  
Try  
{  
    CA   
    {  
        CA1   
        {  
        }  
        CA2  
        {  
        }  
        CA3  
        {  
            //Exception here  
            // Then this will get cancelled  
        }  
  
       // Cancellation for the root activity automatically gets called, which, in turn, adds some logic to revert what was done (Or can decide to actually confirm CA1 & CA2 if the user so desires).  
    }  
}  
Catches {  
// Can do more stuff...  
}  
```  
  
 <span data-ttu-id="28d3f-108">O segundo cenário demonstra executar <xref:System.Activities.Statements.TryCatch> paralelamente a <xref:System.Activities.Statements.Delay>, que os terminar antes de <xref:System.Activities.Statements.TryCatch> ramificação.</span><span class="sxs-lookup"><span data-stu-id="28d3f-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="28d3f-109">A condição de conclusão é definida como `true` uma vez que o primeiro ramificação concluir, causando a outra ramificação a ser cancelado.</span><span class="sxs-lookup"><span data-stu-id="28d3f-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
```  
Parallel   
{  
    Branch1   
    {  
        // Small Delay that times out (timeout1) before branch2.  
    }  
    Branch2   
    {  
        CA   
        {  
            CA1   
            {  
            }  
            CA2   
            {  
            }  
            CA3   
            {  
            }  
            If (timeout1)    
            {  
                call Cancel CA  
            }  
        }  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="28d3f-110">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="28d3f-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="28d3f-111">Usando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra CompensationCancellation.sln.</span><span class="sxs-lookup"><span data-stu-id="28d3f-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="28d3f-112">Compilar o exemplo pressionando CTRL+SHIFT+B ou selecione a solução compilação” do menu de compilação.</span><span class="sxs-lookup"><span data-stu-id="28d3f-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="28d3f-113">Executar o exemplo pressionando F5 ou selecione “Iniciar a depuração” no menu debug.</span><span class="sxs-lookup"><span data-stu-id="28d3f-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="28d3f-114">Como alternativa você pode pressionar Ctrl+F5 ou selecione “Iniciar sem depuração” no menu debug.</span><span class="sxs-lookup"><span data-stu-id="28d3f-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="28d3f-115">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="28d3f-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="28d3f-116">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="28d3f-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="28d3f-117">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="28d3f-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="28d3f-118">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="28d3f-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`  
  
## <a name="see-also"></a><span data-ttu-id="28d3f-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="28d3f-119">See Also</span></span>