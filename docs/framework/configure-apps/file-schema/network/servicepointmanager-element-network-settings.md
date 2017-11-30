---
title: "&lt;servicePointManager&gt; elemento (configurações de rede)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 85ccad3e2c3b237e286f3737589a5e58994521bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicepointmanagergt-element-network-settings"></a><span data-ttu-id="ab9b3-102">&lt;servicePointManager&gt; elemento (configurações de rede)</span><span class="sxs-lookup"><span data-stu-id="ab9b3-102">&lt;servicePointManager&gt; Element (Network Settings)</span></span>
<span data-ttu-id="ab9b3-103">Configura conexões aos recursos da rede.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="ab9b3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ab9b3-104">\<configuration></span></span>  
<span data-ttu-id="ab9b3-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="ab9b3-105">\<system.net></span></span>  
<span data-ttu-id="ab9b3-106">\<Configurações ></span><span class="sxs-lookup"><span data-stu-id="ab9b3-106">\<settings></span></span>  
<span data-ttu-id="ab9b3-107">\<servicePointManager ></span><span class="sxs-lookup"><span data-stu-id="ab9b3-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab9b3-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ab9b3-108">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab9b3-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ab9b3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ab9b3-110">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab9b3-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ab9b3-111">Attributes</span></span>  
  
|<span data-ttu-id="ab9b3-112">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="ab9b3-112">**Attribute**</span></span>|<span data-ttu-id="ab9b3-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ab9b3-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="ab9b3-114">Especifica se o sistema deve verificar se o nome do certificado corresponde o nome de host do servidor antes de usar o certificado.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="ab9b3-115">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="ab9b3-116">Especifica se o sistema deve verificar se o certificado foi revogado antes de usar o certificado.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="ab9b3-117">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="ab9b3-118">Especifica quanto tempo serviço DNS (Domain Name) resoluções são armazenados em cache em conjunto com a opção DNS Round Robin, em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="ab9b3-119">O valor padrão é de 120.000 milissegundos (dois minutos).</span><span class="sxs-lookup"><span data-stu-id="ab9b3-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="ab9b3-120">Especifica se resolução DNS do host nomes com retorno de vários endereços IP (Internet Protocol) de todos os endereços ou apenas o primeiro.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="ab9b3-121">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="ab9b3-122">Especifica a política de criptografia aplicada a uma sessão SSL/TLS em um <xref:System.Net.ServicePointManager> instância.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="ab9b3-123">Os valores possíveis são equivalentes aos valores para o <xref:System.Net.Security.EncryptionPolicy> enumeração.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="ab9b3-124">O uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> é necessária quando a política de criptografia é definida como `NoEncryption`.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="ab9b3-125">O valor padrão é `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="ab9b3-126">Especifica se os métodos de POSTAGEM devem esperar receber um `100-continue` resposta do servidor.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="ab9b3-127">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="ab9b3-128">Especifica se as conexões controlados pelo Gerenciador de ponto de serviço usar o algoritmo Nagle.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="ab9b3-129">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab9b3-130">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ab9b3-130">Child Elements</span></span>  
 <span data-ttu-id="ab9b3-131">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab9b3-132">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ab9b3-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ab9b3-133">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ab9b3-133">**Element**</span></span>|<span data-ttu-id="ab9b3-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ab9b3-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ab9b3-135">Configurações</span><span class="sxs-lookup"><span data-stu-id="ab9b3-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="ab9b3-136">Configura as opções de rede básicaspara o namespace <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="ab9b3-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab9b3-137">Comentários</span><span class="sxs-lookup"><span data-stu-id="ab9b3-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ab9b3-138">Arquivos de Configuração</span><span class="sxs-lookup"><span data-stu-id="ab9b3-138">Configuration Files</span></span>  
 <span data-ttu-id="ab9b3-139">Esse elemento pode ser usado no arquivo de configuração do aplicativo ou o arquivo de configuração de máquina (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="ab9b3-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab9b3-140">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ab9b3-140">See Also</span></span>  
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [<span data-ttu-id="ab9b3-141">Esquema de configurações de rede</span><span class="sxs-lookup"><span data-stu-id="ab9b3-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)