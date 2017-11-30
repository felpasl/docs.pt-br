---
title: "Serviço: fluxo de transações por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9172075294de8431216540b06aec542753c94621
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="1fad8-102">Serviço: fluxo de transações por segundo</span><span class="sxs-lookup"><span data-stu-id="1fad8-102">Service: Transactions Flowed Per Second</span></span>
<span data-ttu-id="1fad8-103">Nome do contador: Fluxo de transações por segundo.</span><span class="sxs-lookup"><span data-stu-id="1fad8-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1fad8-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="1fad8-104">Description</span></span>  
 <span data-ttu-id="1fad8-105">Número de transações fluíram para operações neste serviço em um segundo.</span><span class="sxs-lookup"><span data-stu-id="1fad8-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="1fad8-106">Esse contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="1fad8-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1fad8-107">(1 - N 0 N) / ((D - 1D 0) / F)</span><span class="sxs-lookup"><span data-stu-id="1fad8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>