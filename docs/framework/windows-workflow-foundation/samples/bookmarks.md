---
title: Bookmarks2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 035fadb2-49fa-4ac7-b398-daf138f66e87
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01373b820c0c8c4747eae60ff59063fdbfc4493b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="bookmarks"></a><span data-ttu-id="4ed66-102">Indicadores</span><span class="sxs-lookup"><span data-stu-id="4ed66-102">Bookmarks</span></span>
<span data-ttu-id="4ed66-103">Este exemplo demonstra como escrever uma atividade personalizado que cria um indicador para receber entrada externo.</span><span class="sxs-lookup"><span data-stu-id="4ed66-103">This sample demonstrates how to write a custom activity that creates a bookmark to receive external input.</span></span> <span data-ttu-id="4ed66-104">O exemplo também inclui um aplicativo de console básico que usa a atividade personalizado em um fluxo de trabalho e mostra como descobrir e para continuar indexadores associados com um fluxo de trabalho em execução como ouvinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="4ed66-104">The sample also includes a basic console application that uses the custom activity in a workflow and shows how to discover and resume bookmarks associated with a running workflow instance.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4ed66-105">indicadores, consulte [indicadores](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="4ed66-105"> bookmarks, see [Bookmarks](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4ed66-106">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="4ed66-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4ed66-107">Abra a solução de exemplo de Bookmarks.sln em [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ed66-107">Open the Bookmarks.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="4ed66-108">Para criar a solução, pressione CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="4ed66-108">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4ed66-109">Para executar o exemplo, pressione CTRLl + F5.</span><span class="sxs-lookup"><span data-stu-id="4ed66-109">To run the sample, press CTRLl + F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ed66-110">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="4ed66-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4ed66-111">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4ed66-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4ed66-112">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="4ed66-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4ed66-113">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="4ed66-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CodeBodied\Bookmarks`  
  
## <a name="see-also"></a><span data-ttu-id="4ed66-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4ed66-114">See Also</span></span>