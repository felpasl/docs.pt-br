---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: df75fdfa68e11a4a017dffa54e1bb4d628940968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="2fe56-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="2fe56-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="2fe56-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="2fe56-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fe56-104">ID</span><span class="sxs-lookup"><span data-stu-id="2fe56-104">ID</span></span>|<span data-ttu-id="2fe56-105">301</span><span class="sxs-lookup"><span data-stu-id="2fe56-105">301</span></span>|  
|<span data-ttu-id="2fe56-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2fe56-106">Keywords</span></span>|<span data-ttu-id="2fe56-107">Solução de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="2fe56-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="2fe56-108">Nível</span><span class="sxs-lookup"><span data-stu-id="2fe56-108">Level</span></span>|<span data-ttu-id="2fe56-109">Erro</span><span class="sxs-lookup"><span data-stu-id="2fe56-109">Error</span></span>|  
|<span data-ttu-id="2fe56-110">Canal</span><span class="sxs-lookup"><span data-stu-id="2fe56-110">Channel</span></span>|<span data-ttu-id="2fe56-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="2fe56-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2fe56-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="2fe56-112">Description</span></span>  
 <span data-ttu-id="2fe56-113">Esse evento é emitido do código do usuário.</span><span class="sxs-lookup"><span data-stu-id="2fe56-113">This event is emitted from user code.</span></span> <span data-ttu-id="2fe56-114">Os desenvolvedores podem emitir esse evento quando ocorre um erro personalizadas em seu serviço.</span><span class="sxs-lookup"><span data-stu-id="2fe56-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="2fe56-115">Isso pode ser feito usando o <xref:System.Diagnostics.Eventing> APIs.</span><span class="sxs-lookup"><span data-stu-id="2fe56-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="2fe56-116">Além disso, há um exemplo do WCF que encapsula essa API e demonstra como emitir corretamente este evento.</span><span class="sxs-lookup"><span data-stu-id="2fe56-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2fe56-117">Mensagem</span><span class="sxs-lookup"><span data-stu-id="2fe56-117">Message</span></span>  
 <span data-ttu-id="2fe56-118">Nome: '%1', referência: '%2', carga: % 3</span><span class="sxs-lookup"><span data-stu-id="2fe56-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="2fe56-119">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2fe56-119">Details</span></span>  
  
|<span data-ttu-id="2fe56-120">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="2fe56-120">Data Item Name</span></span>|<span data-ttu-id="2fe56-121">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="2fe56-121">Data Item Type</span></span>|<span data-ttu-id="2fe56-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="2fe56-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2fe56-123">Nome</span><span class="sxs-lookup"><span data-stu-id="2fe56-123">Name</span></span>|`xs:string`|<span data-ttu-id="2fe56-124">O nome do evento definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="2fe56-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="2fe56-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="2fe56-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="2fe56-126">Para serviços hospedados na Web, este campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="2fe56-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2fe56-127">O formato é definido como ' caminho Virtual do aplicativo de nome de Site da Web &#124; Caminho Virtual do serviço &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="2fe56-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2fe56-128">Exemplo: ' Default Web Site/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="2fe56-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2fe56-129">Carga</span><span class="sxs-lookup"><span data-stu-id="2fe56-129">Payload</span></span>|`xs:string`|<span data-ttu-id="2fe56-130">A carga do evento definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="2fe56-130">The user-defined payload of the event.</span></span>|