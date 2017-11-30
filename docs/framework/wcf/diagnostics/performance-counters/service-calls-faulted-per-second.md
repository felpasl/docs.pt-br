---
title: "Serviço: chamadas com falha por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5cf587102814c5bbd2a9c22d88db90f48fbf4da1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-faulted-per-second"></a><span data-ttu-id="356d1-102">Serviço: chamadas com falha por segundo</span><span class="sxs-lookup"><span data-stu-id="356d1-102">Service: Calls Faulted Per Second</span></span>
<span data-ttu-id="356d1-103">Nome do contador: Chamadas com falha por segundo.</span><span class="sxs-lookup"><span data-stu-id="356d1-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="356d1-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="356d1-104">Description</span></span>  
 <span data-ttu-id="356d1-105">Número de chamadas que retornados falhas para esse serviço em um segundo.</span><span class="sxs-lookup"><span data-stu-id="356d1-105">Number of calls that have returned faults to this service in a second.</span></span>  
  
 <span data-ttu-id="356d1-106">Esse contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="356d1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="356d1-107">(1 - N 0 N) / ((D - 1D 0) / F)</span><span class="sxs-lookup"><span data-stu-id="356d1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="356d1-108">Em [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] aplicativos, métodos de serviço se comunicam usando mensagens de falha SOAP de informações de erro de processamento.</span><span class="sxs-lookup"><span data-stu-id="356d1-108">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="356d1-109">Falhas de SOAP são tipos de mensagem que estão incluídos nos metadados para uma operação de serviço e, portanto, crie um contrato de falha que os clientes podem usar para tornar a execução mais robusta ou interativo.</span><span class="sxs-lookup"><span data-stu-id="356d1-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="356d1-110">Como falhas de SOAP são demonstradas para clientes em formato XML, eles são altamente interoperáveis.</span><span class="sxs-lookup"><span data-stu-id="356d1-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="356d1-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="356d1-111">See Also</span></span>  
 <span data-ttu-id="356d1-112">[Specifying and Handling Faults in Contracts and Services](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) (Especificando e lidando com falhas em contratos e serviços)</span><span class="sxs-lookup"><span data-stu-id="356d1-112">[Specifying and Handling Faults in Contracts and Services](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)</span></span>