---
title: "Sessão confiável de WS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
caps.latest.revision: "30"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ec04c91237516bcf535963c2d5ff7b0584c52be2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="ws-reliable-session"></a><span data-ttu-id="95cd0-102">Sessão confiável de WS</span><span class="sxs-lookup"><span data-stu-id="95cd0-102">WS Reliable Session</span></span>
<span data-ttu-id="95cd0-103">Este exemplo demonstra o uso de sessões confiáveis.</span><span class="sxs-lookup"><span data-stu-id="95cd0-103">This sample demonstrates the use of reliable sessions.</span></span> <span data-ttu-id="95cd0-104">Sessões confiáveis oferecem suporte para o sistema de mensagens confiável e sessões.</span><span class="sxs-lookup"><span data-stu-id="95cd0-104">Reliable sessions provide support for reliable messaging and sessions.</span></span> <span data-ttu-id="95cd0-105">Mensagens confiáveis tentativas de comunicação em caso de falha e permite que as garantias de entrega seja especificada, como na ordem chegada de mensagens.</span><span class="sxs-lookup"><span data-stu-id="95cd0-105">Reliable messaging retries communication on failure and allows delivery assurances to be specified, such as in-order arrival of messages.</span></span> <span data-ttu-id="95cd0-106">Sessões de mantêm o estado dos clientes entre chamadas.</span><span class="sxs-lookup"><span data-stu-id="95cd0-106">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="95cd0-107">O exemplo implementa sessões para manter o estado do cliente e especifica as garantias de entrega em ordem.</span><span class="sxs-lookup"><span data-stu-id="95cd0-107">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="95cd0-108">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="95cd0-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="95cd0-109">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="95cd0-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="95cd0-110">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="95cd0-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="95cd0-111">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="95cd0-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 <span data-ttu-id="95cd0-112">Este exemplo se baseia o [Introdução](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa um serviço de cálculo.</span><span class="sxs-lookup"><span data-stu-id="95cd0-112">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="95cd0-113">Os recursos de sessão confiável estão ativados e configurados nos arquivos de configuração do aplicativo para o cliente e o serviço.</span><span class="sxs-lookup"><span data-stu-id="95cd0-113">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>  
  
 <span data-ttu-id="95cd0-114">Neste exemplo, o serviço é hospedado no Internet Information Services (IIS) e o cliente é um aplicativo de console (.exe).</span><span class="sxs-lookup"><span data-stu-id="95cd0-114">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95cd0-115">As instruções de procedimento e a compilação de configuração para este exemplo estão localizadas no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="95cd0-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="95cd0-116">O exemplo usa o `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="95cd0-116">The sample uses the `wsHttpBinding`.</span></span> <span data-ttu-id="95cd0-117">A associação é especificada nos arquivos de configuração para o cliente e o serviço.</span><span class="sxs-lookup"><span data-stu-id="95cd0-117">The binding is specified in the configuration files for both the client and service.</span></span> <span data-ttu-id="95cd0-118">O tipo de associação é especificado no elemento de ponto de extremidade `binding` conforme mostrado no exemplo de configuração do atributo.</span><span class="sxs-lookup"><span data-stu-id="95cd0-118">The binding type is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="95cd0-119">O ponto de extremidade contém um `bindingConfiguration` atributo que faz referência a uma configuração de associação denominada "Binding1".</span><span class="sxs-lookup"><span data-stu-id="95cd0-119">The endpoint contains a `bindingConfiguration` attribute that references a binding configuration named "Binding1."</span></span> <span data-ttu-id="95cd0-120">A configuração de associação permite que as sessões confiáveis, definindo o `enabled` atributo o [ \<reliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) para `true`.</span><span class="sxs-lookup"><span data-stu-id="95cd0-120">The binding configuration enables reliable sessions by setting the `enabled` attribute of the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) to `true`.</span></span> <span data-ttu-id="95cd0-121">Garantias de entrega ordenada sessões são controladas pela definição de atributo ordenada `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="95cd0-121">Delivery assurances for ordered sessions are controlled by setting the ordered attribute to `true` or `false`.</span></span> <span data-ttu-id="95cd0-122">O padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="95cd0-122">The default is `true`.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="95cd0-123">A classe de implementação de serviço implementa <xref:System.ServiceModel.InstanceContextMode.PerSession> instanciamento para manter uma instância da classe separada para cada cliente, conforme mostrado no código de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="95cd0-123">The service implementation class implements <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing to maintain a separate class instance for each client, as shown in the following sample code.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```  
  
 <span data-ttu-id="95cd0-124">Quando você executar o exemplo, as respostas e solicitações de operação são exibidas na janela do console do cliente.</span><span class="sxs-lookup"><span data-stu-id="95cd0-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="95cd0-125">Pressione ENTER na janela do cliente para desligar o cliente.</span><span class="sxs-lookup"><span data-stu-id="95cd0-125">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="95cd0-126">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="95cd0-126">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="95cd0-127">Instalar [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="95cd0-127">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="95cd0-128">Certifique-se de que você executou o [único procedimento de instalação para os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="95cd0-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="95cd0-129">Para compilar o c# ou Visual Basic .NET edição da solução, siga as instruções em [compilar os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="95cd0-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="95cd0-130">Para executar o exemplo em uma configuração ou entre computadores, siga as instruções em [executando os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="95cd0-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95cd0-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="95cd0-131">See Also</span></span>